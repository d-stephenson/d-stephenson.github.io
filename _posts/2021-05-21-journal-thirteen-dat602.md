---
layout: post
title:  "Journal #Thirteen [DAT602] - Practical Project Development" 
author: Dale Stephenson
categories: [ DAT602, Journal, Database Application Development ]
image: assets/images/DAT602-J13.jpeg
featured: true
hidden: true
---
<i>Practical Project Development</i>

JOURNAL #THIRTEEN [DAT602]

<h2>Practical Project Development</h2>

It's well past time that this journal series for <code>DAT602</code> included some practical examples of the project development being worked on, now that milestone 2 has been completed it's reasonable to share the progress made. For those interested in seeing the complete MySql and C# please go to the <a href='https://github.com/d-stephenson/DAT602' target='_blank'>GitHub repo</a>.

<h3>MySQL DDL</h3>

The following SQL is the player table:

<pre><code>DROP TABLE IF EXISTS tblPlayer;

CREATE TABLE tblPlayer (
	PlayerID int AUTO_INCREMENT,
	Email varchar(50) NOT NULL,
	Username varchar(10) NOT NULL,
	`Password` BLOB NOT NULL,
	AccountAdmin bit DEFAULT FALSE NOT NULL,
	AccountLocked bit DEFAULT FALSE NOT NULL,
	ActiveStatus bit DEFAULT FALSE NOT NULL,
	FailedLogins tinyint DEFAULT 0 NOT NULL,
	HighScore int DEFAULT 0 NOT NULL, 
	PRIMARY KEY (PlayerID),
	CONSTRAINT UC_Email UNIQUE (Email),
	CONSTRAINT UC_Username UNIQUE (Username),
	CONSTRAINT CHK_Email CHECK (Email Like '_%@_%._%')
);

	ALTER TABLE tblPlayer AUTO_INCREMENT=000001;
	ALTER TABLE tblPlayer ADD COLUMN Salt varchar(36); 
	ALTER TABLE tblPlayer ENCRYPTION='Y'; -- Encrypt Player table
</code></pre>

<h3>MySQL Create Users & Grants</h3>

Adding a <code>mysql.user</code> to the database and setting grants:

<pre><code>SELECT `user`, `host` FROM mysql.user;

DROP USER IF EXISTS 'databaseAdmin'@'localhost';
CREATE USER IF NOT EXISTS 'databaseAdmin'@'localhost' IDENTIFIED BY 'P@ssword1';
GRANT ALL ON sdghGameDatabase TO 'databaseAdmin'@'localhost';

SHOW GRANTS FOR 'databaseAdmin'@'localhost';
SHOW GRANTS FOR 'root'@'localhost';
</code></pre>

<h3>MySQL Procedures</h3>

The following are some of the procedures created as they relate to the CRUD analysis.

<h4>User login and home screen display data:</h4>

<pre><code>DROP PROCEDURE IF EXISTS LoginCheckCredentials;
DELIMITER //
CREATE DEFINER = 'root'@'localhost' PROCEDURE LoginCheckCredentials(
		IN pUsername varchar(50), 
		IN pPassword BLOB
    )
SQL SECURITY DEFINER

