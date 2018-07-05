# SQL

###Introduction

* SQL is Structured Query Language, which is a programming language for storing, manipulating and retrieving data stored in a relational database.
* SQL is the standard language for Relational Database System. All the Relational Database Management Systems (RDMS) like MySQL, MS   Access, Oracle, Sybase, Informix, Postgres and SQL Server use SQL as their standard database language.

####SQL Process
* When a SQL command is executed in any RDBMS, the system determines the best way to carry out your command and SQL engine figures out how to interpret the task.
* Components like Query Dispatcher, Optimization Engines, Classic Query Engine, SQL Query Engine etc are involved in this process.

###SQL Commands
## DDL - Data Definition Language
DDL is short name of Data Definition Language, which deals with database schemas and descriptions, of how the data should reside in the database.
* CREATE - create a new table, view for a table or other object in the database
* ALTER - modifies an existing database object, such as a table
* DROP - deletes an entire table, a view of a table or other objects in the database
* TRUNCATE - remove all records from a table, including all spaces allocated for the records are removed
* COMMENT - add comments to the data dictionary
* RENAME - rename an object

## DML - Data Manipulation Language
DML is short name of Data Manipulation Language which deals with data manipulation and includes most common SQL statements such SELECT, INSERT, UPDATE, DELETE etc, and it is used to store, modify, retrieve, delete and update data in a database.

* SELECT - retrieves records from one or more tables
* INSERT - creates a record
* UPDATE - modifies records
* DELETE - deletes records
* MERGE - UPSERT operation (insert or update)
* CALL - call a PL/SQL or Java subprogram
* EXPLAIN PLAN - interpretation of the data access path
* LOCK TABLE - concurrency control

## DCL - Data Control Language
DCL is short name of Data Control Language which includes commands such as GRANT and mostly concerned with rights, permissions and other controls of the database system.

* GRANT (Grant privilige(s) to user)
* REVOKE (Remove granted privilige(s) from a user)

## TCL - Transaction Control Language
TCL is short name of Transaction Control Language which deals with a transaction within a database.

* COMMIT - commits a transaction
* ROLLBACK - rollback a transaction in case of any error occurs
* SAVEPOINT - to rollback the transaction making points within groups
* SET TRANSACTION - specify characteristics of the transaction

