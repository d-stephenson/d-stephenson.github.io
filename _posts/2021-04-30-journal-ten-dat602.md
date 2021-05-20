---
layout: post
title:  "Journal #Ten [DAT602] - Sub Queries, Cascades & Transaction Isolation"
author: Dale Stephenson
categories: [ DAT602, Journal, Database Application Development ]
image: assets/images/DAT602-J10.jpeg
featured: true
hidden: true
---
<i>Sub Queries, Cascades & Transaction Isolation</i>

JOURNAL #TEN [DAT602]

<h2>Sub Queries, Cascades & Transaction Isolation</h2>

<h3>Subquery</h3>
 
A subquery in MySQL is a query that is nested inside another query, subqueries can also be nested inside other subqueries, which when combined make complex queries in MySQL. Subqueries can be deployed in SELECT, INSERT, UPDATE and DELETE statements.
 
Subqueries are defined by parenthesis in MySQL and are also known as the inner queries, whilst the query that contains them is known as the outer query.
 
The following query has been created for the game database in development as part of the DAT602 course, it contains a subquery in the WHERE clause, which compares PlayerID's from the tblPlayer table where they are not contained in the tblPlay table.

<center><img src="/assets/images/DAT602-Subquery.png" alt="MySQL Subquery" width="950"></center><br>
 
Subqueries can be used with comparison operators such as <code>=</code>, <code><</code>, <code>></code> such as:<br>
<code>
…WHERE quantity = (SELECT MAX(quantity) FROM tblStock);
…WHERE > (SELECT AVG(quantity) FROM tblStock);
</code>
 
The FROM clause can also contain a subquery as follows:
<code>SELECT MAX(product) FROM (SELECT supplierA, COUNT(supplierA) AS product FROM tblProduct…</code>
 
<h3>Cascade</h3>
 
Deleting data in MySQL can be performed more efficiently by using the <code>DELETE CASCADE</code> referential action against foreign keys. What this does is delete data from all child tables as part of the data deletion in the parent table.
 
If we imagine an automotive database with two tables, tblMake and tblModel, each car make can have one or many models, but each model relates to just one car make. A car model wouldn’t exist without a make, for example, a Phantom car model is made by Rolls Royce, but Rolls Royce makes the Phantom, Ghost, Wraith, Dawn and Cullinan.
 
In this database design, when you delete a car make, you also want to delete the model rows that relate to that make. To delete all the child references on the foreign key we must use ON DELETE CASCADE in the model table as follows:<br>
<code> 
CREATE TABLE tblModel (<br>
    Model_Name Varchar(255) NOT NULL<br>
    Make_Name Varchar(255)<br>
    FOREIGN KEY (Make_Name)<br>
    REFERENCES tblMake (Make_Name)<br>
    ON DELETE CASCADE<br>
);<br>
</code>
 
If a delete statement was run on the tblMake table to delete the row where car make equals Rolls Royce, all the models that belong to the Rolls Royce brand will be deleted from the tblModel table as well. This is where the efficiencies are made when deleting data from a database.
 
<h3>Transaction Isolation</h3>
 
Transaction isolation is vital for database processing, without it the game development for this course could not be achieved. Isolation forms part of the ACID principle and allows multiple transactions to be performed, and to make changes to the database, at the same time. This principle and functionality mean a database is consistent and reliable when these procedures are processed.
 
Various transaction levels supported by MySQL:
 
<b>Repeatable Read: </b>Perform consistent reads within a transaction read, meaning select statements are consistent with each other. This is the default isolation level for InnoDB, which is being used for the local version of the game database development. In this isolation level changes made by other transactions are not taken into account.
 
<b>Read Committed: </b>This isolation level produces a separate snapshot for each consistent read, even when using the same transaction. This means that uncommitted changes are not visible to any other transaction that is being performed
 
<b>Read Uncommitted: </b>In this isolation level transactions can view data changes made by other transactions before they are committed. This is the lowest level of isolation available and can lead to the reading of data that never gets committed, leading to what is known as a 'dirty-read'.
 
<b>Serializable: </b>This isolation level will isolate transactions from one another, meaning one cannot impact another. One transaction must finish before another can be completed, these combined make this the strongest possible isolation level.

<i>References</i>

MySQL :: MySQL 8.0 Reference Manual: 15.7.2.1 Transaction Isolation Levels. (n.d.). Retrieved April 29, 2021, from [https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-isolation-levels.html](https://dev.mysql.com/doc/refman/8.0/en/innodb-transaction-isolation-levels.html)

MySQL ON DELETE CASCADE: Deleting Data from Related Tables Automatically. (n.d.). MySQL Tutorial. Retrieved April 29, 2021, from [https://www.mysqltutorial.org/mysql-on-delete-cascade/](https://www.mysqltutorial.org/mysql-on-delete-cascade/)

MySQL Subquery. (n.d.). MySQL Tutorial. Retrieved April 29, 2021, from [https://www.mysqltutorial.org/mysql-subquery/](https://www.mysqltutorial.org/mysql-subquery/)

R, K. P. (2018, June 22). Back to basics: Isolation Levels In MySQL. [https://mydbops.wordpress.com/2018/06/22/back-to-basics-isolation-levels-in-mysql/](https://mydbops.wordpress.com/2018/06/22/back-to-basics-isolation-levels-in-mysql/)