BEGIN
	DECLARE retrieveSalt varchar(36) DEFAULT NULL;
	DECLARE proposedUID int DEFAULT NULL;
	DECLARE currentAS bit DEFAULT NULL;
          
    SELECT Salt
    FROM tblPlayer
	WHERE
		Username = pUsername
	INTO retrieveSalt; -- Retrieves the users SALT record 
    
	SELECT PlayerID
	FROM tblPlayer
	WHERE
		AES_ENCRYPT(CONCAT(retrieveSalt, pPassword), 'Game_Key_To_Encrypt') = `Password` 
        AND pUsername = Username
	INTO proposedUID; -- Retrieves the users Username and Password

	SELECT ActiveStatus
	FROM tblPlayer
	WHERE
		Username = pUsername
	INTO currentAS;
    
    IF proposedUID IS NULL AND currentAS = 0 THEN 
		UPDATE tblPlayer
		SET FailedLogins = FailedLogins +1, AccountLocked = (FailedLogins +1) > 5, ActiveStatus = (FailedLogins +1) < 1
        WHERE 
			Username = pUsername;
		    
		SELECT 'You have entered an incorrect Username or Password, after 5 failed attempts your account will be locked' AS MESSAGE;
        -- Increments the failed logins, if it equals 5 then account is locked
	ELSEIF proposedUID IS NOT NULL AND currentAS = 0 THEN
		UPDATE tblPlayer
        SET ActiveStatus = 1, FailedLogins = 0, AccountLocked = 0
        WHERE 
			Username = pUsername; 
            
		SELECT 'Success' AS MESSAGE;
        
		SELECT GameID AS 'GameID', COUNT(pl.GameID) AS 'PlayerCount'
        FROM tblPlayer py 
            JOIN tblPlay pl ON py.PlayerID = pl.PlayerID
        GROUP BY pl.GameID;  
        
		SELECT Username AS 'Player', HighScore AS 'HighScore' 
		FROM tblPlayer; 
		-- If credentials are correct user is logged into account by setting active status to true
	ELSE 
		SELECT 'You are logged in' AS MESSAGE;
    
		SELECT GameID AS 'GameID', COUNT(pl.GameID) AS 'PlayerCount'
        FROM tblPlayer py 
            JOIN tblPlay pl ON py.PlayerID = pl.PlayerID
        GROUP BY pl.GameID;  
        
		SELECT Username AS 'Player', HighScore AS 'HighScore' 
		FROM tblPlayer;  
        -- Conditions are met so user is already logged in
	END IF;
END //
DELIMITER ;
</code></pre>

<h4>Moving a player to an adjacent tile:</h4>

<pre><code>DROP PROCEDURE IF EXISTS MovePlayer;
DELIMITER //
CREATE DEFINER = 'root'@'localhost' PROCEDURE MovePlayer(
        IN pTileID int,
        IN pPlayerID int,
        IN pGameID int
    )
SQL SECURITY DEFINER

