


 Day 1: Frontend, Backend, API and File System vs DBMS
A. Frontend (Client Side)
The visual and interactive layer of a website or application that users see and use in a browser or mobile app. It runs on the user's device.
Responsibilities
•	Displays web pages and the user interface (UI)
•	Accepts user input (forms, buttons, search boxes)
•	Validates input before sending it to the server
•	Calls backend APIs to fetch or send data
•	Displays the response received from the backend
•	Provides animations and interactive effects
•	Ensures responsive design for mobile, tablet and desktop
Common Frontend Technologies
Technology	Purpose
HTML	Structure of the webpage
CSS	Styling and layout
JavaScript	Interactivity and dynamic behavior
Bootstrap	Responsive UI framework
React.js	JavaScript library for building UI
Angular	Frontend framework
Vue.js	Progressive JavaScript framework
TypeScript	JavaScript with static typing

Examples: login page, registration form, shopping cart, dashboard, profile page, online payment page.
Real-time example (Login button): the frontend collects the username and password, sends them to the backend through an API, waits for the response, then shows either "Login Successful" or "Invalid Username/Password".
B. Backend (Server Side)
The server-side part of an application. Users cannot see it directly, but it performs business logic, security, data processing and database operations. It is the brain of the application.
Responsibilities
•	Processes client requests
•	Implements business logic
•	Connects with databases
•	Performs CRUD operations
•	Authenticates and authorizes users
•	Encrypts passwords and sensitive data
•	Generates reports
•	Sends emails and notifications
•	Handles file uploads and downloads
•	Returns responses to the frontend
Common Backend Technologies
Technology	Purpose
Java	Backend programming language
Spring Boot	Java framework
Node.js	JavaScript runtime
Python (Django/Flask)	Backend development
PHP	Web development
.NET	Microsoft backend framework
Go	High-performance backend
Ruby on Rails	Rapid web development

Databases used: MySQL, PostgreSQL, Oracle, SQL Server, MongoDB, Firebase.
Login flow in the backend: receive username/password, check the database, verify the password, generate a JWT token or session, send a success/failure response.
Online banking example: check balance, validate transaction, transfer money, update database, send SMS/email confirmation. All of this happens in the backend.
C. API (Application Programming Interface)
An API is a set of rules and protocols that allows two applications or systems to communicate and exchange data without exposing their internal implementation. In short: API = Communication Bridge.
Restaurant analogy: You (client) give your order to the Waiter (API), who passes it to the Kitchen (server). The Kitchen hands the food back to the Waiter, who brings it to you.
Type	Description	Example
REST API	Uses HTTP, most common	Weather app fetching data
SOAP API	XML-based, used in banking	Net banking transactions
GraphQL	Fetch only what you need	Facebook, GitHub
WebSocket API	Real-time, two-way	WhatsApp, live scores

Real-time scenario: MakeMyTrip does not own airline data. It calls the IndiGo, Air India (and other) APIs, each of which returns available seats and prices, and shows everything in one place.
D. Storage Areas
Applications need to store data such as customer, billing and call information. There are two types of storage areas.
Temporary storage: memory areas where data is stored temporarily. Example: JVM memory areas (Heap, Stack, Method Area, PC Registers, Native Method Stacks), which are cleared when the JVM shuts down.
Permanent (persistent) storage: data is stored permanently. Examples: file systems, databases, data warehouses, big data.
E. File Management System (FMS)
A system where data is stored in files on the operating system. Each application program must handle its own storage, retrieval and updating. File systems suit very small amounts of data (KB). Example: a library system storing books.txt and members.txt.
Limitations of FMS
1.	Data redundancy: the same data is stored in multiple files
2.	Data inconsistency: updates in one file may not reach another
3.	Poor data security: no proper access control
4.	Difficult retrieval: searching needs custom programs
5.	Integrity issues: no constraints (e.g. roll number uniqueness)
6.	Scalability issues: hard to manage as data grows
F. Database Management System (DBMS)
A DBMS is a collection of programs that enables users to create, manage and manipulate databases. It acts as an interface between the user and the database.
Advantages
•	Can store huge amounts of information
•	Query language support makes database operations easy
•	A username and password are required to access data, so data is secured
•	Data is stored in tables; normalization and constraints (Unique key, Primary key) prevent duplication and inconsistency
Difference between FMS and DBMS
#	File Management System	Database Management System
1	Data is stored in separate files.	Data is stored and managed in a database.
2	High data redundancy may occur.	Redundancy reduced through design and normalization.
3	Harder to maintain and update.	Easier to maintain and update using DBMS tools and queries.
4	Limited security and access control.	Authentication, authorization, roles and access control.
5	Concurrent access is hard to manage.	Multiple users can work simultaneously with concurrency control.
6	Relationships between files not managed.	Relationships via Primary Key and Foreign Key.
7	Backup and recovery are manual.	Built-in backup and recovery mechanisms.
8	Integrity is difficult to enforce.	Constraints and transactions maintain consistency and integrity.
9	Suitable for simple applications.	Suitable for small, medium and large applications.

