---
layout: post
title:  "Journal #Eleven [DAT601]"
author: d-stephenson
categories: [ DAT601, Journal, Database Design & Administration ]
image: assets/images/check_constraint.jpg
featured: true
hidden: true
---
<i>SQL Server - Constraints</i>

JOURNAL #ELEVEN [DAT601]

Learning Summary<br>

Class activity has included setting up remote access to the SQL Server database in our client node, and an introduction to constraints and their implementation. 

The remote database access was set up mostly prior to class session and reviewed in class to resolve common issues that were affecting a lot of the class. Once these were resolved we were able to access the SQL Server database through the Microsoft Office application Access. Access is a familiar program that I have used in my career but also as the database tool in DAT502. 

The class session on Friday focussed on constraints and their practical implementation in SQL Server.

<b>Check Constraints</b>

The check constraint is utilised by database users to reduce the value range placed in a column, allowing only a certain value to the column.  The constraint is used to specify a value in a column that must specify a Boolean expression. 

The CHECK can be named the same way that a table is named by using the CONSTRAINT keyword e.g:

CONSTRAINT value_unit CHECK(unit_price > 0)

Check constraints can be used against more than one column for example a database user may need to use the constraint in order to check when a product is discounted, that the discounted price is always lower than the recommended retail price. 

Check constraints can be added to existing tables through an ALTER TABLE ADD CONSTRAINT statement. Check constraints can also be removed from tables using the DROP CONSTRAINT statement.

The below is an example of some of the practical application applied in class:

<img src="/assets/images/check_constraint.jpg" alt="Practice Check Constraint">
<br>

Separately, work has progressed well with milestone 2 and the logical diagram, I’m hoping to have it submission ready by the end of the long weekend so I can focus effectively on the physical development up the end of term.