BEGIN
	DECLARE currentTurn varchar(10) DEFAULT NULL;
	DECLARE availableTile int DEFAULT NULL;
    DECLARE ifPlayerOnTileAreTheyActive bit DEFAULT NULL;
	DECLARE currentTileRow tinyint DEFAULT NULL;
	DECLARE currentTileColumn tinyint DEFAULT NULL;
	DECLARE newTileRow tinyint DEFAULT NULL;
	DECLARE newTileColumn tinyint DEFAULT NULL;
    
	SELECT CharacterTurn -- Checks the character turn for the game
	FROM tblGame
	WHERE 
		GameID = pGameID 
	INTO currentTurn;
    
	SELECT TileID -- Checks if a tile is empty and available
	FROM tblTile
	WHERE 
		TileID NOT IN (SELECT TileID 
					   FROM tblPlay 
                       WHERE 
							GameID = pGameID) 
							AND TileID = pTileID
							AND HomeTile = FALSE 
	INTO availableTile; 
    
	SELECT ActiveStatus -- Checks the active status if a player is on the tile selected
    FROM tblPlayer pl
		JOIN tblPlay py ON pl.PlayerID = py.PlayerID
	WHERE 
		py.TileID = pTileID
		AND GameID = pGameID
    INTO ifPlayerOnTileAreTheyActive; -- This allows player to move to a tile with another player located but the active status is 0

    SELECT TileRow -- The current player tile row
    FROM tblTile ti 
        JOIN tblPlay pl ON ti.TileID = pl.TileID
	WHERE 
		PlayerID = pPlayerID 
        AND GameID = pGameID
	INTO currentTileRow;
    
	SELECT TileColumn -- The current player tile column
    FROM tblTile ti 
        JOIN tblPlay pl ON ti.TileID = pl.TileID
	WHERE 
		PlayerID = pPlayerID 
        AND GameID = pGameID
	INTO currentTileColumn;
        
	SELECT TileRow -- The selected tile row
    FROM tblTile
	WHERE 
		TileID = pTileID
	INTO newTileRow;
    
	SELECT TileColumn -- The selected tile column
    FROM tblTile
	WHERE 
		TileID = pTileID
	INTO newTileColumn;
    
    BEGIN
		IF ((newTileRow = currentTileRow OR newTileRow = currentTileRow + 1 OR newTileRow = currentTileRow - 1) 
			AND (newTileColumn = currentTileColumn OR newTileColumn = currentTileColumn + 1 OR newTileColumn = currentTileColumn - 1)) 
			AND (availableTile IS NOT NULL OR ifPlayerOnTileAreTheyActive = 0 OR pTileID = 001) 
			AND (currentTurn = (SELECT CharacterName 
								FROM tblPlay 
								WHERE 
									PlayerID = pPlayerID 
									AND GameID = pGameID)) THEN  
			UPDATE tblPlay
			SET TileID = pTileID
			WHERE 
				PlayerID = pPlayerID 
				AND GameID = pGameID;
						
			SELECT 'Your character has moved!!!' AS MESSAGE;	
			
            SELECT TileColour, TileRow, TileColumn 
			FROM tblCharacter ch 
				JOIN tblPlay pl ON ch.CharacterName = pl.CharacterName
				JOIN tblTile ti ON pl.TileID = ti.TileID
			WHERE 
				PlayerID = pPlayerID;
		ELSE
			SELECT 'Your character cant move to this tile!!!' AS MESSAGE;
		END IF;
	END;
END //
DELIMITER ;
</code></pre>

<h3>C# Data Access</h3>

Data Access in C# for the Login Check Credentials Procedure:

<code>
// Login Check Credentials Procedure
        public HomeDisplayData LoginCheckCredentials(string pUsername, string pPassword)
        {
            HomeDisplayData theHomeDisplayData = new HomeDisplayData();
            List<MySqlParameter> paramInput = new List<MySqlParameter>();
            var paramUsername = new MySqlParameter("@Username", MySqlDbType.VarChar, 10);
            var paramPassword = new MySqlParameter("@Password", MySqlDbType.Blob);
            paramUsername.Value = pUsername;
            paramPassword.Value = pPassword;
            paramInput.Add(paramUsername);
            paramInput.Add(paramPassword);

            var aDataSet = MySqlHelper.ExecuteDataset(DataAccess.mySqlConnection, "LoginCheckCredentials(@Username,@Password)", paramInput.ToArray());

            var aMessage = (aDataSet.Tables[0].Rows[0])["MESSAGE"].ToString();
            theHomeDisplayData.message = aMessage;
            Console.WriteLine(aMessage);
            if ((aMessage == "Success") || (aMessage == "You are logged in"))
            {
                theHomeDisplayData.GameCount = (from aResult in aDataSet.Tables[1].AsEnumerable()
                                                select
                                                    new GameCount
                                                    {
                                                        GameID = Convert.ToInt32(aResult.ItemArray[0].ToString()),//Field<int>("GameID"),
                                                        PlayerCount = Convert.ToInt32(aResult.ItemArray[1].ToString())//aResult.Field<int>("PlayerCount"),
                                                    }).ToList();

                theHomeDisplayData.PlayerHighScore = (from aResult in aDataSet.Tables[2].AsEnumerable()
                                                      select
                                                          new PlayerHighScore
                                                          {
                                                              Player = aResult.Field<string>("Player"),
                                                              HighScore = Convert.ToInt32(aResult.ItemArray[1].ToString())//aResult.Field<int>("HighScore"),
                                                          }).ToList();
                theHomeDisplayData.haveData = true;

                return theHomeDisplayData;
            }
            else 
            {
                return null;
            }
        }
