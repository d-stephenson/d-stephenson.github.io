---
layout: post
title:  "Journal #Nine [DAT601]"
author: d-stephenson
categories: [ DAT601, Journal, Database Design & Administration ]
image: assets/images/DAT9_joinEX2.png
featured: true
hidden: true
---
<i>SQL Server - Data Types and Joins</i>

JOURNAL #NINE [DAT601]

Learning Summary<br>

<b>Looking at Data Types and Joins in SQL Server</b>

Class sessions this week introduced us to data types and join tables in SQL Server. Microsoft Docs contains excellent documentation for review and testing within our test database.

<b><u>WHAT</u></b>

<u>Data Types</u>

In the relational database an attribute is defined by a data type. Data contained in the columns of the database can only hold data as defined by the data type.<br>

The data types that an attribute can be defined by are:

<img src="/assets/images/DAT9_datatypes.png" alt="Data Types"><br>

<u>Join Tables</u>

Join tables are a method used to join data from 2 or more tables. The logical relationships that exist between tables can be manipulated using conditions:

-	Selecting the specific columns from each table that need to be used in the join, typically a join will include the foreign key (FK) from one table and the associated key in the other table 
-	Using a logic operator such as =, <> to compare the values contained in the selected columns 

<u>Types of Joins</u>

Inner Joins – these can be specified in the FROM clause or the WHERE clause and return matching values in both tables

Outer Joins – These can only be specified in the FROM clause:
-	Left outer join – return records from the left table and those matched records from the right table
-	Right outer join - return records from the right table and those matched records from the left table
-	Full outer join – return all records where there is a match in both tables 

These types of joins are represented in the following chart:

<img src="/assets/images/DAT9_joins.png" alt="Join Types"><br>

Cross Joins – These joins work by joining each row from the first table with all the rows of the second table, if a WHERE clause is used then it functions like an inner join.<br>

The conditions used in the join work with the WHERE search condition and the HAVING search condition. These search conditions allow a database user to control the rows that are selected from the tables as defined in the FROM clause.<br>

When we specify the conditions of the join in the FROM clause, we are separating them from other search conditions in the WHERE clause. This can be seen in the following example applied in the test database in SQL Server:

<img src="/assets/images/DAT9_joinEX1.png" alt="Join Table Example"><br>

When we select columns for a join, we can choose all columns or identify a subset of the columns stored in the table to suit requirements.<br>

When using more then two tables in a join, a three table join for example, only one of the tables can be used to act as a bridge between the other two tables. The bridge table does not have to have any of its columns selected in the select list.

<u>Operators</u>

Operators allow database users with permissions to:

-	Temporality or permanently change data
-	Carry out searches on rows or columns based around a set of conditions
-	Use columns of data or expressions to implement decisions 
-	Use as a test before committing to a transaction or before executing code

The following operator categories are used in SQL Server:

<img src="/assets/images/DAT9_operators.png" alt="Join Table Example"><br>

<b><u>WHY</u></b>

Join operators are used to retrieve data from tables within a database. Join operators are considered as an easy way to read and understand the appropriate data and used an efficient way to for retrieving that data.<br>

Joins can be used instead of sub-queries and there are several advantages of join tables which include:

-	Execute faster, performance may not always be noticeable by the user
-	Multiple join types that can used to define the output 

<b><u>HOW</u></b>

We have been running these join queries in our test bed data within out SQL Server. Microsoft Docs has been useful in testing these join queries.<br> 

In the following example we have identified the database we want to pull the data from, then selected the data we want to retrieve using the SELECT clause and the AS clause the name the columns.<br> 

This is followed with the FROM clause which define the database, schema and table and joined it using JOIN to a second table through an ID and operator. Finally, we include an order condition which list last name and first name in ascending order by last name.<br>

<img src="/assets/images/DAT9_joinEX2.png" alt="Join Table Example"><br>