Interview question: What is the difference between a File System and a DBMS?
A file system stores data in separate files and may lead to data redundancy and security issues. A DBMS stores data in a structured manner using tables, reduces redundancy, provides security, supports multiple users, and ensures data consistency and integrity.

 Day 2: Database Basics, SQL Identifiers, Commands and Data Types
Data, Field, Record, Database
Term	Definition	Example
Data	Raw facts or figures without context	101, Ravi, 50000, hyd
Field	Smallest unit of data in a database (column/attribute)	EmpName, EmpId, EmpSalary
Record	Collection of related fields (row/tuple)	(111, ravi, 60000, vjy)
Database	Organized collection of related records stored together	An employee database

Client-Server Architecture
Client: sends requests to the server and gets a response.
Server: software that takes requests from clients. For a valid request it generates a response and hands it to the client; for an invalid request it raises an error.
Protocol: a set of rules and regulations used to send requests from client to server.
SQL Identifiers
Identifiers are names used to identify database objects: databases, tables, columns, views, indexes, constraints, triggers and stored procedures. Rules from class:
1.	Allowed characters: a-z, A-Z, 0-9, _ and $
2.	Must begin with a letter or underscore (_)
3.	Cannot be a reserved keyword
4.	Spaces are not allowed
5.	Identifiers are case sensitive
6.	Maximum length of 15 characters (class guideline)
Note: In actual MySQL, identifiers can be up to 64 characters, and table-name case sensitivity depends on the operating system. The 15-character limit is a class guideline.
SQL Command Categories
Command	Description
DDL	Data Definition Language: defines and modifies structure of database objects (tables, schemas, indexes).
DML	Data Manipulation Language: manages data inside objects (insert, update, delete).
DQL	Data Query Language: fetches/retrieves data from the database.
DCL	Data Control Language: manages permissions and access control.
TCL	Transaction Control Language: manages transactions to maintain data integrity.

DDL Commands
DDL commands define, create, alter and remove the structure of database objects. Changes made by DDL commands are auto-committed and permanent.
Command	Description
CREATE	Creates a new object such as a table, database, view, index or schema.
ALTER	Modifies the structure of an existing object (add, delete or modify columns).
DROP	Permanently deletes an object along with its data and structure. Cannot be rolled back in most databases.
TRUNCATE	Removes all rows quickly while keeping the table structure. Faster than DELETE.
RENAME	Renames an existing object without changing its structure or data.
COMMENT	Adds explanatory notes to objects for documentation; does not affect data.

CREATE TABLE Students (ID INT, Name VARCHAR(50));
ALTER TABLE Students ADD Email VARCHAR(100);

Numeric Data Types
Data types define the kind of information each column can store. MySQL groups them into numeric, string, and date/time types.
Type	Signed range	Unsigned range
TINYINT	-128 to 127	0 to 255
SMALLINT	-32,768 to 32,767	0 to 65,535
MEDIUMINT	-8,388,608 to 8,388,607	0 to 16,777,215
INT / INTEGER	-2,147,483,648 to 2,147,483,647	0 to 4,294,967,295
BIGINT	-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807	0 to 18,446,744,073,709,551,615
FLOAT	Approx. -3.4E+38 to 3.4E+38 (single precision)	N/A
DOUBLE	Approx. -1.8E+308 to 1.8E+308 (double precision)	N/A
DECIMAL(M,D)	Exact fixed-point; M = total digits, D = digits after decimal. Used for financial data.	N/A

CREATE TABLE tinyint_example (age TINYINT);
INSERT INTO tinyint_example (age) VALUES (25);
 
CREATE TABLE decimal_example (price DECIMAL(10, 2));
INSERT INTO decimal_example (price) VALUES (1999.99);

First Practice: EMPLOYEES Table
SHOW DATABASES;
CREATE DATABASE PFS7;
USE PFS7;
 
CREATE TABLE EMPLOYEES(
    EMPID CHAR(5),
    FNAME VARCHAR(100),
    LNAME VARCHAR(30),
    AGE INT,
    DOJ DATE,
    ADDRESS TINYTEXT,
    DEPT VARCHAR(20)
);


 Day 3: String, Binary and Date/Time Data Types