</code>

<h3>C# Program</h3>

Program in C# to display a selection list menu:

<code>
namespace DAT602_ConsoleApp
{
    class Program
    {
        static void Main(string[] args)
        {
            bool showMenu = true;
            while (showMenu)
            {
                showMenu = MainMenu();
            }
        }

        private static bool MainMenu()
        {
            Console.Clear();
            Console.WriteLine("Choose an option:");
            Console.WriteLine("1) Register account");
            Console.WriteLine("2) User login");
            Console.WriteLine("3) Create a new game");
            Console.WriteLine("4) Join a game");
            Console.WriteLine("5) Move a player");
            Console.WriteLine("6) Find a gem");
            Console.WriteLine("7) Select a gem");
            Console.WriteLine("8) Update turn");
            Console.WriteLine("9) Logout of game");
            Console.WriteLine("10) Enter admin area");
            Console.WriteLine("11) Kill a game");
            Console.WriteLine("12) Add a new player");
            Console.WriteLine("13) Update a players details");
            Console.WriteLine("14) Delete a player");
            Console.WriteLine("15) Exit");
            Console.Write("\r\nSelect an option: ");

            DataAccess aDataAccess = new DataAccess();

            switch (Console.ReadLine())
            {
                case "1":
                    Console.WriteLine(aDataAccess.NewUserRegistration("ConsoleU_1@appmail.com", "ConsoleU_1", "P@ssword1"));
                    Console.ReadLine();
                    return true;
                case "2":
                    var aHomePage = aDataAccess.LoginCheckCredentials("ConsoleU_1", "P@ssword1");
                    Console.WriteLine("List of games");
                    foreach (var item in aHomePage.GameCount)
                    {
                        Console.WriteLine("This game id is: " + item.GameID.ToString());
                        Console.WriteLine("This game's player count is: " + item.PlayerCount.ToString());
                    }
                    Console.WriteLine("List of players");
                    foreach (var item in aHomePage.PlayerHighScore)
                    {
                        Console.WriteLine("This player is: " + item.Player);
                        Console.WriteLine("Their high score is: " + item.HighScore.ToString());
                    }
                    Console.ReadLine();
                    return true;
                case "3":
                    Console.WriteLine(aDataAccess.NewGame("ConsoleU_1"));
                    Console.ReadLine();
                    return true;
                case "4":
                    Console.WriteLine(aDataAccess.JoinGame("100003", "1"));
                    Console.ReadLine();
                    return true;
                case "5":
                    var aTileInfo = aDataAccess.MovePlayer("32", "9", "100003"); 
                    Console.WriteLine("Tile Details");
                    foreach (var item in aTileInfo.TileInfo)
                    {
                        Console.WriteLine("This tile colour is: " + item.TileColour);
                        Console.WriteLine("The tile row is: " + item.TileRow.ToString());
                        Console.WriteLine("The tile column is: " + item.TileColumn.ToString());
                    }
                    Console.ReadLine();
                    return true;
                case "6":
                    var aGemSelection = aDataAccess.FindGem("50", "9", "100003");
                    if (aGemSelection != null)
                    {
                    foreach (var item in aGemSelection.GemSelection)
                        {
                            Console.WriteLine("List of gems");
                            Console.WriteLine("This item id is: " + item.ItemID.ToString());
                            Console.WriteLine("This gem type is: " + item.GemType);
                            Console.WriteLine("The points are: " + item.Points.ToString());
                            Console.WriteLine("The game id is: " + item.GameID.ToString());
                            Console.WriteLine("This player id is: " + item.PlayerID.ToString());
                            Console.WriteLine("This play id is: " + item.PlayID.ToString());
                            Console.WriteLine("This tile id is: " + item.TileID.ToString());
                        }
                    }
                    Console.ReadLine();
                    return true;
</code>