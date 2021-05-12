---
layout: post
title:  "Journal #Eleven [DAT602] - ACID" 
author: Dale Stephenson
categories: [ DAT602, Journal, Database Application Development ]
image: assets/images/DAT602-J11.jpeg
featured: true
hidden: true
---
<i>ACID</i>

JOURNAL #ELEVEN [DAT602]

<h2>ACID</h2>
 
ACID is an important database design model that describes four separate aims that database management systems should incorporate to guarantee the reliability of transactions processed. To this end, the ACID model concerns itself with how a database can recover from a failure that occurs whilst processing a given transaction, maintaining accuracy and consistency despite the failure.
 
ACID provides a mechanism that seeks to provide for the correctness of a database. It does this by ensuring that transactions group operations into a single procedural unit to produce results that are consistent and act in isolation from other updates or operations. The principles of ACID are adhered to by all major relational database management systems including InnoDB as part of MySQL, with features that support the four aims.
 
The four aims of ACID that form the acronym stand for:
 
- Atomicity
- Consistency
- Isolation
- Durability
 
<h2>Transaction Isolation</h2>
 
Transaction isolation is an essential part of database processing, being the "I" in the ACID model. Transaction isolation is an important consideration for database development, choosing the appropriate level for the database ensures that users and stakeholder gain the right balance between the performance and reliability, consistency and reproducibility of outputs from the system. The importance of the decision-making process becomes more apparent when multiple transactions are implementing changes in the database and multiple queries are being performed simultaneously.
 
The four transaction levels have been described in [Journal Ten](https://d-stephenson.github.io/dat602/journal/database%20application%20development/2021/04/30/journal-ten-dat602.html) and consist of:
 
- REPEATABLE READ
- READ COMMITTED 
- READ UNCOMMITTED
- SERIALIZABLE
 
The database in development as part of this course has been updated from 'repeatable read', to 'read committed'. This decision has been made due to the balance trade-off for the type of multi-player role-based game and the benefits of the level as follows.
 
<h3>Consistent Nonlocking Reads</h3>
 
A consistent read presents a query snapshot of the database at a specific point in time, meaning that any transaction that has committed changes to the database before the specific point in time is returned. Changes contained within uncommitted transactions are not returned in the query.
 
Furthermore, unlike the default InnoDB setting 'repeatable read' where consistent reads contained in the same transaction, read the snapshot that is established by the first read, 'read committed' sets and reads a fresh snapshot for each consistent read in the transaction.
 
<h3>Locking Reads</h3>
 
Locking reads include:
 
- SELECT with FOR UPDATE or LOCK IN SHARE MODE
- UPDATE statements
- DELETE statements
 
For these instances only index records are locked, this allows for new records to be inserted next to locked records. With UPDATE and DELETE statements 'read committed' holds locks for the rows that are being updated or deleted, rows that are not included in the statement are released after the WHERE condition has been evaluated. This is important for reducing the chance of deadlocks occurring, but it doesn't entirely eliminate them.
 
If a row is locked and forms part of an UPDATE statement, a 'semi-consistent' read is performed in InnoDB. In these cases, the latest committed version is returned and the row is checked to determine if it matched the WHERE condition. If the match is confirmed then the row is read again and locked, or MySQL waits for it to be locked.
 
<h2>Transaction Activity</h2>
 
Activity performed on the database by its users occurs inside the transactions. This activity takes the form of:
 
- autocommit
- Commit
- Rollback
 
Where a database has 'autocommit' enabled all statements will form separate, single transactions. autocommit is enabled by default when each session is started, which means that each statement is committed unless an error is found, at which point the statement may be rolled back.
 
With autocommit enabled on a session, multiple-statement transactions can be performed. These transactions can be created with the following syntax:
 
// Start the transaction
START TRANSACTION or BEGIN
 
// End the transaction
COMMIT or ROLLBACK
 
When commit or rollback is used to end a transaction, a new transaction can then be started. If autocommit is disabled on a session and the transaction does not end with COMMIT, ROLLBACK will be performed on the transaction.
 
COMMIT makes the changes made in a transaction permanent and available to other sessions
ROLLBACK cancels any modifications made in a transaction
 
All of the locks that are set in a transaction are released when COMMIT or ROLLBACK are run at the end of the transaction.

<i>References</i>

MySQL :: MySQL 5.7 Reference Manual: 14.7.2.1 Transaction Isolation Levels. (n.d.). Retrieved May 12, 2021, from [https://dev.mysql.com/doc/refman/5.7/en/innodb-transaction-isolation-levels.html](https://dev.mysql.com/doc/refman/5.7/en/innodb-transaction-isolation-levels.html)

MySQL :: MySQL 8.0 Reference Manual: 15.7.2.2 autocommit, Commit, and Rollback. (n.d.). Retrieved May 12, 2021, from [https://dev.mysql.com/doc/refman/8.0/en/innodb-autocommit-commit-rollback.html](https://dev.mysql.com/doc/refman/8.0/en/innodb-autocommit-commit-rollback.html)

MySQL :: MySQL 8.0 Reference Manual: 15.7.2.3 Consistent Nonlocking Reads. (n.d.). Retrieved May 12, 2021, from [https://dev.mysql.com/doc/refman/8.0/en/innodb-consistent-read.html](https://dev.mysql.com/doc/refman/8.0/en/innodb-consistent-read.html)

sql server—Benefits of SET TRANSACTION ISOLATION LEVEL READ UNCOMMITTED. (n.d.). Database Administrators Stack Exchange. Retrieved May 12, 2021, from [https://dba.stackexchange.com/questions/106566/benefits-of-set-transaction-isolation-level-read-uncommitted](https://dba.stackexchange.com/questions/106566/benefits-of-set-transaction-isolation-level-read-uncommitted)