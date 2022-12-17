# Relational Database

- [My MySQL playlist](https://www.youtube.com/playlist?list=PLgH5QX0i9K3qLcx9DvVDWmNJ7riPvxzCD)

## 1. introduction to Database

### Some important terms

- Data: unorganized & meaningless facts are known as data. example - anis, 101, 3.45, name, gpa, roll
- Information: organized, process & meaningful facts are known as Information.

- Database: Collection of related Data table or files. Example: college db can have student, teacher table etc.

### Advantages & Disadvantages of Database

- Advantages: faster presentation, easily accessible, update is easy, easily storable
- Disadvantage: security issue, required skill to handle database

## 2. Types of Database

- Simple database vs Relational database
- 3 important elements of RD: field=col, key-field, record=row, value
- field vs record

## 3. Types of Key

- Primary key: unique key. in a table you will have one primary key.
- foreign key: one table's primary key - same other's table general key(foreign key). It is used to make relation between tables. In one table there can be multiple foreign keys.
- composite key: when you need to use 2 or more keys to identify a record
- Priamry key vs Foreign key

## 4. DBMS & DBMS

## 5. Database Relations

- one-to-one (one record with another table's one record)
- one-to-many (one record with another table's many records)
- many-to-many (many records with another table's many records)

## 6. Sorting vs Indexing

## 7. Database security

- Encryption

## 8. Query

- Select Query - query based on column or field
- Unmatched Query
- CrossTab Query
- Action Query
- Query Language: QUEL, QBE, SQL (Structured Query Language)
- Features of SQL
  - Statements are not case sensitive (SELECT / select)
  - every statement mustbe end with semicolon
- SQL Statements types
  - DML (DATA MANIPULATION LANGUAGE): CRUD - SELECT, INSERT, UPDATE, DELETE
  - DDL (DATA DEFINITION LANGUAGE): CREATE, ALTER, DROP

## 9. SQL

- DBMS - XAMPP (Cross platform Apache, MySQL, PHP Perl)

## 10. DDL (Data Definition Language)

- SHOW DATABASE;
- CREATE DATABASE college;
- DROP DATABASE college;
- CREATE, DROP, SHOW DATABASE

## 11. Data Type

- Number - SMALLINT, INT, BIGINT, FLOAT, DOUBLE(M,D), DECIMAL(M,D)
- Characters - CHAR(M) will take memory for whatever size defined, VARCHAR(M) will take memory for only whatever characters you have used, TEXT
- DATE(YYYY-MM-DD), YEAR(YYYY), TIME(HH:MM:SS)
- BLOB(BINARY LARGE OBJECT) - image, audio, video
- LOGICAL - true/false

## 12.CREATE, DROP, RENAME TABLE

- syntax for creating table

```sql
CREATE TABLE table_name(
  col_name1 data_type(size),
  col_name2 data_type(size),
  PRIMARY KEY(col_name)
  ...
  );
```

- RENAME TABLE old_table_name TO new_table_name;
- DROP TABLE table_name;

## 13. INSERT RECORDS

- syntax for inserting records

```sql
-- for instering one record
INSERT INTO TABLE_NAME(COL1,COL2,...COLN)
VALUES
(VAL1, VAL2, ...VALN);

-- for instering one record with shortcut
INSERT INTO TABLE_NAME
VALUES
(VAL1, VAL2, ...VALN);

-- for instering multiple records
INSERT INTO TABLE_NAME
VALUES
(VAL1, VAL2, ...VALN),
(VAL1, VAL2, ...VALN),
....
(VAL1, VAL2, ...VALN);
```

## 13. FIND / SELECT RECORDS

- syntax for selecting records

```sql
-- find all records with specific fields/columns
SELECT COL1,COL2,...COLN
FROM table_name
-- find all records with all the fields/columns
SELECT *
FROM table_name;
```

## 14. DISTINCT, LIMIT, ORDER BY

- distinct command for avoiding repeated values, limit can return limited records

```sql
SELECT DISTINCT COL1,COL2,...COLN
FROM table_name
LIMIT 5;

SELECT DISTINCT COL1,COL2,...COLN
FROM table_name
-- (start from record 3, how many records you want )
LIMIT 2,5;

-- ORDER BY helps us to sort
SELECT COL1,COL2,...COLN
FROM table_name
ORDER BY COL1, COL2,...COLN;

-- for descending ORDER BY helps us to sort
SELECT COL1,COL2,...COLN
FROM table_name
ORDER BY COL1, COL2,...COLN DESC ;
```

## 15. Operators

- Arithmetic operators: + - \* / %
- Comparision or Relational operators > >= < <= = != BETWEEN
- Logical operators: AND OR NOT IN

## 16. WHERE Clause

- where clause allows us to find records conditionally

```sql
SELECT COL1,COL2,...COLN
FROM table_name
WHERE codition;

example
SELECT Name
FROM students
WHERE city='Tampere';
```

## 16. RELATIONAL OPERTAORS IN SQL

- BETWEEN

```sql
SELECT COL1,COL2,...COLN
FROM table_name
WHERE COL BETWEEN START_VALUE AND END_VALUE;

example
SELECT ID, NAME, GPA
FROM students
WHERE ID BETWEEN 101 AND 105;
```

## 17. LOGICAL OPERTAORS IN SQL

- OR, AND, NOT, IN, LIKE

```sql
SELECT COL1,COL2,...COLN
FROM table_name
WHERE FIELD_NAME=VALUE OR FIELD_NAME=VALUE ...;

SELECT COL1,COL2,...COLN
FROM table_name
WHERE FIELD_NAME=VALUE AND FIELD_NAME=VALUE ...;

SELECT *
FROM students
WHERE city='Tampere'
  OR city='Helsinki'
  OR city='Oulu'

SELECT *
FROM students
WHERE city IN ('Tampere','Helsinki','Oulu');

SELECT *
FROM students
WHERE city NOT IN ('Tampere','Helsinki','Oulu');

-- like helps to search based on a pattern
SELECT *
FROM students;
-- find anyone name starts with s
WHERE name LIKE '%s';
-- find anyone name ends with s
WHERE name LIKE '%s';
-- find anyone name contains hi
WHERE name LIKE '%hi%';
```

## 18. Custom name with AS Keyword

```sql
SELECT COL1 AS 'CUSTOM_NAME'
FROM table_name;


example1
SELECT Roll as 'student_id'
FROM students;

example1
SELECT Roll as id
FROM students;
```

## 19. Constraint and AUTO_INCREMENT

- When creating table we can set constraint and auto increment
- Constraints: NOT NULL, UNIQUE, PRIMARY KEY = NOT NULL + UNIQUE, DEFAULT

```sql
CREATE TABLE TABLE_NAME N(
  ID int NOT NULL AUTO_INCREMENT,
  Name NOT NULL,
)

```

## 20. UPDATE STATEMENT

```sql
UPDATE table_name
SET COL1=VAL1, COL2=VAL2, ...COLN=VALN
WHERE condition;

example1
UPDATE techers
SET salary=20000
WHERE ID=102;

example2
UPDATE techers
SET salary=salary+20000
WHERE salary>=10000;
```

## 20. DELETE STATEMENT

```sql
DELETE FROM table_name
WHERE condition;

example
DELETE FROM techers
WHERE ID=102;
```
