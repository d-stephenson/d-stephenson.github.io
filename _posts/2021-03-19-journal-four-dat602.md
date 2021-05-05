---
layout: post
title:  "Journal #Four [DAT602] - CRUD Table" 
author: Dale Stephenson
categories: [ DAT602, Journal, Database Application Development ]
image: assets/images/DAT602-J4.jpeg
featured: true
hidden: true
---
<i>CRUD Table</i>

JOURNAL #FOUR [DAT602]

<h2>CRUD Table</h2>

Development work has continued on the game design with the creation and refinement of the CRUD table. Version control has been established to ensure changes to the ERD are reflected in the CRUD table, an iterative and incremental approach has been adopted for the game development and consequently changes to the CRUD table are expected as the game build proceeds. 

<h3>WHAT</h3>

Effective development of persistent storage applications requires four functions, these are create, retrieve, update and delete (CRUD). 

<b>CREATE:</b> The create function is used to create records in the database using INSERT, this adds a new row to a table and populates the columns within that row.  

<b>RETRIEVE:</b> The retrieve function can be viewed as a search function to retrieve specified information from the database, using SELECT, and can follow a set of customised criteria defined by the database user using FROM and WHERE.

<b>UPDATE:</b> The update function is used to modify specified data stored in the database using ALTER, for example, user information can change over time such as addresses or mobile telephone numbers.

<b>DELETE:</b> The delete function removes records from the database using DELETE. The delete function removes records from the database using DELETE. The decision to delete information should not be made lightly and some database administrators perform soft deletes that update the row status instead, depending on the circumstances this may be preferable to a hard delete with removes the record from the database entirely. 

<center><img src="/assets/images/DAT602_CRUD.png" alt="Game CRUD table"></center><br>

<h3>WHY</h3>

CRUD is used to identify the events inherent to relational databases and the applications that use them, such as MySQL, Microsoft SQL Server, MariaDB and Oracle. The concept of CRUD functions works extremely well with a relational database, operating over attribute rows or fields within the table, or tuple. 

<h3>HOW</h3>

The CRUD table has been developed as a product of the logical ERD, the entities and attributes have been lifted from the current logical diagram version. The business and functional requirement in conjunction with the storyboards have been used to create the events listed on the table. 

A detailed analysis is formed for each of the identified events:

- Login Check Credentials
- New User Registration
- Failed Login Account Lock
- Login Successful
- New Game
- Join Game
- Player Moves
- Player Finds Gem
- End Game
- Player Logout
- Enter Admin Screen
- Admin Kill Game
- Admin Add Player
- Admin Update Player
- Admin Remove Player

The CRUD table has been created in a spreadsheet as this makes it easier to update and change then it would otherwise be in a word table for example. 

<i>References</i> 

What is CRUD? Explaining CRUD Operations. (n.d.). Sumo Logic. Retrieved March 7, 2021, from [https://www.sumologic.com/glossary/crud/](https://www.sumologic.com/glossary/crud/)