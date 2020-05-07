---
layout: post
title:  "Journal #Eight [DAT601]"
author: d-stephenson
categories: [ DAT601, Journal, Database Design & Administration ]
image: assets/images/sqlServer.png
featured: true
hidden: true
---
<i>SQL Server</i>

JOURNAL #EIGHT [DAT601]

Learning Summary<br>

<b>Getting started with SQL Server</b>

Class sessions focused on the setting up and testing of SQL Server in the virtual TALOS, VMWare environment.

The setup process was simple and straightforward to follow, in no small part to the excellent documentation provided. No issues were encountered personally during setup and the software performed as expected with the test output being generated as follows:

<img src="/assets/images/dat_output.png" alt="Class Dat SQL Server Output"><br>

It was incredibly useful performing the installation during a class session. Although the installation was simple, and the instructions clear I could envisage a scenario whereby options could be easily missed or accidentally added which could cause confusion. Given the class structure students were able to voice problems and get support with potential solutions.

<b><u>WHAT</u></b>

SQL Server is a full-featured relational database management system (RDBMS) developed by Microsoft. Originally introduced in 1989 Microsoft has released subsequent versions which include more advanced options in addition to improved security.

These improved features include:

-	Dynamic Management Views (DMV)
-	XML data type support
-	Full text search capability
-	Database mirroring 

As with many rival offerings such as Oracle Database and MySQL, SQL Server supports the standard SQL language known as ANSI SQL in addition to its own SQL implementation, T-SQL.

The main interface tool is SQL Server Management Studio (SSMS) and that is part of the installation package completed in this week’s class session.

SQL Server is made up of two main components, the database engine, and the SQL Server Operating System (SQLOS).

<u>Database Engine</u>

The Database engine consists of a relational engine, this engine allows the processing of queries. Additionally, there is the storage engine, it is here where database files, pages and indexes are managed. The storage engine retrieves the requested data from the storage systems based on the relational engines query input. 

The relational engine acts as the processor of the query in the relationship between the two. 

<u>SQLOS</u>

The SQL Server Operating System provides services to the database engine including I/O management, syncing, exception handling and memory.

<b><u>WHY</u></b>

There are many benefits to using Microsoft SQL Server over and above the obvious, which include optimising and maintaining server performance and having a system solution that has a track record or recoverability and availability.

1.	Relatively simple installation 
Installation is achieved via a setup wizard meaning any complexity is kept to a minimum, additional features can be installed later only if they are required. Necessary updates are detected and installed automatically which reduces maintenance costs.

2.	Improved security features 
SQL server uses Policy-Based Management that can detect non-compliant policies, meaning only those personnel that have been authorised are able to access the database. Security audits and events can also be automated for analysis and review.

3.	Performance upgrades
SQL Server features efficient permission management tools with built-in data compression and encryption. This means there is no requirement to modify programs to safely encrypt the data. When combined, these features improve data collection speeds.

<b><u>HOW</u></b>

To get the best out of a Microsoft SQL Server database, the following steps should be considered:

1.	Maintain an SQL Server environment that is standardised and consistent with coherent configurations to minimise complexity 

2.	Allocate a dedicate server for SQL Server, there should be no requirements to maintain other processes alongside the running o SQL Server

3.	Efficiently manage data files and logs by enabling AUTOGROW and turning AUTOSHRINK off

4.	Provide users with only required security permissions, implement the least privilege security principle

5.	Implement a back up system that has been tested and that performs back-ups on at least a daily basis, larger organisations and businesses often carry out multiple backups throughout the day