String Data Types
Type	Description
CHAR(n)	Fixed length; pads with spaces to length n.
VARCHAR(n)	Variable length; storage-efficient. Max 65,535 bytes (UTF-8 characters may use more than 1 byte).
TEXT	Up to 65,535 characters; cannot have a default value; stored outside the row.
TINYTEXT	Up to 255 characters.
MEDIUMTEXT	Up to 16,777,215 characters.
LONGTEXT	Up to 4,294,967,295 characters.
ENUM	Predefined list of values; stores only one chosen value.
SET	Predefined list of values; can store multiple values.

CREATE TABLE example (code CHAR(5));
INSERT INTO example (code) VALUES ('AB'), ('ABCDE');
-- 'AB   ' (padded), 'ABCDE'
 
CREATE TABLE example2 (status ENUM('active', 'inactive', 'pending'));
CREATE TABLE example3 (permissions SET('read', 'write', 'execute'));
INSERT INTO example3 (permissions) VALUES ('read,write');

CHAR vs VARCHAR
Feature	CHAR(n)	VARCHAR(n)
Storage type	Fixed-length string	Variable-length string
Padding	Pads with spaces to length n	No padding
Storage size	Always n bytes	Actual length plus 1-2 bytes for length prefix
Performance	Slightly faster for fixed-length data	More efficient for varying-length data
Max length	255 characters	65,535 bytes (depends on row size and character set)

BINARY vs VARBINARY
Feature	BINARY(n)	VARBINARY(n)
Length	Fixed	Variable
Padding	Pads with \0 (null bytes)	No padding
Use case	Consistent-length binary data	Varying-length binary data
Similar to	CHAR(n)	VARCHAR(n)

DATE
Stores the date only, in the format YYYY-MM-DD (for example 2022-01-01). No time information.
CREATE TABLE Orders (
    OrderId INT,
    ProductName VARCHAR(255),
    OrderDate DATE
);
INSERT INTO Orders (OrderId, ProductName, OrderDate)
VALUES (1, 'Product 1', '2022-01-01');
 
SELECT * FROM Orders WHERE OrderDate = '2022-01-01';

Date Functions
Function	Purpose
CURDATE()	Returns the current date
DATE_ADD()	Adds an interval to a date
DATE_SUB()	Subtracts an interval from a date
DATEDIFF()	Difference between two dates

SELECT CURDATE();
SELECT DATE_ADD('2024-01-09', INTERVAL 3 MONTH);
SELECT DATE_SUB('2024-01-09', INTERVAL 3 MONTH);
SELECT DATEDIFF('2024-01-09', '2024-01-14');

Note: The interval unit is MONTH (singular), not MONTHS.
TIME
Stores hours, minutes and seconds in the format HH:MI:SS.
CREATE TABLE table_name (column_name TIME);
INSERT INTO table_name (column_name) VALUES ('17:34:20');
 
SELECT CURTIME();
SELECT ADDTIME('11:30:45', '15:30:45');
SELECT SUBTIME('11:30:45', '15:30:45');

TIMESTAMP
Stores both date and time (YYYY-MM-DD HH:MI:SS). Typically used to track updates and changes to a record.
CREATE TABLE table_name (
    column1 TIMESTAMP DEFAULT CURRENT_TIMESTAMP
                      ON UPDATE CURRENT_TIMESTAMP,
    column2 VARCHAR(100)
);

ON UPDATE CURRENT_TIMESTAMP automatically refreshes the column whenever another field in the row changes.

 Day 4: DDL - ALTER TABLE Operations
All operations below were performed on the EMPLOYEES table. Use DESC EMPLOYEES; after each step to verify the structure and SHOW TABLES; to list tables.
Task	Syntax	Example
Modify column	ALTER TABLE t MODIFY col TYPE(size);	ALTER TABLE EMPLOYEES MODIFY FNAME VARCHAR(70);
Add column	ALTER TABLE t ADD col TYPE;	ALTER TABLE EMPLOYEES ADD LOCATION TINYTEXT;
Add after a column	ALTER TABLE t ADD col TYPE AFTER existing;	ALTER TABLE EMPLOYEES ADD PFID INT AFTER ADDRESS;
Rename column	ALTER TABLE t CHANGE COLUMN old new TYPE(size);	ALTER TABLE EMPLOYEES CHANGE COLUMN FNAME FIRSTNAME VARCHAR(30);
Drop column	ALTER TABLE t DROP COLUMN col;	ALTER TABLE EMPLOYEES DROP COLUMN PFID;
Rename table	ALTER TABLE t RENAME TO new;	ALTER TABLE EMPLOYEES RENAME TO CODEGNAN_EMP;

