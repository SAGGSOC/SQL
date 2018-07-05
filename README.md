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

#### Data Abstraction and Data Independence

Database systems comprise of complex data-structures. In order to make the system efficient in terms of retrieval of data, and reduce complexity in terms of usability of users, developers use abstraction i.e. hide irrelevant details from the users.

There are mainly 3 levels of data abstraction:
* Physical: This is the lowest level of data abstraction. It tells us how the data is actually stored in memory. The access methods like sequential or random access and file organisation methods like B+ trees, hashing used for the same. Usability, size of memory, and the number of times the records are factors which we need to know while designing the database.
Suppose we need to store the details of an employee. Blocks of storage and the amount of memory used for these purposes is kept hidden from the user.

* Logical: This level comprises of the information that is actually stored in the database in the form of tables. It also stores the relationship among the data entities in relatively simple structures. At this level, the information available to the user at the view level is unknown.
We can store the various attributes of an employee and relationships, e.g. with the manager can also be stored.

* View: This is the highest level of abstraction. Only a part of the actual database is viewed by the users. This level exists to ease the accessibility of the database by an individual user. Users view data in the form of rows and columns. Tables and relations are used to store data. Multiple views of the same database may exist. Users can just view the data and interact with the database, storage and implementation details are hidden from them.

### ER- Model
ER Model is used to model the logical view of the system from data perspective which consists of these components:

Entity, Entity Type, Entity Set –

* An Entity may be an object with a physical existence – a particular person, car, house, or employee – or it may be an object with a conceptual existence – a company, a job, or a university course.
* An Entity is an object of Entity Type and set of all entities is called as entity set. e.g.; E1 is an entity having Entity Type Student and set of all students is called Entity Set.

Attribute:
Attributes are the properties which define the entity type. For example, Roll_No, Name, DOB, Age, Address, Mobile_No are the attributes which defines entity type Student. In ER diagram, attribute is represented by an oval.

1. Key Attribute
The attribute which uniquely identifies each entity in the entity set is called key attribute.For example, Roll_No will be unique for each student. In ER diagram, key attribute is represented by an oval with underlying lines.

2. Composite Attribute
An attribute composed of many other attribute is called as composite attribute. For example, Address attribute of student Entity type consists of Street, City, State, and Country. In ER diagram, composite attribute is represented by an oval comprising of ovals.

3. Multivalued Attribute
An attribute consisting more than one value for a given entity. For example, Phone_No (can be more than one for a given student). In ER diagram, multivalued attribute is represented by double oval.

4. Derived Attribute
An attribute which can be derived from other attributes of the entity type is known as derived attribute. e.g.; Age (can be derived from DOB). In ER diagram, derived attribute is represented by dashed oval.

### Relational Algebra
Relational Algebra is procedural query language, which takes Relation as input and generate relation as output. Relational algebra mainly provides theoretical foundation for relational databases and SQL.

## Operators in Relational Algebra

# Projection (π)
Projection is used to project required column data from a relation.

      R              
  (A  B  C)    
  ----------
   1  2  4
   2  2  3
   3  2  3
   4  3  4
   
   π (BC) 
    B  C
    -----
    2  4
    2  3
    3  4
    
# Selection (σ)
Selection is used to select required tuples of the relations. 
for the above relation

σ (c>3)R

will select the tuples which have c more than 3

# Note: Selection operator only selects the required tuples but does not display them. For displaying, data projection operator is used. For the above selected tuples, to display we need to use projection also.

π (σ (c>3)R ) will show following tuples.

A  B  C
-------
1  2  4
4  3  4

## Union (U)
Union operation in relational algebra is same as union operation in set theory, only constraint is for union of two relation both relation must have same set of Attributes.

## Set Difference (-)
Set Difference in relational algebra is same set difference operation as in set theory with the constraint that both relation should have same set of attributes.

## Rename (ρ)
Rename is a unary operation used for renaming attributes of a relation.
ρ (a/b)R will rename the attribute ‘b’ of relation by ‘a’.

## Cross Product (X)
Cross product between two relations let say A and B, so cross product between A X B will results all the attributes of A followed by each attribute of B. Each record of A will pairs with every record of B.
 A                                  B
    (Name   Age  Sex )                (Id   Course)  
    ------------------                -------------
    Ram    14   M                      1     DS
    Sona   15   F                      2     DBMS
    kim    20   M

     A X B
  Name   Age   Sex   Id   Course
---------------------------------
  Ram    14    M      1    DS
  Ram    14    M      2    DBMS
  Sona   15    F      1    DS
  Sona   15    F      2    DBMS
  Kim    20    M      1    DS
  Kim    20    M      2    DBMS
  
### Natural Join (⋈)

Natural join is a binary operator. Natural join between two or more relations will result set of all combination of tuples where they have equal common attribute.

        Emp                              Dep
   (Name   Id   Dept_name )          (Dept_name   Manager)
   ------------------------          ---------------------    
     A     120    IT                    Sale     Y
     B     125    HR                    Prod     Z
     C     110    Sale                  IT       A
     D     111    IT                      


                      Emp X Dep

                      Name   Id   Dept_name   Manager
                      -------------------------------
                      A     120   IT          A 
                      C     110   Sale        Y
                      D     111   IT          A
                      
### Conditional Join

Conditional join works similar to natural join. In natural join, by default condition is equal between common attribute while in conditional join we can specify the any condition such as greater than, less than, not equal

        R                           S
  (ID   Sex   Marks)          (ID   Sex   Marks)
  ------------------          -------------------- 
   1   F   45                   10   M   20
   2   F   55                   11   M   22
   3   F   60                   12   M   59
 
Join between R And S with condition  R.marks >= S.marks

      R.ID   R.Sex   R.Marks   S.ID   S.Sex   S.Marks
      -----------------------------------------------
      1       F       45        10     M        20
      1       F       45        11     M        22
      2       F       55        10     M        20
      2       F       55        11     M        22
      3       F       60        10     M        20
      3       F       60        11     M        22
      3       F       60        12     M        59
      
      
