---
layout: post
title:  "Journal #Seven [DAT602] - Procedures & Functions" 
author: Dale Stephenson
categories: [ DAT602, Journal, Database Application Development ]
image: assets/images/DAT602-J7.jpeg
featured: true
hidden: true
---
<i>Procedures & Functions</i>

JOURNAL #SEVEN [DAT602]

<h2>Procedures & Functions</h2>

<h3>Determinism</h3>
 
Deterministic functions will return the same results if the same values are being called, non-deterministic functions on the other hand might return different results when called, even if the input values are the same.
 
Built-in functions are either deterministic or nondeterministic, their state cannot be changed. For example, the <code>AVG</code> function is always deterministic and will return the same result if the same value is called. The <code>GETDATE</code> function however, is nondeterministic, returning the current date and time that will always be a different result when called. Specifying a clause such as <code>ORDER BY</code> in a query will not change the determinism of a function.
 
The following are examples of deterministic and nondeterministic functions:
 
<table style="width:100%">
  <tr>
    <th>Deterministic Functions</th>
    <th>Nondeterministic Functions</th>
  </tr>
  <tr>
    <td><code>ROUND</code></td>
    <td><code>GETDATE</code></td>
  </tr>
  <tr>
    <td><code>ISNULL</code></td>
    <td><code>GETUTCDATE</code></td>
  </tr>
    <tr>
    <td><code>DATALENGTH</code></td>
    <td><code>GET_TRANSMISSION_STATUS</code></td>
  </tr>
  <tr>
    <td><code>DATEADD</code></td>
    <td><code>LAST_VALUE</code></td>
  </tr>
    <tr>
    <td><code>EXP</code></td>
    <td><code>NEWSEQUENTIALID</code></td>
  </tr>
  <tr>
    <td><code>SQUARE</code></td>
    <td><code>RAND</code></td>
  </tr>
  <tr>
    <td><code>NULLIF</code></td>
    <td><code>CURRENT_TIMESTAMP</code></td>
  </tr>
</table><br>
 
<h3>Access Control</h3>
 
Stored procedures are used as a way to improve the performance of databases, they are also used to improve database security and restrict user access. The security aspects of a stored procedure include:
 
<code>DEFINER</code> - A clause that specifies the creator of the stored procedure.<br>
<code>SQL SECURITY</code> - A clause that specifics the context of the stored procedure.
 
<h3>Definer</h3>
 
The <code>DEFINER</code> attribute should match the credentials of a valid user account to prevent an error from being returned when the procedure is invoked. The <code>DEFINER</code> assigns an owner to a procedure, if it's defined with <code>SQL SECURITY</code> then it will run with the privileges of that account, regardless of which users invoke the procedure.
 
Database users that have sufficient privileges, such as <code>SET_USER_ID</code> or <code>SUPER</code>, can select any user as the <code>DEFINER</code> attribute. If a user does not have sufficient privileges then the only account they specific as the <code>DEFINER</code> is their own.
 
Before selecting a <code>DEFINER</code> in a stored procedure a check on all users and the host can be made, using the following statement:
 
<code>SELECT user, host FROM mysql.user;</code>
 
To create a <code>DEFINER</code> within a database a query can be created as a stored procedure as follows:

<code>
delimiter //<br>
CREATE DEFINER = 'username'@'localhost' PROCEDURE SP_Definer()<br>
BEGIN<br>
  SELECT 'MySQL Definer';<br>
END;<br>
//<br>
</code>
 
<h3>SQL Security</h3>
 
When considering the security of stored procedures two characteristics can be specified, the <code>DEFINER</code> context and the <code>INVOKER</code> context. If neither is selected then the <code>DEFINER</code> context is set as the default characteristic of the stored procedure.
 
Selecting the <code>DEFINER</code> security context will execute the stored procedure with the privileges of the account named in the <code>DEFINER</code> attribute, which might be different from the privileges assigned to the user invoking the procedure. In procedures established in this way, the <code>INVOKER</code> privileges are disregarded for the purpose of calling the procedure, even if the <code>DEFINER</code> privileges are higher than that of the <code>INVOKER</code>.
 
When considering the security of a database, those users with a high level of security should seriously consider who needs to call any given procedure.
 
The following is an example of a stored procedure that has declared an <code>SQL SECURITY DEFINER</code> characteristic:

<code> 
delimiter //<br>
CREATE DEFINER = 'username'@'localhost' PROCEDURE SP_Definer()<br>
SQL SECURITY DEFINER<br>
BEGIN<br>
  UPDATE tbl_Accounts SET counter = counter + 1;<br>
END;<br>
//<br>
-- Executes with the DEFINER security context privilege<br>
</code>
 
