# mysql-notes

## What is Database(DB)?
Basically, it's any collection of related information. In old days, we used to write down mobile numbers on a notebook. That notebook is a database, which stores data like recipent name and it's number. 

## What is Database Management Systems (DBMS)?
A softare program that help users perform CRUD(Create, Read, Update, Delete) operations and maintain a database. More feature includes:
- Maintain large amount of data or information in a grouped manner
- Handles security 
- Create backups
- Import or export data
- Concurrency 
- Interact with software applications.

DBMS is not a database, it's just helps devs to perform CRUD ops on database.

## Two Main Types of Database:

1. **Relationdal Databases or SQL databases**
2. **Non Relational Databases or No SQL databases** 


## Relationdal Databases or SQL databases 
Organizes data in tables(& tables has rows and columns) and has unique keys.
System that allows to do CRUD operations on Relational Databases are called RDBMS (R stands for relational).
Some RDBMS are mySql, postgreSQL, Oracle, mariaDB, etc.
  
All above RDMS uses SQL (Structured Query Language).  

### Structured Query Language
- Standardized Language for interaction with RDBMS
- Used to perform CRUD operations as well as administrative tasks.
- Used to define table & structures.
- SQL code is not always portable from one RDBMS to another.



## Database Queries
DB cQueries are requests that will be sent to DBMS to fetch some specific information. 
As DB strucures gets more & more complex, it becomes more & more difficult to get specific pieces of information.


#####Jargons:
1. Column - Vertical
2. Row - Horizontal
3. Primary Key - A unique attribute about a specific entry that can help in identifying the rest entries, either in a row or a column based on design. It also helps in differentiating two or more entries & hence, it should be unique.

| transaction_id | title       | amount | type    | tag      |
|----------------|-------------|--------|---------|----------|
| 1              | netflix     | 2499   | outflow | ott      |
| 2              | electricity | 1999   | outflow | bills    |
| 3              | ITC         | 2500   | inflow  | dividend |

In the above case, transaction_id should be the primary key.

4. Foreign Key - An attribute(not necessarily unique) that can help link two tables. A foreign key is basically the primary key of another table.

![image](https://user-images.githubusercontent.com/28825619/140561218-dcf6191f-b1ef-43e3-91c1-64ce412deb02.png)
  
A foreign key can also be used to relate the same table that has the foreign key.

![image](https://user-images.githubusercontent.com/28825619/140561976-8ae34a53-6621-488b-8470-4b8c1a027484.png)

5. Composite Key - Two columns that combine to make a primary key(a unique key).

![image](https://user-images.githubusercontent.com/28825619/140562495-b82ad3d4-75be-4414-9ea7-1ee9760213eb.png)

![image](https://user-images.githubusercontent.com/28825619/140562942-a4cb3175-b5f9-478b-9f31-d19cf3ee33bb.png)

---

## SQL Basics

SQL is a language (not a programming language) that can be used to communicate with RDBMS.

SQL implementations vary between systems.

SQL is a hybrid language. It's a package of 4 languages:
1. Data Query Language - Used to query database info & get information that's already stored.
2. Data Definition Language - Used for defining database schemas.
3. Data Control Language - Used for defining security rules.
4. Data Manipulation Language - Used for IUD(Inserting, Updating, Deleting) ops.

### Queries
In SQL, it's set of instruction given to RDBMS to retrieve data that you want to retrieve. 

### Core Datatypes in mySQL
1. INT (Integers)
2. DECIMAL(M,N) [M-> Total number of digits, N-> Post decimal digits]
3. VARCHAR(L) [L-> Length of characters it can store]
4. BLOB [Binary Large Object, used to store Large Data]  
5. DATE [YYYY-MM-DD]
6. TIMESTAMP [YYYY-MM-DD HH-MM-SS]

### Creating Database Tables

1. With Key
```sql
CREATE TABLE <table-name> (
  <column-name> <datatype> <key>,
);
```
Example:

```sql
CREATE TABLE students (
  student_id INT PRIMARY KEY,
  name VARCHAR(20),
  major VARCHAR(20),
);
```

2. Without Key
```sql
CREATE TABLE <table-name> (
  <column-name> <datatype>,
  <key>(<column-name>),
);
```
Example:

```sql
CREATE TABLE students (
  student_id INT,
  name VARCHAR(20),
  major VARCHAR(20),
  PRIMARY KEY(student_id),
);
```

Using semi-colon helps mySQL detect the line ending, hence it's neccessary to add one.

`CREATE TABLE` is the keyword that SQL uses to create a table.
It's not necessary to write `CREATE TABLE` in all caps, you can use in small caps too but convention says to do in all caps so as to differentiate SQL commands.

### Viewing Table

```sql
DESCRIBE <table-name>;
```

Example:

```sql
DESCRIBE students;
```

### Deleteting Table

```sql
DROP TABLE <table-name>;
```

Example:

```sql
DROP TABLE students;
```

### Modifying Table

```sql
ALTER TABLE <table-name> ADD <column-name> <datatype>;
```

Example:

```sql
ALTER TABLE students ADD gpa DECIMAL(3,2);
```

### Deleting Columns

```sql
ALTER TABLE <table-name> DROP COLUMN <column-name>;
```

Example:

```sql
ALTER TABLE students DROP COLUMN gpa;
```
