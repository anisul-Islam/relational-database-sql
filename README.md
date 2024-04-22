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

- DBMS - XAMPP (Cross platform Apache, MySQL, PHP Perl)
- first download and install the DBMS - [PostgreSQL](https://www.postgresql.org/download/)
- after downloading check the version: `psql -version`
- type `psql` in the command line
- some common commands for Postgres: These are just a few examples of psql commands. You can find more commands and options by typing `\?` in the psql command-line interface to display the help menu.

1. **Connect to a Database**: Connect to a specific database.

   ```bash
   \c dbname
   ```

   Replace `dbname` with the name of the database you want to connect to.

2. **List Databases**: List all databases on the server.

   ```bash
   \l
   ```

3. **List Tables**: List all tables in the current database.

   ```bash
   \dt
   ```

4. **Describe Table**: Display the structure of a specific table.

   ```bash
   \d table_name
   ```

   Replace `table_name` with the name of the table you want to describe.

5. **Quit psql**: Exit the psql command-line interface.

   ```bash
   \q
   ```

6. **Execute SQL File**: Execute SQL commands from a file.

   ```bash
   \i path/to/file.sql
   ```

   Replace `path/to/file.sql` with the path to your SQL file.

7. **Toggle Expanded Display**: Toggle expanded display mode (shows long lines as multiple lines).

   ```bash
   \x
   ```

8. **Show Version**: Display the version of PostgreSQL.

   ```bash
   SELECT version();
   ```

   or

   ```bash
   SELECT version;
   ```

9. **List Roles**: List all roles (users) on the server.

   ```bash
   \du
   ```

10. **Change Password**: Change the password for the current user.

    ```bash
    \password
    ```

## 5. Database Relations

- one-to-one (one record with another table's one record)
- one-to-many (one record with another table's many records)
- many-to-many (many records with another table's many records)

## 6. Sorting vs Indexing

- Indexing: Indexing in a database is a technique used to optimize the retrieval of data by creating data structures, called indexes, that allow for faster lookup of records. Indexes are similar to the index of a book, which helps you quickly locate information within the book.

Here's how indexing works and its benefits:

1. **How Indexing Works**:
   - When you create an index on a column or set of columns in a database table, the database system creates a separate data structure that contains pointers to the actual rows in the table.
   - These pointers are organized in a way that allows the database engine to quickly locate the rows associated with a specific value or range of values in the indexed column(s).
   - When you query the database using a condition that matches the indexed column(s), the database engine first consults the index to find the corresponding rows, significantly reducing the time required to retrieve the data.

2. **Benefits of Indexing**:
   - Improved Query Performance: Indexes speed up data retrieval operations, especially for queries that involve filtering, sorting, or joining data based on indexed columns.
   - Faster Data Access: By reducing the number of disk I/O operations needed to locate data, indexes help minimize latency and improve overall system responsiveness.
   - Enhanced Concurrency: Indexes can also improve the concurrency of database operations by reducing the time it takes to acquire locks on data pages, allowing multiple transactions to access data simultaneously.
   - Efficient Sorting and Grouping: Indexes facilitate efficient sorting and grouping operations, making it easier to analyze and aggregate data.

3. **Types of Indexes**:
   - **Single-Column Index**: An index created on a single column.
   - **Composite Index**: An index created on multiple columns, allowing for efficient querying based on combinations of those columns.
   - **Unique Index**: Ensures that the indexed column(s) contain unique values, preventing duplicate entries.
   - **Clustered Index**: Defines the physical order of rows in the table based on the indexed column(s). Each table can have only one clustered index.
   - **Non-Clustered Index**: Stores the index data separately from the table data, allowing for faster retrieval but not affecting the physical order of rows in the table.

Indexing is a crucial aspect of database performance optimization. However, it's essential to strike a balance between the benefits of indexing and the overhead it imposes on data modification operations such as inserts, updates, and deletes. Over-indexing can lead to increased storage requirements and slower write operations, so it's essential to carefully consider the indexing strategy based on the specific requirements of your database application.

## 7. Database security

- Encryption

## 8. Query

A query in the context of databases refers to a request for data or information from a database table or combination of tables. It is essentially a command that is written in a structured query language (SQL) or a similar language to retrieve specific information from a database.

Here are some common types of queries:

1. **SELECT Query**: The most commonly used type of query, the SELECT query retrieves data from one or more tables based on specified criteria. It can be used to fetch entire rows, specific columns, or calculated values.

   Example:

   ```sql
   SELECT * FROM customers;
   ```

2. **INSERT Query**: This type of query is used to add new records (rows) to a table.

   Example:

   ```sql
   INSERT INTO customers (name, email) VALUES ('John Doe', 'john@example.com');
   ```

3. **UPDATE Query**: An UPDATE query is used to modify existing records in a table.

   Example:

   ```sql
   UPDATE products SET price = 20.99 WHERE id = 123;
   ```

4. **DELETE Query**: DELETE queries are used to remove records from a table based on specified conditions.

   Example:

   ```sql
   DELETE FROM orders WHERE order_date < '2023-01-01';
   ```

5. **JOIN Query**: JOIN queries are used to combine rows from two or more tables based on related columns between them.

   Example:

   ```sql
   SELECT orders.order_id, customers.name
   FROM orders
   JOIN customers ON orders.customer_id = customers.customer_id;
   ```

6. **CREATE Query**: CREATE queries are used to create new database objects such as tables, indexes, or views.

   Example:

   ```sql
   CREATE TABLE employees (
       id INT PRIMARY KEY,
       name VARCHAR(100),
       department VARCHAR(100)
   );
   ```

7. **ALTER Query**: ALTER queries are used to modify the structure of existing database objects such as tables, indexes, or views.

   Example:

   ```sql
   ALTER TABLE employees ADD COLUMN salary DECIMAL(10, 2);
   ```

8. **DROP Query**: DROP queries are used to remove database objects such as tables, indexes, or views from the database.

   Example:

   ```sql
   DROP TABLE employees;
   ```

- Query Language: QUEL, QBE, SQL (Structured Query Language)

## 9. SQL

- Features of SQL
  - Statements are not case sensitive (SELECT / select)
  - every statement mustbe end with semicolon
- SQL Statements types
  - DML (DATA MANIPULATION LANGUAGE): CRUD - SELECT, INSERT, UPDATE, DELETE
  - DDL (DATA DEFINITION LANGUAGE): CREATE, ALTER, DROP

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

- Create Database `CREATE DATABASE YourDatabaseName;` `CREATE DATABASE ecommerce`
- Drop Database `DROP DATABASE YourDatabaseName;`

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

### Ecommerce Plan

For an e-commerce application, you typically need CRUD operations for various entities such as users, products, orders, and categories. Here's an outline of the CRUD operations you might need for each entity:

1. **Users**:
   - Create: Register a new user.
   - Read: Retrieve user information by ID or username.
   - Update: Update user information (e.g., profile details, password).
   - Delete: Remove a user account.

2. **Products**:
   - Create: Add a new product to the catalog.
   - Read: Retrieve product information by ID, name, category, etc.
   - Update: Modify product details (e.g., name, price, description).
   - Delete: Remove a product from the catalog.

3. **Orders**:
   - Create: Place a new order for a user.
   - Read: Retrieve order information by ID, user, date, etc.
   - Update: Update order status (e.g., processing, shipped, delivered).
   - Delete: Cancel an order.

4. **Categories**:
   - Create: Create a new product category.
   - Read: Retrieve category information by ID or name.
   - Update: Modify category details (e.g., name, description).
   - Delete: Delete a category and optionally reassign products to another category.

These operations can be implemented using SQL queries or ORM (Object-Relational Mapping) frameworks depending on your technology stack. Additionally, you may need additional operations such as search, filtering, and pagination to enhance the functionality of your e-commerce application.

- here's an example of SQL commands to create tables for the entities mentioned:

    1. **Users**:

    ```sql
    <!-- for mysql  -->
    CREATE TABLE Users (
        UserID INT PRIMARY KEY AUTO_INCREMENT, (for mysql)
        Username VARCHAR(50) UNIQUE NOT NULL,
        Password VARCHAR(100) NOT NULL,
        Email VARCHAR(100) UNIQUE NOT NULL,
        FullName VARCHAR(100),
        Address VARCHAR(255),
        CreatedAt DATETIME DEFAULT CURRENT_TIMESTAMP
    );
    ```

    ```sql
    <!-- for psql -->
   CREATE TABLE Users (
    UserID SERIAL PRIMARY KEY,
    Username VARCHAR(50) UNIQUE NOT NULL,
    Password VARCHAR(100) NOT NULL,
    Email VARCHAR(100) UNIQUE NOT NULL,
    FullName VARCHAR(100),
    Address VARCHAR(255),
    CreatedAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    );
    ```
    
  - In PostgreSQL, SERIAL is a pseudo data type that automatically generates a sequence of integers for each row inserted into the table. When you define a column as SERIAL, PostgreSQL will automatically create a sequence object and associate it with the column. This sequence generates unique integer values for the column whenever a new row is inserted into the table.

    2. **Products**:

    ```sql
    <!-- for mysql -->
    CREATE TABLE Products (
        ProductID INT PRIMARY KEY AUTO_INCREMENT,
        Name VARCHAR(255) NOT NULL,
        Description TEXT,
        Price DECIMAL(10, 2) NOT NULL,
        CategoryID INT,
        FOREIGN KEY (CategoryID) REFERENCES Categories(CategoryID),
        CreatedAt DATETIME DEFAULT CURRENT_TIMESTAMP
    );
    ```

    ```sql
    <!-- for psql -->
    CREATE TABLE Products (
    ProductID SERIAL PRIMARY KEY,
    Name VARCHAR(255) NOT NULL,
    Description TEXT,
    Price DECIMAL(10, 2) NOT NULL,
    CategoryID INT,
    CreatedAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (CategoryID) REFERENCES Categories(CategoryID)
    );
    ```

    - `DECIMAL(10, 2)`: This specifies the data type of the column. `DECIMAL` is a fixed-point number with a specified precision and scale. In this case, `(10, 2)` indicates that the column can store up to 10 digits in total, with 2 digits reserved for the fractional part (decimal places).
    - `NOT NULL`: This constraint ensures that the column cannot contain null values, meaning every row must have a valid price value.

    So, `Price DECIMAL(10, 2) NOT NULL` means that the `Price` column will store decimal numbers with up to 10 digits in total, where 2 digits are reserved for the fractional part (e.g., cents). Additionally, it ensures that the `Price` column cannot be null, meaning it must always contain a valid price value.

    3. **Orders**:

    ```sql
    CREATE TABLE Orders (
        OrderID INT PRIMARY KEY AUTO_INCREMENT,
        UserID INT,
        OrderDate DATETIME DEFAULT CURRENT_TIMESTAMP,
        Status ENUM('Pending', 'Processing', 'Shipped', 'Delivered') DEFAULT 'Pending',
        FOREIGN KEY (UserID) REFERENCES Users(UserID)
    );
    ```

    ```sql
    <!-- for psql -->
    CREATE TABLE Orders (
    OrderID SERIAL PRIMARY KEY,
    UserID INT,
    OrderDate TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    Status VARCHAR(20) DEFAULT 'Pending',
    FOREIGN KEY (UserID) REFERENCES Users(UserID)
    );
    ```

    4. **Categories**:

    ```sql
    <!-- for mysql -->
    CREATE TABLE Categories (
        CategoryID INT PRIMARY KEY AUTO_INCREMENT,
        Name VARCHAR(100) UNIQUE NOT NULL,
        Description TEXT
    );
    ```

    ```sql
    <!-- for psql -->
    CREATE TABLE Categories (
    CategoryID SERIAL PRIMARY KEY,
    Name VARCHAR(100) UNIQUE NOT NULL,
    Description TEXT 
    );
    ```

These SQL commands create the necessary tables with appropriate columns and constraints to support the CRUD operations for an e-commerce application. You may need to adjust the data types and constraints based on your specific requirements and database system. Additionally, you can add more columns or constraints as needed.

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

### An example of SQL commands to insert data into the tables we created:

1. **Inserting data into the Users table**:

```sql
INSERT INTO Users (Username, Password, Email, FullName, Address)
VALUES ('john_doe', 'password123', 'john@example.com', 'John Doe', '123 Main St'),
       ('jane_smith', 'letmein', 'jane@example.com', 'Jane Smith', '456 Elm St');

-- or 
INSERT INTO Users (Username, Password, Email, FullName, Address, CreatedAt) VALUES
    ('username1', 'password1', 'user1@example.com', 'User One', 'Address One', CURRENT_TIMESTAMP),
    ('username2', 'password2', 'user2@example.com', 'User Two', 'Address Two', CURRENT_TIMESTAMP),
    ('username3', 'password3', 'user3@example.com', 'User Three', 'Address Three', CURRENT_TIMESTAMP);

```

2. **Inserting data into the Products table**:

```sql
INSERT INTO Products (Name, Description, Price, CategoryID)
VALUES ('T-Shirt', 'Comfortable cotton t-shirt', 15.99, 1),
       ('Jeans', 'Classic denim jeans', 29.99, 1),
       ('Running Shoes', 'Lightweight running shoes', 49.99, 2);
```

3. **Inserting data into the Orders table**:

```sql
INSERT INTO Orders (UserID, Status)
VALUES (1, 'Pending'),
       (2, 'Shipped');
```

4. **Inserting data into the Categories table**:

```sql
INSERT INTO Categories (Name, Description)
VALUES ('Apparel', 'Clothing and accessories'),
       ('Footwear', 'Shoes and sandals');
```

These SQL commands insert sample data into each table. Adjust the values as needed to reflect the actual data you want to populate your tables with.
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

## 14. SELECT and WHERE Clause

To perform select operations in PostgreSQL, you can use the `SELECT` statement. Here's an example of how you can retrieve data from the `Users` table:

```sql
-- Retrieve all columns for all users
SELECT * FROM Users;

-- Retrieve specific columns for all users
SELECT UserID, Username, Email FROM Users;

-- Retrieve data based on a condition (e.g., where UserID equals 1)
SELECT * FROM Users WHERE UserID = 1;

-- Retrieve data based on multiple conditions
SELECT * FROM Users WHERE Username = 'username1' AND Email = 'user1@example.com';
```

Similarly, you can perform select operations on other tables like `Products`, `Categories`, and `Orders` using the same `SELECT` statement with appropriate column names and conditions. Here are some examples:

```sql
-- Retrieve all columns for all products
SELECT * FROM Products;

-- Retrieve products belonging to a specific category (e.g., where CategoryID equals 1)
SELECT * FROM Products WHERE CategoryID = 1;

-- Retrieve all columns for all categories
SELECT * FROM Categories;

-- Retrieve all columns for all orders
SELECT * FROM Orders;

-- Retrieve orders placed by a specific user (e.g., where UserID equals 1)
SELECT * FROM Orders WHERE UserID = 1;
```

You can customize the select queries based on your specific requirements and the structure of your database tables.

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

## 15. DISTINCT, LIMIT, ORDER BY

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

## 16. UPDATE STATEMENT

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

Sure, here are examples of `UPDATE` and `DELETE` operations in PostgreSQL for the given tables:

**UPDATE operation:**

1. Update the email address of a user with a specific username:

```sql
UPDATE Users SET Email = 'new_email@example.com' WHERE Username = 'username1';
```

2. Update the status of an order with a specific OrderID:

```sql
UPDATE Orders SET Status = 'Shipped' WHERE OrderID = 123;
```

These examples illustrate how to use `UPDATE` and `DELETE` statements to modify or remove records from the tables in your PostgreSQL database.

## 17. DELETE STATEMENT

```sql
DELETE FROM table_name
WHERE condition;

example
DELETE FROM techers
WHERE ID=102;
```

**DELETE operation:**

1. Delete a user with a specific UserID:

```sql
DELETE FROM Users WHERE UserID = 1;
```

2. Delete all orders placed by a user with a specific UserID:

```sql
DELETE FROM Orders WHERE UserID = 1;
```

## 18. Operators

- Arithmetic operators: + - \* / %
- Comparision or Relational operators > >= < <= = != BETWEEN
- Logical operators: AND OR NOT IN

## 19. RELATIONAL OPERTAORS IN SQL

- `SELECT * FROM Users WHERE CreatedAt > '2022-01-01';`

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

## 20. LOGICAL OPERTAORS IN SQL

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
WHERE name LIKE 's%';
-- find anyone name ends with s
WHERE name LIKE '%s';
-- find anyone name contains hi
WHERE name LIKE '%hi%';
```

- Retrieve users with a username containing a specific substring:

```sql
SELECT * FROM Users WHERE Username LIKE '%part_of_username%';
```

- Retrieve users with a username starting with a specific letter:

```sql
SELECT * FROM Users WHERE Username LIKE 'A%';
```

- Retrieve users with a username ending with a specific letter:

```sql
SELECT * FROM Users WHERE Username LIKE '%a';
```

- Retrieve users with a username starting with a specific letter and having a certain length:

```sql
SELECT * FROM Users WHERE Username LIKE 'A%' AND LENGTH(Username) > 5;
```

- Retrieve users created after a specific date:

```sql
SELECT * FROM Users WHERE CreatedAt > '2022-01-01';
```

- Retrieve users created within a specific date range:

```sql
SELECT * FROM Users WHERE CreatedAt BETWEEN '2022-01-01' AND '2022-12-31';
```

- Select users whose full names are not null or addresses are not null:
`SELECT * FROM Users WHERE FullName IS NOT NULL OR Address IS NOT NULL;`

These examples demonstrate various ways you can use the `WHERE` clause to filter records based on different conditions in your PostgreSQL queries.

## 21. Custom name with AS Keyword

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

`SELECT Email AS UserEmail FROM Users;`

## 22. Constraint and AUTO_INCREMENT

- When creating table we can set constraint and auto increment
- Constraints: NOT NULL, UNIQUE, PRIMARY KEY = NOT NULL + UNIQUE, DEFAULT

```sql
CREATE TABLE TABLE_NAME N(
  ID int NOT NULL AUTO_INCREMENT,
  Name NOT NULL,
)
```

## 23. SubQueries & [UPPER and LOWER Function](https://youtu.be/95wBGq9PJZQ)

- Sub Queries: Query inside query

```sql
SELECT * FROM Products
WHERE Price > (SELECT AVG(Price) FROM Products);
```

## 24. [Functions](https://youtu.be/hn6P4tBRaIE)

- Concatenating the username and email address:

```sql
SELECT CONCAT(Username, '@', Email) AS UserEmail FROM Users;
```

- Getting the length of the username:

```sql
SELECT Username, LENGTH(Username) AS UsernameLength FROM Users;
```

- Extracting the year from the created date:

```sql
SELECT Username, EXTRACT(YEAR FROM CreatedAt) AS CreatedYear FROM Users;
```

- Converting the username to uppercase:

```sql
SELECT UPPER(Username) AS UpperCaseUsername FROM Users;
```

- Converting the username to lowercase:

```sql
SELECT LOWER(Username) AS LowerCaseUsername FROM Users;
```

- The GREATEST and LEAST functions in SQL are typically used with numeric or date/time values.
Sure, let's consider a scenario where we want to find the user with the earliest registration date (`CreatedAt`) and the user with the latest registration date.

Here's how you can use the `LEAST` and `GREATEST` functions in SQL for the `Users` table:

```sql
-- Find the user with the earliest registration date
SELECT * FROM Users
WHERE CreatedAt = (SELECT LEAST(CreatedAt) FROM Users);

-- Find the user with the latest registration date
SELECT * FROM Users
WHERE CreatedAt = (SELECT GREATEST(CreatedAt) FROM Users);
```

In these queries:

- `LEAST(CreatedAt)` finds the minimum value of the `CreatedAt` column.
- `GREATEST(CreatedAt)` finds the maximum value of the `CreatedAt` column.
- We then use subqueries to select the user(s) whose `CreatedAt` matches the result of `LEAST` or `GREATEST`.

These queries will return the user(s) with the earliest and latest registration dates, respectively, from the `Users` table.

## 25. [Aggregate Functions](https://youtu.be/dO2h-s8tv2g)

- aggregate: one result in the end. AVG(), COUNT(), MAX(), MIN(), SUM()

```sql
-- Total number of users
SELECT COUNT(*) AS TotalUsers FROM Users;

-- Average age of users (assuming there's an Age column)
SELECT AVG(Age) AS AverageAge FROM Users;

-- Earliest registration date
SELECT MIN(CreatedAt) AS EarliestRegistrationDate FROM Users;

-- Latest registration date
SELECT MAX(CreatedAt) AS LatestRegistrationDate FROM Users;

-- Total number of products
SELECT COUNT(*) AS TotalProducts FROM Products;

-- Average price of products
SELECT AVG(Price) AS AveragePrice FROM Products;

-- Highest price of a product
SELECT MAX(Price) AS HighestPrice FROM Products;

-- Lowest price of a product
SELECT MIN(Price) AS LowestPrice FROM Products;

```

## 26. PostgreSQL REST API

- PostgreSQL is a RDBMS like MySQL
- it supports sql and json
- download PostgreSQL and node
- psql postgres://anisul_islam@localhost:5432/anisul_islam
- go to postgres database with the command psql -U postgres

```sql
  \l -> list of all databases
  \c databaseName-> move a specific databaseName
  \dt -> show all the tables in a db
  DROP DATABASE database_name

CREATE DATABASE todo_database;

--\c into todo_database

CREATE TABLE todo(
  todo_id SERIAL PRIMARY KEY,
  description VARCHAR(255)
);

SELECT *
FROM todo;
```

CRUD operations
CREATE - POST HTTP METHOD

```sql
INSERT INTO table_name (col1, col2, ..., coln)
VALUES
(val1, val2, ..., valN);
```

READ - GET HTTP METHOD

```sql
SELECT (col1, col2, ..., coln)
FROM table_name
WHERE condition;
```

UPDATE - PUT HTTP METHOD

```sql
UPDATE table_name
SET col1=val1, col2=val2, ...coln=valn
WHERE condition;
```

DELETE - DELETE HTTP METHOD

```sql
DELETE FROM table_name
WHERE condition;
```

- install express pg nodemon
- create server
- create a database
- create a table