To execute this procedure, any user that has the <code>EXECUTE</code> privilege can <code>CALL</code> the statement, as well as <code>UPDATE</code> the table tbl_Account under the <code>DEFINER</code> security context.
 
If a stored procedure selects the <code>INVOKER</code> security context then it can only be invoked by those users that have the appropriate privileges. The <code>DEFINER</code> attribute privileges are disregarded for the purpose of calling the procedure.
 
The following is an example of a stored procedure that has declared an <code>SQL SECURITY INVOKER</code> characteristic:

<code> 
delimiter //<br>
CREATE DEFINER = 'username'@'localhost' PROCEDURE SP_Invoker()<br>
SQL SECURITY INVOKER<br>
BEGIN<br>
  UPDATE tbl_Accounts SET counter = counter + 1;<br>
END;<br>
//<br>
-- Executes with the INVOKER security context privilege<br>
</code>
 
This procedure executes in the <code>INVOKER</code> security context, meaning the <code>DEFINER</code> security context is ignored, if the <code>INVOKER</code> does not have the <code>EXECUTE</code> or <code>UPDATE</code> privilege the procedure will fail.
 
What <code>SQL SECURITY</code> does is restrict users access to tables directly, whilst allowing access to certain data to perform their required functions. This can help support an organisation to meet the security concept of 'principle of least privilege' (POLP) and help to secure sensitive or customer data.
 
In SQL the POLP extends to:

- Read-access to data
- Creating user accounts
- Changing table structure
 
<h3>Procedures and Stored Procedures</h3>
 
Procedures or stored procedures are SQL queries that are created once and stored in the database to be executed multiple times when required by a database user by calling the procedure. Stored procedures result in reduced execution time.

<code> 
delimiter //<br>
DROP PROCEDURE IF EXISTS SelectTileBoard;<br>
CREATE PROCEDURE SelectTileBoard( pTileID int )<br>
BEGIN<br>
  SELECT BoardType AS 'Board Description', TileID AS 'Tile Ref'<br>
  FROM tblBoardTile<br>
  WHERE TileID = pTileID;<br>
END;<br>
//<br>
</code>
 
Stored procedures can accept parameters as an input, such as those defined in the above example. Multiple values can be returned as an output parameter by calling the procedure.

<i>References</i>

Access Control in MySQL Stored Routines: DEFINER, INVOKER & SQL SECURITY - ..::CHANGE is INEVITABLE::.. (2012, January 30). [https://kedar.nitty-witty.com/blog/access-control-in-mysql-stored-routines-by-example-definer-invoker-sql-security](https://kedar.nitty-witty.com/blog/access-control-in-mysql-stored-routines-by-example-definer-invoker-sql-security)

Deterministic and Nondeterministic Functions—SQL in a Nutshell, 3rd Edition [Book]. (n.d.). Retrieved April 13, 2021, from [https://www.oreilly.com/library/view/sql-in-a/9780596155322/ch04s01s01.html](https://www.oreilly.com/library/view/sql-in-a/9780596155322/ch04s01s01.html)

rothja. (n.d.). Deterministic and Nondeterministic Functions—SQL Server. Retrieved April 13, 2021, from [https://docs.microsoft.com/en-us/sql/relational-databases/user-defined-functions/deterministic-and-nondeterministic-functions](https://docs.microsoft.com/en-us/sql/relational-databases/user-defined-functions/deterministic-and-nondeterministic-functions)

Is `definer` required when creating a MySQL stored procedure? (n.d.). Retrieved April 12, 2021, from [https://www.tutorialspoint.com/is-definer-required-when-creating-a-mysql-stored-procedure](https://www.tutorialspoint.com/is-definer-required-when-creating-a-mysql-stored-procedure)

MySQL :: MySQL 8.0 Reference Manual: 25.6 Stored Object Access Control. (n.d.). Retrieved April 12, 2021, from [https://dev.mysql.com/doc/refman/8.0/en/stored-objects-security.html](https://dev.mysql.com/doc/refman/8.0/en/stored-objects-security.html)

Security: The Principle of Least Privilege (POLP). (2021, February 3). TECHCOMMUNITY.MICROSOFT.COM. [https://techcommunity.microsoft.com/t5/azure-sql/security-the-principle-of-least-privilege-polp/ba-p/2067390](https://techcommunity.microsoft.com/t5/azure-sql/security-the-principle-of-least-privilege-polp/ba-p/2067390)

stored procedures—Mysql CREATE DEFINER. (n.d.). Stack Overflow. Retrieved April 12, 2021, from [https://stackoverflow.com/questions/16594860/mysql-create-definer](https://stackoverflow.com/questions/16594860/mysql-create-definer)

What is Procedure in SQL? - Structure to create procedure with Example. (2019, May 9). EDUCBA. https://www.educba.com/what-is-procedure-in-sql/