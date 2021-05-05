---
layout: post
title:  "Journal #Five [DAT602] - Structured Query Language (SQL)" 
author: Dale Stephenson
categories: [ DAT602, Journal, Database Application Development ]
image: assets/images/DAT602-J5.jpeg
featured: true
hidden: true
---
<i>Structured Query Language (SQL)</i>

JOURNAL #FIVE [DAT602]

<h2>Structured Query Language (SQL)</h2>

<h3>WHAT</h3>

The game database has been developed as a MariaDB hosted with AWS, which is backed up daily to ensure there is no loss of data. The data centre is located in Frankfurt, Germany to take advantage of the EU GDPR to offer the greatest level of privacy protection for users and their data. Details of the AWS MariaDB are as follows:

<img src="/assets/images/DAT602-MariaDb_AWS.png" alt="AWS MariaDb Screen">

Unfortunately due to firewall rules when connected to the wi-fi in class the database was not accessible, so instead the database is now being stored locally. 

<h3>WHY</h3>

The Data Definition Language (DDL) is the creation (CREATE) of tables and their columns. The following tables have been established in the game database:

<h4>Player Table</h4>

All player registration information is stored in the player table, this includes their current status and any account privileges. The table also stores the player's high score. The table consists of the following fields:

- Player ID
- Email
- Username
- Password
- Account Admin
- Account Locked
- Active Status
- Failed Logins
- High Scores

<h4>Game Table</h4>

The game table stores each instance of games that have been set up by players, it includes an identifier, the board type being played and the character turn. The fields are as follows:

- Game ID
- Board Type
- Character Turn 

<h4>Board Table</h4>

The board table is established as a parent table, the table assigns games to boards and boards to tiles that make up the board. The table consists of the following fields:

- Board Type
- X-Axis
- Y-Axis

<h4>Tile Table</h4>

The tile table lists the separate tiles that make up the X and Y-axis of the board type. The tiles have a unique identifier that can be used to layout the board based on tile locations. The row and column numbers could have been used as a combine primary key, however, more flexibility is offered to stakeholders if they choose to create a more uniquely shaped board later in the business model life cycle. The fields are as follows: 

- Tile ID
- Tile Row
- Tile Column
- Home Tile

<h4>Board/Tile Table</h4>

The board/tile table is used to link a tile record to the board type record in the relational database. This join table allows for different sized boards to created and potentially different shapes of boards. 

<h4>Character Table</h4>

The character table establishes the seven dwarfs as characters, they are then assigned to players when they create or join a game. The fields are as follows:

- Name
- Tile Colour

<h4>Gem Table</h4>

The gem table establishes the gem types that available for the player to collect when they land on a tile. The fields are as follows:

- Type
- Points

<h4>Item Table</h4>

The item table acts to assign gems to an item record, as there can be multiple instances of the same gem type on each board the items define instances of the gems. The fields are as follows:

- Item ID
- Gem Type

<h4>Play Table</h4>

The play table acts to assign players to specific games, playing a specific character, which is currently located on one tile. The fields are as follows:

- PlayID
- Player ID 
- Character Name
- Game ID 
- Tile ID
- Play Score

<h4>Item/Game Table</h4>

The item/game table is used to link an item record to the game record in the relational database. This join table allows for items to be associated with games so they can be found by players. Two additional fields are required by this table as follows:

- Tile ID
- Play ID

<h3>HOW</h3>

The following screens show the DDL that has been used to create the game database. The CREATE TABLE DDL has been stored in a procedure which is called once all the tables have been created.

<center><img src="/assets/images/DAT602-DDL1.png" alt="Create database"></center><br>
<center><img src="/assets/images/DAT602-DDL2.png" alt="Create stored procedure"></center><br>
<center><img src="/assets/images/DAT602-DDL2.png" alt="Create table"></center>

