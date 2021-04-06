---
layout: post
title:  "Journal #Six [DAT602] - Transact-SQL (T-SQL)" 
author: Dale Stephenson
categories: [ DAT602, Journal, Database Application Development ]
image: assets/images/DAT602-J6.jpeg
featured: true
hidden: true
---
<i>Transact-SQL (T-SQL)</i>

JOURNAL #SIX [DAT602]

<h2>Transact-SQL (T-SQL)</h2>

<h3>WHAT</h3>

<h4>SQL Queries</h4>
 
Working with data requires queries to be called against the database, these can take the form of:
 
Select queries: The retrieval of information from the database that is displayed in a 'virtual' table<br>
Action queries: Requests activities on the database such as the creation of new tables<br>
Aggregate queries: Perform calculations against a determined set of values<br>
 
<h4>Select Queries</h4> 
 
Select queries retrieve rows or columns from tables within a database, the select statement can include the following clauses:
 
  <b>INTO</b> - Creates a new table and inserts the results of the query

  <b>FROM</b> - Can be used in SELECT, UPDATE and DELETE statements and specifies the table source

  <b>JOIN</b> - A join is used where a result is produced from two or more tables in the database, join types are:
- <b>INNER</b>: Returns all matching rows, discarding unmatched rows
- <b>FULL [OUTER}</b>: A row from either the right or left table not meeting the join condition is included in the result set
- <b>LEFT [OUTER]</b>: All rows from the left table not meeting the join condition is included in the result set  
- <b>RIGHT [OUTER]</b>: All rows from the right table not meeting the join condition is included in the result set  

<b>WHERE</b> - Used to define the search condition for the returned rows

<b>GROUP BY</b> - Groups rows with the same values into summary rows, can be used with aggregate functions such as COUNT, SUM, AVG

<b>HAVING</b> - Exclusive use in SELECT statements and specifies a search condition for a GROUP BY or aggregate

<b>DISTINCT</b> - Used to return only those values that are different, those that are not duplicated in a table

<b>OVER</b> - Defines a set of rows within a query result as specified by the user
 
<h4>Action Queries</h4> 
 
Action queries are used to make changes in a database, an action query can take the form of one of the following statements:
 
<b>CREATE</b> - Used to make tables in the database

<b>ALTER</b> - Modifies columns or constraints in a table

<b>INSERT</b> - Adds data into current table rows

<b>UPDATE</b> - Takes existing data in a table and changes it

<b>DELETE</b> - Deletes data contained in rows of a database

<b>DROP</b> - Deletes tables from a database
 
<h4>Aggregated Queries</h4>
 
Aggregate functions perform calculations on a set of values to return a single value, these types of functions ignore values that are NULL and are commonly used with the SELECT statement and GROUP BY clause.
 
An aggregate query can include the following clauses:
 
<b>AVG</b> - Used to return the average of a set of values in a group, ignoring NULL values

<b>COUNT</b> - Returns an <i>int</i> data type value representing the number of items found in a group

<b>GROUPING</b> - If the specified column expression is aggregated the statement returns '1', if not it returns '0'

<b>SUM</b> - Takes all the values in a column and returns the sum, can only be used in numerical columns

<b>MAX</b> - The maximum value in the expression is returned

<b>MIN</b> - The minimum value in the expression is returned
 
<h3>WHY</h3>
 
Learning SQL is important primarily because it is the most commonly used language in database design. This makes it a valuable skill to have for IT professionals, particularly as data has become the most valuable asset today, being an important part of the organisation's decision-making process.
 
The commonality of SQL makes it an incredibly sought-after skill by employees. SQL is a query language that applies to most database engines, meaning knowledge of the language allows professionals to work across any relational database.
 
<h3>HOW</h3>
 
There are, however, some differences between SQL depending on the application.  Microsoft SQL Server uses different keywords to MySQL or MariaDB for example, in SQL Server the IDENTITY keyword is used to automatically increase the value of an <i>int</i> column type, whereas the keyword in MySQL and MariaDB is AUTO_INCREMENT.
 
The following SQL is procedural transactions in SQL Server:

<center><img src="/assets/images/DAT602-DML1.png" alt="Data Manipulation Language"></center><br>
<center><img src="/assets/images/DAT602-DML2.png" alt="Data Manipulation Language"></center><br>
<center><img src="/assets/images/DAT602-DML3.png" alt="Data Manipulation Language"></center><br>
<center><img src="/assets/images/DAT602-DML4.png" alt="Data Manipulation Language"></center><br>
<center><img src="/assets/images/DAT602-DML5.png" alt="Data Manipulation Language"></center><br>

<i>References</i> 

cawrites. (n.d.). Aggregate Functions (Transact-SQL)—SQL Server. Retrieved April 6, 2021, from https://docs.microsoft.com/en-us/sql/t-sql/functions/aggregate-functions-transact-sql

JanbaskTraining. (2019, February 28). What Is SQL Queries? List Of All SQL Queries With Examples. JanbaskTraining. 
https://www.janbasktraining.com/blog/what-is-sql-queries

SQL GROUP BY Statement. (n.d.). Retrieved April 6, 2021, from https://www.w3schools.com/sql/sql_groupby.asp

VanMSFT. (n.d.-a). FROM clause plus JOIN, APPLY, PIVOT (T-SQL)—SQL Server. Retrieved April 6, 2021, from https://docs.microsoft.com/en-us/sql/t-sql/queries/from-transact-sql

VanMSFT. (n.d.-b). Queries—SQL Server. Retrieved April 6, 2021, from https://docs.microsoft.com/en-us/sql/t-sql/queries/queries

What is SQL and why is it important? - Quora. (n.d.). Retrieved April 6, 2021, from https://www.quora.com/What-is-SQL-and-why-is-it-important?share=1
