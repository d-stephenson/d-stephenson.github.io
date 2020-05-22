---
layout: post
title:  "Journal #Ten [DAT601]"
author: d-stephenson
categories: [ DAT601, Journal, Database Design & Administration ]
image: assets/images/SQL1.png
featured: true
hidden: true
---
<i>SQL Server - Clauses and Subqueries</i>

JOURNAL #TEN [DAT601]

Learning Summary<br>

<b>Clauses and Subqueries</b>

Class sessions have revolved around looking at the application of clause to queries in SQL server and discussion the use of subqueries. After class tasks included the adaptation of MySQL queries with a few to making them function in SQL Server. 

I have included a selection of these completed tasks at the end of this journal.

<b><u>WHAT</u></b>

<u>SELECT DISTINCT</u>

The select distinct clause can be used to return only those values that are distinct from any other value.

An example of applying a DISTINCT clause to a SELECT statement would be to select ‘DepartmentID’ from an Employees table, it wouldn’t be much use having each DepartmentID listed in the query multiple times. So by applying DISTINCT we only return one instance of each DepartmentID. 

<u>SELECT ORDER BY</u>

The select order by clause allow a database user to sort the data that is being returned by a query. 

What the order by clause does is to allow us to order the result set of the query by the column list that has been specified. A user is able to use the clause to limit the rows that are returned in the query to a range specified by the query. 

The clause will, by default return the results in ascending order, but can return the results in descending order if specified. 

ORDER BY can be used in the following examples: 

- by a numeric ID, such as ProductID, OrderID etc.
- by a column not detailed in the SELECT list, such as ListPrice of a product where only ProductID is specified
- by an alias of a specified column such as PURCHASE_ORDER_No(OrderID) AS ‘Purchase Order No’
- sort the column by specifying an expression, such as the year employees joined the business
- ascending and descending together, such as FirstName(desc) LastName(asc)

<u>SELECT HAVING</u>

The having clause is used exclusively with the SELECT statement and most often with the GROUP BY clause.

The HAVING clause is best explained through the use of an example:

SELECT OrderID, SUM(LineTotal) As SubTotal
FROM SalesOrderData
GROUP BY OrderID
HAVING SUM(LineTotal) > 500.00
ORDER BY OrderID;

The above example is using the HAVING clause to retrieve only totals, for each OrderID that is greater then $500.00.

<u>Subqueries</u>

Subqueries are queries that are nested inside another query, or another subquery. Subqueries are always enclosed in parentheses. These queries can be:
- SELECT statements 
- INSERT statements 
- UPDATE statements 
- DELETE statements

A subquery is also known as an inner query and the statement containing it as the outer query. Subqueries can be used as an alternative to joins. 

A subquery that is nested inside a SELECT statement must include the following:
- SELECT query with the expected list components
- FROM clause with one or more table or view names

The subquery nested inside a SELECT statement may also include the following:
- WHERE clause
- GROUP BT clause
- HAVING clause
- ORDER BY clause only where a TOP clause is specified 

<b><u>WHY</u></b>

A database user can take advantage of the clauses and subqueries to better manage the data. Manipulating the data in this way provide valuable information to business users so they cam better understand their business and use it in the decision making process.

These types of queries are used across multiple departments in an organisation to improve data management, identify inconsistencies, make error corrections and identify opportunities to improve data input processes. 

<b><u>HOW</u></b>

Below are my examples of using queries to retrieve information from the example database in SQL Server:

<img src="/assets/images/SQL2.png" alt="Practice SQL">
<br>
<img src="/assets/images/SQL3.png" alt="Practice SQL">
<br>
<img src="/assets/images/SQL4.png" alt="Practice SQL">
<br>
<img src="/assets/images/SQL5.png" alt="Practice SQL">
<br>
<img src="/assets/images/SQL6.png" alt="Practice SQL">
<br>
<img src="/assets/images/SQL1.png" alt="Practice SQL">
<br>