ALTER TABLE EMPLOYEES MODIFY FNAME VARCHAR(70);
ALTER TABLE EMPLOYEES MODIFY LNAME VARCHAR(80);
ALTER TABLE EMPLOYEES ADD LOCATION TINYTEXT;
ALTER TABLE EMPLOYEES ADD PFID INT AFTER ADDRESS;
ALTER TABLE EMPLOYEES CHANGE COLUMN FNAME FIRSTNAME VARCHAR(30);
ALTER TABLE EMPLOYEES CHANGE COLUMN LNAME LASTNAME VARCHAR(30);
ALTER TABLE EMPLOYEES DROP COLUMN PFID;
ALTER TABLE EMPLOYEES DROP COLUMN LOCATION;
ALTER TABLE EMPLOYEES RENAME TO CODEGNAN_EMP;
ALTER TABLE CODEGNAN_EMP RENAME TO EMPLOYEES;

Common Errors Seen
•	ERROR 1146 (Table doesn't exist): wrong table name (EMPLOYEE instead of EMPLOYEES) or wrong database selected.
•	ERROR 1091 (Can't DROP): column name misspelled (PFI instead of PFID).
Assignment: company_staff Table
Create the table with the required datatypes, make emp_id the PRIMARY KEY, display the structure, and show all tables in the database.
Column	Datatype
emp_id	INT, PRIMARY KEY
age	TINYINT
experience	SMALLINT
gender	CHAR(1)
emp_name	VARCHAR(50)
address	TINYTEXT
salary	DECIMAL(10,2)
department	ENUM('HR','IT','Sales','Finance','Support')
skills	SET('Java','Python','SQL','Excel','Communication')
joining_date	DATE

CREATE TABLE company_staff (
    emp_id INT PRIMARY KEY,
    age TINYINT,
    experience SMALLINT,
    gender CHAR(1),
    emp_name VARCHAR(50),
    address TINYTEXT,
    salary DECIMAL(10,2),
    department ENUM('HR','IT','Sales','Finance','Support'),
    skills SET('Java','Python','SQL','Excel','Communication'),
    joining_date DATE
);
 
DESC company_staff;
SHOW TABLES;


 Day 5: DML - INSERT, UPDATE, DELETE, TRUNCATE, DROP
DML commands insert, update, delete and manage data inside existing tables. Unlike DDL, DML changes can typically be rolled back if not committed.
INSERT: Four Approaches
Approach 1: specify columns
INSERT INTO EMPLOYEES(EMPID,FIRSTNAME,LASTNAME,AGE,DOJ,ADDRESS,DEPT)
VALUES ('E001','MALLI','ARJUN',27,'2024-03-20','HYD','JAVA');
 
-- Multiple rows in one statement
INSERT INTO EMPLOYEES(EMPID,FIRSTNAME,LASTNAME,AGE,DOJ,ADDRESS,DEPT)
VALUES
('E002','ARJUN','SARKAR',37,'2022-02-20','VJY','SALES'),
('E003','SAI','VARDAN',22,'2024-03-18','HYD','PYTHON');

Approach 2: without column list
INSERT INTO EMPLOYEES VALUES
('E004','SUMA','SRI',24,'2025-10-10','BNG','DEVELOPMENT');

Approach 3: only particular columns (others become NULL)
INSERT INTO EMPLOYEES(FIRSTNAME,DOJ,LASTNAME,EMPID,ADDRESS)
VALUES ('SAI','2017-07-07','RAM','E008','VIJAYAWADA');

Approach 4: SET syntax
INSERT INTO EMPLOYEES
SET EMPID='E010', FIRSTNAME='SUDHEER', LASTNAME='KUMAR',
    AGE=45, DOJ='2024-06-01', ADDRESS='KOLKATTA', DEPT='DEVELOPMENT';

UPDATE
Syntax: UPDATE table SET column=value WHERE condition;
UPDATE EMPLOYEES SET LASTNAME='KUMAR' WHERE FIRSTNAME='ARUN';
UPDATE EMPLOYEES SET AGE=47 WHERE EMPID='E008';
UPDATE EMPLOYEES SET DEPT='IT' WHERE ADDRESS='VIJAYAWADA';
UPDATE EMPLOYEES SET DOJ='2026-06-27' WHERE EMPID='E009';

Note: Always use a WHERE clause; without it, every row is updated.
DELETE
DELETE FROM EMPLOYEES WHERE EMPID='E010';
DELETE FROM EMPLOYEES WHERE FIRSTNAME='SAI';

TRUNCATE and DROP
TRUNCATE TABLE EMPLOYEES;  -- removes all rows, keeps structure
DROP TABLE EMPLOYEES;      -- removes structure and data

Transactions: DELETE with Rollback
START TRANSACTION;
DELETE FROM employees WHERE department = 'Sales';
SELECT * FROM employees;   -- Sales rows are gone (not yet committed)
ROLLBACK;                  -- undo the DELETE
SELECT * FROM employees;   -- rows restored

Use COMMIT instead of ROLLBACK to make the change permanent. In MySQL, TRUNCATE and DROP are DDL commands, so they are auto-committed and cannot be rolled back.
DROP vs DELETE vs TRUNCATE
Aspect	DROP	DELETE	TRUNCATE
Removes	Table structure + data	Specific rows (WHERE)	All rows
Table structure	Removed	Intact	Intact
Speed	Fast (whole object)	Slower (row by row)	Fast (bulk)
Rollback (MySQL)	No	Yes (in a transaction)	No (auto-commit)
Auto-increment reset	N/A	No	Yes
Command type	DDL	DML	DDL


 Day 6: DCL - GRANT / REVOKE and Table Utilities
Data Control Language (DCL)
DCL commands grant and take back authority from database users.
GRANT <privileges> ON <object> TO <username>;
REVOKE <privileges> ON <object> FROM <username>;
 
GRANT SELECT, UPDATE ON MY_TABLE TO SOME_USER, ANOTHER_USER;
REVOKE SELECT, UPDATE ON MY_TABLE FROM USER1, USER2;

Here the privilege is a statement such as INSERT, DELETE, UPDATE or SELECT, and the object is a table, view, etc.
Demo: Users and Privileges
USE codegnan;
CREATE TABLE students (name VARCHAR(20), age INT, mobile VARCHAR(12));
INSERT INTO students VALUES ('student 1', 23, '9182454984');
 
CREATE USER user1 IDENTIFIED BY 'user1';
GRANT SELECT, INSERT, UPDATE ON students TO user1;
 
CREATE USER user2 IDENTIFIED BY 'user2';
GRANT SELECT, UPDATE ON students TO user2;

User	Privileges granted	Allowed	Denied
user1	SELECT, INSERT, UPDATE	SELECT, INSERT, UPDATE	DELETE, DROP
user2	SELECT, UPDATE	SELECT, UPDATE	INSERT, DROP

To log in as a user from the command line: mysql -u user1 -p, then USE codegnan;. A denied action returns ERROR 1142 (command denied to user).
REVOKE
REVOKE UPDATE ON students FROM user2;
-- user2 now gets: ERROR 1142: UPDATE command denied

Table Utilities
AUTO_INCREMENT primary key
CREATE TABLE EMPLOYEES(
    EMPID INT AUTO_INCREMENT PRIMARY KEY,
    NAME VARCHAR(100),
    DEPARTMENT VARCHAR(50)
);
INSERT INTO EMPLOYEES(NAME,DEPARTMENT) VALUES ('MALLI','IT'),('INDU','HR');

Backup using CREATE TABLE ... AS SELECT
CREATE TABLE BACKUPEMPLOYEES AS SELECT * FROM EMPLOYEES;

Note: This copies columns and data, but not keys, auto-increment or indexes (the PRIMARY KEY is missing in DESC BACKUPEMPLOYEES).
Generated (computed) columns
CREATE TABLE PRODUCTS(
    PRODUCTID INT PRIMARY KEY,
    PRICE DECIMAL(10,2),
    QUANTITY INT,
    TOTALAMOUNT DECIMAL(10,2) GENERATED ALWAYS AS (PRICE*QUANTITY) STORED
);
INSERT INTO PRODUCTS(PRODUCTID,PRICE,QUANTITY) VALUES (1,50,3),(2,100.25,6);
UPDATE PRODUCTS SET PRICE=500 WHERE PRODUCTID=1;
-- TOTALAMOUNT for product 1 recalculates to 1500.00


 Quick Reference
Category	Commands covered
DDL	CREATE, ALTER, DROP, TRUNCATE, RENAME, COMMENT
DML	INSERT, UPDATE, DELETE
DQL	SELECT
DCL	GRANT, REVOKE
TCL	START TRANSACTION, COMMIT, ROLLBACK

How to Use These Notes
1.	Install MySQL Server 8.0 or later and a client (MySQL CLI or Workbench).
2.	Open each day's section and run the SQL examples in order.
3.	Use DESC <table>; and SELECT * FROM <table>; to verify results after each step.
4.	Attempt the Day 4 assignment before checking the solution.
