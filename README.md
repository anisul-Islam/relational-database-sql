# Relational Database

- [My MySQL playlist](https://www.youtube.com/playlist?list=PLgH5QX0i9K3qLcx9DvVDWmNJ7riPvxzCD)
- [PSQL Tutorial](https://www.postgresqltutorial.com/)

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
-- Drop the existing order_products table
DROP TABLE IF EXISTS table_name;

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

- **Users**:

    ```sql
    <!-- for mysql  -->
    
    CREATE TABLE Users (
      userId SERIAL PRIMARY KEY,
      name VARCHAR(100) NOT NULL,
      email VARCHAR(100) UNIQUE NOT NULL,
      password VARCHAR(255) NOT NULL,
      address VARCHAR(255),
      image VARCHAR(255),
      isAdmin BOOLEAN DEFAULT FALSE,
      isBanned BOOLEAN DEFAULT FALSE,
      createdAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP

    );


    ALTER TABLE users

    ADD COLUMN isAdmin BOOLEAN DEFAULT FALSE,
    ADD COLUMN isBanned BOOLEAN DEFAULT FALSE;

    ```

    ```sql
    <!-- for psql -->
    -- Drop the existing order_products table

   DROP TABLE IF EXISTS users;

   CREATE TABLE users (
      userId SERIAL PRIMARY KEY,
      name VARCHAR(100) NOT NULL,
      email VARCHAR(100) UNIQUE NOT NULL,
      password VARCHAR(255) NOT NULL,
      address VARCHAR(255),
      image VARCHAR(255),
      isAdmin BOOLEAN DEFAULT FALSE,
      isBanned BOOLEAN DEFAULT FALSE,
      createdAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    );

    ```

    SERIAL: In PostgreSQL, SERIAL is a pseudo data type that automatically generates a sequence of integers for each row inserted into the table. When you define a column as SERIAL, PostgreSQL will automatically create a sequence object and associate it with the column. This sequence generates unique integer values for the column whenever a new row is inserted into the table.

     Image type: if you're storing the actual image files in the database, you might consider using a BYTEA (byte array) data type, which is suitable for storing binary data such as images. In some databases, there are specific data types designed for storing large binary objects (LOBs) like images, such as BLOB (Binary Large Object) in MySQL or BYTEA in PostgreSQL.

- **Using UUID (Universal Unique Identifier) / GUID (Globally Unique Identifier)**
    `userId UUID PRIMARY KEY DEFAULT uuid_generate_v4(),`

    ```sql
    <!-- for psql -->
    -- Drop the existing order_products table

   DROP TABLE IF EXISTS users;

   CREATE TABLE users (
      userId UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
      name VARCHAR(100) NOT NULL,
      email VARCHAR(100) UNIQUE NOT NULL,
      password VARCHAR(255) NOT NULL,
      address VARCHAR(255),
      image VARCHAR(255),
      isAdmin BOOLEAN DEFAULT FALSE,
      isBanned BOOLEAN DEFAULT FALSE,
      createdAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    );

    ```

    To ensure that the `uuid-ossp` extension is installed and enabled in your PostgreSQL database, you can follow these steps:

    1. Connect to your PostgreSQL database using a client tool or command-line interface that supports executing SQL commands.

    2. Check if the `uuid-ossp` extension is already installed by running the following SQL command:

    ```sql
    SELECT * FROM pg_extension WHERE extname = 'uuid-ossp';
    ```

    3. If the extension is not installed, you can install it by running the following SQL command:

    ```sql
    CREATE EXTENSION IF NOT EXISTS "uuid-ossp";
    ```

    This command will install the `uuid-ossp` extension if it's not already installed. If you encounter an error indicating that you don't have permission to create extensions, you may need to perform this action as a superuser or ask your database administrator for assistance.

    4. Once the extension is installed, you can enable it for your current database by running the following SQL command:

    ```sql
    CREATE EXTENSION IF NOT EXISTS "uuid-ossp" SCHEMA public;
    ```

    Replace `public` with the name of the schema where you want to enable the extension if you're using a different schema.

    5. After enabling the extension, you can verify that it's enabled by running the first SQL command again:

    ```sql
    SELECT * FROM pg_extension WHERE extname = 'uuid-ossp';
    ```

    You should see a row indicating that the `uuid-ossp` extension is now installed and enabled in your database.

- **Categories**:

    ```sql
    <!-- for mysql -->
    DROP TABLE IF EXISTS categories;
    CREATE TABLE categories (
        categoryID INT PRIMARY KEY AUTO_INCREMENT,
        name VARCHAR(100) UNIQUE NOT NULL,
        description TEXT
    );
    ```

    ```sql
    <!-- for psql -->
    DROP TABLE IF EXISTS categories;
    CREATE TABLE categories (
      categoryID SERIAL PRIMARY KEY,
      name VARCHAR(100) UNIQUE NOT NULL,
      slug VARCHAR(100) UNIQUE NOT NULL,
      description TEXT 
    );

    DROP TABLE IF EXISTS categories;
    CREATE TABLE categories (
      categoryId UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
      name VARCHAR(100) UNIQUE NOT NULL,
      slug VARCHAR(100) UNIQUE NOT NULL,
      description TEXT 
    );
    ```

- **Products**:

    ```sql
    <!-- for mysql -->
    DROP TABLE IF EXISTS products;
    CREATE TABLE products (
        productID INT PRIMARY KEY AUTO_INCREMENT,
        name VARCHAR(255) NOT NULL,
        description TEXT,
        price DECIMAL(10, 2) NOT NULL,
        categoryID INT,
        FOREIGN KEY (CategoryID) REFERENCES Categories(CategoryID),
        createdAt DATETIME DEFAULT CURRENT_TIMESTAMP
    );
    ```

    ```sql
    <!-- for psql -->
    DROP TABLE IF EXISTS products;
    CREATE TABLE products (
        productID SERIAL PRIMARY KEY,
        name VARCHAR(255) NOT NULL,
        slug VARCHAR(255) NOT NULL,
        description TEXT,
        price DECIMAL(10, 2) NOT NULL,
        quantity INT DEFAULT 0,
        sold INT DEFAULT 0,
        image VARCHAR(255),
        shipping BOOLEAN,
        categoryID INT REFERENCES categories(categoryID), -- Combined with foreign key constraint
        createdAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    );

    ```

    ```sql
    DROP TABLE IF EXISTS products;
    CREATE TABLE products (
        productId UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
        name VARCHAR(255) NOT NULL,
        slug VARCHAR(255) NOT NULL,
        description TEXT,
        price DECIMAL(10, 2) NOT NULL,
        quantity INT DEFAULT 0,
        sold INT DEFAULT 0,
        image VARCHAR(255),
        shipping BOOLEAN,
        categoryID UUID REFERENCES categories(categoryID), -- Combined with foreign key constraint
        createdAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    );
    ```

    - `DECIMAL(10, 2)`: This specifies the data type of the column. `DECIMAL` is a fixed-point number with a specified precision and scale. In this case, `(10, 2)` indicates that the column can store up to 10 digits in total, with 2 digits reserved for the fractional part (decimal places).
    - `NOT NULL`: This constraint ensures that the column cannot contain null values, meaning every row must have a valid price value.

    So, `Price DECIMAL(10, 2) NOT NULL` means that the `Price` column will store decimal numbers with up to 10 digits in total, where 2 digits are reserved for the fractional part (e.g., cents). Additionally, it ensures that the `Price` column cannot be null, meaning it must always contain a valid price value.

- **Orders**:

    ```sql
    CREATE TABLE orders (
        OrderID INT PRIMARY KEY AUTO_INCREMENT,
        UserID INT,
        OrderDate DATETIME DEFAULT CURRENT_TIMESTAMP,
        status VARCHAR(20) DEFAULT 'Pending',
        FOREIGN KEY (UserID) REFERENCES Users(UserID)
    );
    ```

   ```sql
    <!-- for psql -->
   -- Create the orders table (without junction table)

    CREATE TABLE orders (
        orderId UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
        orderDate TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
        status VARCHAR(20) DEFAULT 'Pending',
        <!-- userID INT REFERENCES Users(UserID), -->
        userID UUID REFERENCES Users(UserID),
        payment JSONB, -- Assuming payment details are stored as JSON
        productIDs UUID[], -- Array of product IDs
        createdAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    );

    or 
     <!-- you can create your own type: `CREATE TYPE order_status AS ENUM ('Pending', 'Processing', 'Shipped', 'Delivered');` -->
    CREATE TYPE order_status AS ENUM ('Pending', 'Processing', 'Shipped', 'Delivered');
    CREATE TABLE orders (
      orderId SERIAL PRIMARY KEY,
      orderDate TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
      status order_status DEFAULT 'Pending',
      payment JSONB,
      userId INT REFERENCES users(userId),
      products JSONB, -- denormalize the data and store product information directly   
      createdAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    );

    -- with the junction table : normalize and no direct access to the table without foreign key
     CREATE TYPE order_status AS ENUM ('Pending', 'Processing', 'Shipped', 'Delivered');
     CREATE TABLE orders (
        orderId UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
        orderDate TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
        status order_status DEFAULT 'Pending',
        userID UUID REFERENCES users(userID)
    );


    -- Create the junction table

    CREATE TABLE order_products (
        orderID UUID REFERENCES orders(orderID),
        productID UUID REFERENCES products(productID),
        quantity INT,
        PRIMARY KEY (orderID, productID)
    );

    ```

- you can create your own type: `CREATE TYPE order_status AS ENUM ('Pending', 'Processing', 'Shipped', 'Delivered');`

## 13. ALTER, ADD & DROP

- Add a new column to the table

```sql
ALTER TABLE TableName
ADD NewColumn DATA_TYPE(SIZE);

ALTER TABLE Students
ADD Hobby VARCHAR(100) DEFAULT 'Travelling';

ALTER TABLE Users
ADD COLUMN isAdmin BOOLEAN DEFAULT FALSE,
ADD COLUMN isBanned BOOLEAN DEFAULT FALSE;

```

- To delete a column or change the data type of a column from a table in SQL, you can use the `ALTER TABLE` statement with the `DROP COLUMN` clause. Here's the basic syntax:

```sql
ALTER TABLE table_name
DROP COLUMN column_name;

ALTER TABLE table_name
ALTER COLUMN column_name new_data_type;
```

Replace `table_name` with the name of your table and `column_name` with the name of the column you want to delete.

For example, if you want to delete a column named `email` from a table named `users`, you would execute:

```sql
ALTER TABLE users
DROP COLUMN email;

ALTER TABLE students
ALTER COLUMN age FLOAT;
```

Keep in mind that dropping a column will permanently remove it and all its data from the table, so be sure to use this operation carefully. Also, make sure to back up your data before performing any alterations to your database schema.

## 14. Truncate Table

- Truncate table will not delete entire table just the records
`TRUNCATE TABLE student_details` vs `DROP TABLE student_details`

## 15. INSERT RECORDS

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

- **Inserting data into the Users table**:

```sql

INSERT INTO users (name, email, password, address, image, isAdmin, isBanned)
VALUES 
  ('John Doe', 'john@example.com', 'password123', '123 Main St', 'profile.jpg', TRUE, FALSE),
  ('Alice Smith', 'alice@example.com', 'password456', '456 Elm St', 'avatar.png', FALSE, FALSE),
  ('Bob Johnson', 'bob@example.com', 'password789', '789 Oak St', NULL, FALSE, TRUE),
  ('Emily Davis', 'emily@example.com', 'passwordabc', NULL, 'default.jpg', FALSE, FALSE),
  ('Michael Brown', 'michael@example.com', 'passwordxyz', '567 Pine St', 'user.png', TRUE, FALSE);

-- or 
INSERT INTO users (name, email, password, address, image, isAdmin, isBanned,createdAt)
VALUES 
  ('John Doe', 'john@example.com', 'password123', '123 Main St', 'profile.jpg', TRUE, FALSE,CURRENT_TIMESTAMP),
```

- **Inserting data into the Categories table**:

```sql
  INSERT INTO categories (name, slug, description)
  VALUES 
  ('Electronics', 'electronics', 'Electronic devices and accessories'),
  ('Clothing', 'clothing', 'Apparel and fashion accessories'),
  ('Books', 'books', 'Fiction and non-fiction literature'),
  ('Home Decor', 'home-decor', 'Decorative items for the home'),
  ('Toys', 'toys', 'Children''s toys and games'); 
```

- **Inserting data into the Products table**:

```sql
INSERT INTO products (name, description, price, quantity, categoryID, createdAt)
VALUES
    ('Product 1 Name', 'Product 1 Description', 10.99, 100, 1, NOW()),
    ('Product 2 Name', 'Product 2 Description', 19.99, 50, 2, NOW()),
    -- Add more products here...
    ('Product 20 Name', 'Product 20 Description', 5.99, 200, 4, NOW());


  -- for serial data 
  INSERT INTO products (name, slug, description, price, quantity, sold, image, shipping, categoryID, createdAt)
VALUES 
  ('Laptop', 'laptop', 'High-performance laptop with SSD storage', 999.99, 50, 10, 'laptop.jpg', TRUE, 1, NOW()),
  ('Smartphone', 'smartphone', 'Latest smartphone model with 5G connectivity', 699.99, 100, 30, 'smartphone.jpg', TRUE, 1, NOW()),
  ('T-shirt', 't-shirt', 'Cotton t-shirt with trendy design', 19.99, 200, 80, 't-shirt.jpg', TRUE, 2, NOW()),
  ('Jeans', 'jeans', 'Denim jeans for casual wear', 39.99, 150, 60, 'jeans.jpg', TRUE, 2, NOW()),
  ('Novel', 'novel', 'Bestselling fiction novel', 12.99, 300, 120, 'novel.jpg', TRUE, 3, NOW()),
  ('Cookbook', 'cookbook', 'Collection of popular recipes', 24.99, 100, 40, 'cookbook.jpg', TRUE, 3, NOW()),
  ('Throw Pillow', 'throw-pillow', 'Decorative throw pillow for couch', 29.99, 50, 20, 'throw-pillow.jpg', TRUE, 4, NOW()),
  ('Wall Art', 'wall-art', 'Canvas wall art for home decor', 49.99, 80, 30, 'wall-art.jpg', TRUE, 4, NOW()),
  ('Action Figure', 'action-figure', 'Collectible action figure', 14.99, 120, 50, 'action-figure.jpg', TRUE, 5, NOW()),
  ('Board Game', 'board-game', 'Popular board game for family fun', 29.99, 70, 30, 'board-game.jpg', TRUE, 5, NOW()),
  ('Headphones', 'headphones', 'Wireless headphones with noise cancellation', 149.99, 90, 40, 'headphones.jpg', TRUE, 1, NOW()),
  ('Smart Watch', 'smart-watch', 'Fitness tracker smart watch', 199.99, 60, 20, 'smart-watch.jpg', TRUE, 1, NOW()),
  ('Dress', 'dress', 'Elegant dress for special occasions', 79.99, 80, 25, 'dress.jpg', TRUE, 2, NOW()),
  ('Sneakers', 'sneakers', 'Stylish sneakers for everyday wear', 59.99, 120, 45, 'sneakers.jpg', TRUE, 2, NOW()),
  ('Cooking Utensils Set', 'cooking-utensils-set', 'Complete set of kitchen utensils', 49.99, 100, 35, 'cooking-utensils-set.jpg', TRUE, 4, NOW());

  -- for uuid 
INSERT INTO products (name, slug, description, price, quantity, sold, image, shipping, categoryID, createdAt)
VALUES 
  ('Laptop', 'laptop', 'High-performance laptop with SSD storage', 999.99, 50, 10, 'laptop.jpg', TRUE, '1820433f-fd1a-44c7-a168-59dd34554ca5', NOW()),
  ('Smartphone', 'smartphone', 'Latest smartphone model with 5G connectivity', 699.99, 100, 30, 'smartphone.jpg', TRUE, '1820433f-fd1a-44c7-a168-59dd34554ca5', NOW()),
  ('T-shirt', 't-shirt', 'Cotton t-shirt with trendy design', 19.99, 200, 80, 't-shirt.jpg', TRUE, 'f9e6f058-6c69-4133-9638-352b2b312db8', NOW()),
  ('Jeans', 'jeans', 'Denim jeans for casual wear', 39.99, 150, 60, 'jeans.jpg', TRUE, 'f9e6f058-6c69-4133-9638-352b2b312db8', NOW()),
  ('Novel', 'novel', 'Bestselling fiction novel', 12.99, 300, 120, 'novel.jpg', TRUE, '1d2cab81-1424-4c14-acc5-6cdc0a2a096b', NOW()),
  ('Cookbook', 'cookbook', 'Collection of popular recipes', 24.99, 100, 40, 'cookbook.jpg', TRUE, '1d2cab81-1424-4c14-acc5-6cdc0a2a096b', NOW()),
  ('Throw Pillow', 'throw-pillow', 'Decorative throw pillow for couch', 29.99, 50, 20, 'throw-pillow.jpg', TRUE, 'c79a747b-7741-4b5b-904d-f7ac3a372613', NOW()),
  ('Wall Art', 'wall-art', 'Canvas wall art for home decor', 49.99, 80, 30, 'wall-art.jpg', TRUE, 'c79a747b-7741-4b5b-904d-f7ac3a372613', NOW()),
  ('Action Figure', 'action-figure', 'Collectible action figure', 14.99, 120, 50, 'action-figure.jpg', TRUE, 'd6e297d6-10bb-430a-a774-4d84297f4bcb', NOW()),
  ('Board Game', 'board-game', 'Popular board game for family fun', 29.99, 70, 30, 'board-game.jpg', TRUE, 'd6e297d6-10bb-430a-a774-4d84297f4bcb', NOW()),
  ('Headphones', 'headphones', 'Wireless headphones with noise cancellation', 149.99, 90, 40, 'headphones.jpg', TRUE, '1820433f-fd1a-44c7-a168-59dd34554ca5', NOW()),
  ('Smart Watch', 'smart-watch', 'Fitness tracker smart watch', 199.99, 60, 20, 'smart-watch.jpg', TRUE, '1820433f-fd1a-44c7-a168-59dd34554ca5', NOW()),
  ('Dress', 'dress', 'Elegant dress for special occasions', 79.99, 80, 25, 'dress.jpg', TRUE, 'f9e6f058-6c69-4133-9638-352b2b312db8', NOW()),
  ('Sneakers', 'sneakers', 'Stylish sneakers for everyday wear', 59.99, 120, 45, 'sneakers.jpg', TRUE, 'f9e6f058-6c69-4133-9638-352b2b312db8', NOW()),
  ('Cooking Utensils Set', 'cooking-utensils-set', 'Complete set of kitchen utensils', 49.99, 100, 35, 'cooking-utensils-set.jpg', TRUE, 'c79a747b-7741-4b5b-904d-f7ac3a372613', NOW());
```

- **Inserting data into the Orders table**:

```sql
-- without junction table:  denormalize the data and store product information directly   
INSERT INTO orders (orderDate, status, payment, userId, products)
VALUES
  ('2024-04-20 10:00:00', 'Pending', '{"method": "credit card", "amount": 100}', 1, '[{"product_id": 1, "quantity": 3}, {"product_id": 2, "quantity": 1}]'),
  ('2024-04-21 11:00:00', 'Processing', '{"method": "cash on delivery", "amount": 150}', 2, '[{"product_id": 3, "quantity": 2}]');

```

```sql
-- with junction table
-- Inserting a sample order with multiple products
INSERT INTO orders (orderDate, status, userID) VALUES (CURRENT_TIMESTAMP, 'Pending', 'f10b0683-6e0b-45a1-95a7-909a72aa1187');

-- Inserting products for the sample order
INSERT INTO order_products (orderID, productID, quantity) VALUES
    ('2bb5c629-c822-4b73-b75b-9fe11c39495e', '486103e3-4d54-4f0e-b91c-96561bc8f91b', 2),
    ('2bb5c629-c822-4b73-b75b-9fe11c39495e', '4897005c-ce5f-4af1-8e82-b2e2b54e8720', 1),('2bb5c629-c822-4b73-b75b-9fe11c39495e', 'c1ab6fbc-e4e5-4e5d-b75c-868c3baa28e9', 3);

-- another method
INSERT INTO order_products (orderID, productID, quantity)
SELECT '2bb5c629-c822-4b73-b75b-9fe11c39495e', 
       unnest(array['486103e3-4d54-4f0e-b91c-96561bc8f91b'::uuid, '4897005c-ce5f-4af1-8e82-b2e2b54e8720'::uuid, 'c1ab6fbc-e4e5-4e5d-b75c-868c3baa28e9'::uuid]),
       unnest(array[2, 1, 3]);

-- now select the products, user based on product id
  SELECT
      u.name AS user_name,
      u.email AS user_email,
      p.name AS product_name,
      p.price AS product_price,
      op.quantity AS product_quantity
  FROM
      orders o
  JOIN
      order_products op ON o.orderID = op.orderID
  JOIN
      users u ON o.userID = u.userID
  JOIN
      products p ON op.productID = p.productID
  WHERE
      o.orderID = '2bb5c629-c822-4b73-b75b-9fe11c39495e'; 

```

## 16. FIND / SELECT RECORDS

- syntax for selecting records

```sql
  -- find all records with specific fields/columns
  SELECT COL1,COL2,...COLN
  FROM table_name
  -- find all records with all the fields/columns
  SELECT *
  FROM table_name;
```

```sql
SELECT 
  orderId,
  orderDate,
  status,
  payment,
  userId,
  products
FROM 
  orders
WHERE 
  orderId = 1;

If you want to extract specific information from the products JSONB array, such as the product_id and quantity, you can use JSON functions like jsonb_array_elements or jsonb_array_elements_text. Here's an example:
SELECT 
  orderId,
  orderDate,
  status,
  payment,
  userId,
  (jsonb_array_elements(products) ->> 'product_id')::int AS product_id,
  (jsonb_array_elements(products) ->> 'quantity')::int AS quantity
FROM 
  orders
WHERE 
  orderId = 1;
```

- To visualize a PostgreSQL table nicely in the terminal, you can use the `\x` command in `psql` to toggle expanded display mode.
  - Run the following command to enter expanded display mode `\x`

  - After enabling expanded display mode, run a query to select data from your table. For example: `SELECT * FROM your_table;`

  - To disable expanded display mode and return to the default display format, simply run: `\x`

## 17. SELECT and WHERE Clause

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

## 18. DISTINCT, LIMIT, ORDER BY

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

## 19. DELETE STATEMENT

```sql
DELETE FROM table_name
WHERE condition;

example
DELETE FROM techers
WHERE ID=102;
```

**DELETE operation:**

- Delete a user with a specific UserID:

```sql
DELETE FROM Users WHERE UserID = 1;
```

- Delete all orders placed by a user with a specific UserID:

```sql
DELETE FROM Orders WHERE UserID = 1;
```

## 20. Operators

- Arithmetic operators: + - \* / %
- Comparision or Relational operators > >= < <= = != BETWEEN
- Logical operators: AND OR NOT IN

## 21. RELATIONAL OPERTAORS IN SQL

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

## 22. LOGICAL OPERTAORS IN SQL

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

## 23. Custom name with AS Keyword

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

## 24. SubQueries & [UPPER and LOWER Function](https://youtu.be/95wBGq9PJZQ)

- Sub Queries: Query inside query

```sql
SELECT * FROM Products
WHERE Price > (SELECT AVG(Price) FROM Products);
```

## 25. Constraint and AUTO_INCREMENT

- When creating table we can set constraint and auto increment
- Constraints: NOT NULL, UNIQUE, PRIMARY KEY = NOT NULL + UNIQUE, DEFAULT

```sql
CREATE TABLE TABLE_NAME N(
  ID int NOT NULL AUTO_INCREMENT,
  Name NOT NULL,
)
```

## 26. [Functions](https://youtu.be/hn6P4tBRaIE)

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

## 27. [Aggregate Functions](https://youtu.be/dO2h-s8tv2g)

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

## 28. GroupBy

```sql
SELECT Country, COUNT(UserID) AS UserCount
FROM Users
GROUP BY Country;
```

## 29. Joining Tables

```sql
-- create student table 
CREATE TABLE Students (
    StudentId INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Gender VARCHAR(50),
    DOB DATE,
    Age INT
);

INSERT INTO Students (StudentId, FirstName, LastName, Gender, DOB, Age) VALUES
(1, 'John', 'Doe', 'Male', '1995-05-15', 26),
(2, 'Jane', 'Smith', 'Female', '1998-08-20', 23),
(3, 'Michael', 'Johnson', 'Male', '1997-03-10', 24),
(4, 'Emily', 'Brown', 'Female', '1996-11-25', 25),
(5, 'David', 'Williams', 'Male', '1999-06-30', 22),
(6, 'Sarah', 'Jones', 'Female', '1994-09-05', 27),
(8, 'Christopher', 'Davis', 'Male', '2000-02-12', 21);


-- create Grade table 
CREATE TABLE Grades (
    GradeID INT PRIMARY KEY,
    StudentID INT,
    Course VARCHAR(50),
    Grade VARCHAR(2)
);

INSERT INTO Grades (GradeID, StudentID, Course, Grade)
VALUES
    (1, 1, 'Math', 'A'),
    (2, 1, 'Science', 'B'),
    (3, 2, 'Math', 'B+'),
    (4, 3, 'Math', 'C'),
    (5, 3, 'Science', 'A-'),
    (6, 7, 'Science', 'A-');

```

### joining based on condition

```sql
SELECT FirstName, LastName, Age, Course, Grade
FROM Students,Grades
WHERE Students.StudentId = Grades.StudentId;

-- more better syntax for avoiding naming conflict by using 'fully qulaified name'
SELECT Students.FirstName, Students.LastName, Students.Age, Grades.Course, Grades.Grade
FROM Students,Grades
WHERE Students.StudentId = Grades.StudentId;

-- shorting the name by using Custom name
SELECT s.FirstName, s.LastName, s.Age, g.Course, g.Grade
FROM Students AS s,Grades AS g
WHERE s.StudentId = g.StudentId;
```

### joining using JOIN Clause

```sql

SELECT s.FirstName, s.LastName, s.Age, g.Course, g.Grade
FROM Students AS s JOIN Grades AS g
ON s.StudentId = g.StudentId;
```

### Inner Join

- INNER JOIN will returned only the matched records

```sql
SELECT s.FirstName, s.LastName, s.Age, g.Course, g.Grade
FROM Students AS s INNER JOIN Grades AS g
ON s.StudentId = g.StudentId;
```

### Left Join

- LEFT JOIN will rturns all rows from the left table (Table1), and the matched rows from the right table (Table). If there is no match, the result is NULL on the right side.

```sql
SELECT s.StudentId, s.FirstName, s.LastName, s.Age, g.Course, g.Grade
FROM Students AS s LEFT JOIN Grades AS g
ON s.StudentId = g.StudentId;
```

### Right Join

- RIGHT JOIN will rturns all rows from the right table (Table2), and the matched rows from the left table (Table1). If there is no match, the result is NULL on the left side.

```sql
SELECT s.StudentId, s.FirstName, s.LastName, s.Age, g.Course, g.Grade
FROM Students AS s RIGHT JOIN Grades AS g
ON s.StudentId = g.StudentId;
```

### FULL Join

- Returns all rows when there is a match in either table. This means it returns all the rows from the left table (Table1) and all the rows from the right table (Table2), with NULLs in the columns where there is no match.

```sql
SELECT s.StudentId, s.FirstName, s.LastName, s.Age, g.Course, g.Grade
FROM Students AS s FULL JOIN Grades AS g
ON s.StudentId = g.StudentId;
```

### Join among all the tables

```sql
-- Order Table 
CREATE TABLE Orders(
  OrderId SERIAL PRIMARY KEY,
  OrderDate TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  Status VARCHAR(50) DEFAULT 'Pending',
  UserId INT REFERENCES Users(UserId),
  ProductId INT REFERENCES Products(ProductId)
);

INSERT INTO Orders (UserId, ProductId, Status)
VALUES
(2, 1, 'Pending');

INSERT INTO Orders (UserId, ProductId, Status)
VALUES
(3, 2, 'Pending');

INSERT INTO Orders (UserId, ProductId, Status)
VALUES
(2, 2, 'Pending');

SELECT u.UserId, u.Username, u.Address, o.Status 
FROM Users u
INNER JOIN Orders o ON u.UserId = o.UserId;


SELECT o.OrderId, o.Status, u.Username, u.Address, p.Name, p.Price, p.Description
FROM Orders o
INNER JOIN Products p ON o.ProductId = p.ProductId
INNER JOIN Users u ON o.UserId = u.UserId;
```

## 30. UNION and UNION ALL, INTERSECT

- create 2 tables: people_visited_england and people_visited_finland
- same number of columns and same sequences
- union will remove duplicates records; it is slower
- union all will not remove duplicates records; it is faster as no concerns of removing duplicates
- find people visited both countries

```sql
SELECT Name, Gender, Age
FROM people_visited_england

UNION

SELECT Name, Gender, Age
FROM people_visited_finland
```

In SQL, the `INTERSECT` operator is used to retrieve the common rows that exist in two separate SELECT queries. It returns only the rows that appear in both result sets. Here's an example:

Suppose we have two tables: `TableA` and `TableB`, each containing different sets of data.

TableA:

| ID | Name    |
|----|---------|
| 1  | John    |
| 2  | Alice   |
| 3  | Bob     |

TableB:

| ID | Name    |
|----|---------|
| 2  | Alice   |
| 3  | Bob     |
| 4  | Sarah   |

Now, let's say we want to find the common names between these two tables. We can use the `INTERSECT` operator to achieve this:

```sql
SELECT Name FROM TableA
INTERSECT
SELECT Name FROM TableB;
```

This query will return:

| Name    |
|---------|
| Alice   |
| Bob     |

Explanation:

- The `SELECT Name FROM TableA` statement retrieves all the names from `TableA`.
- The `SELECT Name FROM TableB` statement retrieves all the names from `TableB`.
- The `INTERSECT` operator returns only the common names that appear in both result sets, which are "Alice" and "Bob".

This demonstrates how the `INTERSECT` operator can be used to find the intersection of two sets of data in SQL.

## 31. VIEW (Virtual Table)

- view is a virtual table a copy of original table with the columns that you want to display

```sql
CREATE VIEW view_name AS 
SELECT Name, Age
FROM original_table;

SELECT *
FROM view_name;
```

- how to drop/delete a view
`DROP VIEW view_name`

- how to update view

```sql
UPDATE student_view
SET Name = 'Fahima'
WHERE Roll=101;
```

- how to insert new records to the view
- how to delete records from the view

## 32. DATE & Time

```sql
// for mysql
SELECT CURDATE() 
SELECT CURTIME()
SELECT NOW()
SELECT MAKEDATE(2017,312);
SELECT DAYNAME('2017-09-14');
SELECT MONTHNAME('2017-09-14');

// for psql
SELECT CURRENT_DATE;
SELECT CURRENT_TIME;
SELECT NOW();
SELECT MAKE_DATE(2017, 312);
SELECT TO_CHAR('2017-09-14'::DATE, 'Day');
SELECT TO_CHAR('2017-09-14'::DATE, 'Month');

-- use DAYNAME(DATE) for DOB
SELECT DAYNAME(DOB)
FROM TableName;

-- in psql
SELECT TO_CHAR(DOB, 'Day') AS day_of_week
FROM TableName;
```

## 33. [Indexing](https://www.postgresqltutorial.com/postgresql-indexes/postgresql-create-index/)

Indexing is a database optimization technique used to improve the performance of queries by allowing the database engine to quickly locate rows in a table that match certain criteria. Here are some reasons why indexing is important:

1. **Faster Data Retrieval**: Indexes provide a quick path to the data, allowing the database engine to locate and retrieve rows more efficiently. Without indexes, the database engine would need to scan the entire table sequentially, which can be slow, especially for large tables.

2. **Improved Query Performance**: Queries that involve filtering, sorting, or joining data often benefit from indexes. Indexes allow the database engine to quickly identify and access the rows that satisfy the query conditions, resulting in faster query execution times.

3. **Support for Constraints**: Indexes are often used to enforce constraints such as primary key or unique constraints. These constraints ensure data integrity and prevent duplicate or null values in key columns.

4. **Optimized Join Operations**: Indexes can be used to optimize join operations between tables by providing efficient access paths to the joined columns.

5. **Reduced Disk I/O**: By storing index data in a separate structure, indexes reduce the amount of disk I/O required to retrieve data, which can lead to overall performance improvements, especially in disk-bound systems.

Overall, indexing plays a crucial role in database performance tuning and is essential for improving the responsiveness and scalability of database applications. However, it's important to carefully consider the indexing strategy and avoid over-indexing, as indexes come with overhead in terms of storage space and maintenance costs.

- create single column index: `CREATE INDEX index_name ON table_name (column_name);`
- create multiple column index: `CREATE INDEX index_name ON table_name (column1_name, column2_name);`
- better syntax

  ```sql
    CREATE INDEX [IF NOT EXISTS] index_name
    ON table_name(column1, column2, ...);
  ```

- drop index: `DROP INDEX index_name;`

- check existing indexes

```sql
SELECT * 
FROM pg_indexes 
WHERE tablename = 'users';

```

```sql
-- Create the Users table
CREATE TABLE users (
    userID SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    address VARCHAR(255),
    image VARCHAR(255),
    isAdmin BOOLEAN DEFAULT FALSE,
    isBanned BOOLEAN DEFAULT FALSE,
    createdAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Insert records into the Users table
INSERT INTO users (name, email, password, address, isAdmin, isBanned, createdAt)
VALUES
    ('Emily Wilson', 'emily@example.com', 'password123', '123 Oak St', false, false, CURRENT_TIMESTAMP),
    ('James Brown', 'james@example.com', 'password456', '456 Maple St', false, false, CURRENT_TIMESTAMP),
    ('Olivia Davis', 'olivia@example.com', 'password789', '789 Elm St', false, false, CURRENT_TIMESTAMP),
    ('Liam Johnson', 'liam@example.com', 'passwordabc', '123 Pine St', false, false, CURRENT_TIMESTAMP),
    ('Ava Garcia', 'ava@example.com', 'passworddef', '456 Oak St', false, false, CURRENT_TIMESTAMP),
    ('Noah Martinez', 'noah@example.com', 'password123', '789 Maple St', false, false, CURRENT_TIMESTAMP),
    ('Isabella Rodriguez', 'isabella@example.com', 'password456', '123 Cedar St', false, false, CURRENT_TIMESTAMP),
    ('William Hernandez', 'william@example.com', 'password789', '456 Pine St', false, false, CURRENT_TIMESTAMP),
    ('Sophia Lopez', 'sophia@example.com', 'passwordabc', '789 Cedar St', false, false, CURRENT_TIMESTAMP),
    ('Benjamin Lewis', 'benjamin@example.com', 'passworddef', '123 Elm St', false, false, CURRENT_TIMESTAMP),
    ('Charlotte Perez', 'charlotte@example.com', 'password123', '456 Pine St', false, false, CURRENT_TIMESTAMP),
    ('Mason Gonzalez', 'mason@example.com', 'password456', '789 Cedar St', false, false, CURRENT_TIMESTAMP),
    ('Amelia Moore', 'amelia@example.com', 'password789', '123 Oak St', false, false, CURRENT_TIMESTAMP),
    ('Ethan Watson', 'ethan@example.com', 'passwordabc', '456 Maple St', false, false, CURRENT_TIMESTAMP),
    ('Harper Cook', 'harper@example.com', 'passworddef', '789 Elm St', false, false, CURRENT_TIMESTAMP),
    ('Michael Brooks', 'michael@example.com', 'password123', '123 Pine St', false, false, CURRENT_TIMESTAMP),
    ('Evelyn Kelly', 'evelyn@example.com', 'password456', '456 Cedar St', false, false, CURRENT_TIMESTAMP),
    ('Alexander Price', 'alexander@example.com', 'password789', '789 Oak St', false, false, CURRENT_TIMESTAMP),
    ('Layla Hayes', 'layla@example.com', 'passwordabc', '123 Maple St', false, false, CURRENT_TIMESTAMP),
    ('Daniel Russell', 'daniel@example.com', 'passworddef', '456 Elm St', false, false, CURRENT_TIMESTAMP);


-- Query without index
EXPLAIN ANALYZE SELECT * FROM users WHERE address = '123 Main St';

-- Create an index on the email column
CREATE INDEX idx_users_address ON users (address);

SELECT 
  indexname, 
  indexdef 
FROM 
  pg_indexes 
WHERE 
  tablename = 'users';


-- Query with index
EXPLAIN ANALYZE SELECT * FROM Users WHERE address = '123 Main St';

```

### When Should Indexes be Avoided? (collected from tutorialspoint)

Although indexes are intended to enhance a database's performance, there are times when they should be avoided. The following guidelines indicate when the use of an index should be reconsidered −

- Indexes should not be used on small tables.

- Tables that have frequent, large batch update or insert operations.

- Indexes should not be used on columns that contain a high number of NULL values.

- Columns that are frequently manipulated should not be indexed.

## 34. How to Use pgAdmin

- you need to have access to psql dbms so make sure to have it already
- download and install pgAdmin
- create a server then connect to a database (if you do not have one then create a database)
- UI
- Run SQL
- SAVE FILE
- BROWSE OBJECT

## 35. PostgreSQL REST API

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

## 36. C# .NET Backend REST API

- Create ASP.NET Core Apps
- Understand REST APIs
- Implement CRUD Endpoints
- Data Transfer Objects (DTOs)
- Extension Methods
- Route Groups
- Handle Invalid Inputs
- Entity Framework Core
- Asynchornous Programming

### create first web api and folder structure

- what is API? why do we need API?
- HTTP Verbs + CRUD Operations
- HTTP Status Code

- `dotnet new list`
- As a beginner start with this command: `dotnet new web -o ecommerce-api`
- command `dotnet new webapi -o ecommerce-api`
- cmd+shift+p -> .NET: New Project + Enter
- check Program.cs

```cs
var builder = WebApplication.CreateBuilder(args);
// WebApplication is basically just host for http server where you can make http requets
var app = builder.Build();

app.MapGet("/", () => "Hello World!");

app.Run();
```

- check .csproj file -> where we will add all dependencies mostly

- appsettings.json vs appsettings.Development.json -> mainly for configuration

- launchSettings.json - profiles configuration for only local development not for production development

- obj file is the intermediate
- bin is the executeable
- how to build the project: go to root directory: dotnet buiild (ctrl+shift+B)
- how to run the app (F5) + install Jsonnet Language Server + select c# + http/default or go to solution explorer -> debug -> start without debugging
- how to run with terminal. go to root directory -> `dotnet run`
- auto sever restart `dotnet watch run`

### API, REST API

REST (Representational State Transfer) is an architectural style for designing networked applications. It relies on a stateless, client-server communication model and emphasizes the use of standard HTTP methods and status codes. REST APIs adhere to a set of constraints that define their architectural properties. These constraints, defined by Roy Fielding in his doctoral dissertation, help ensure that RESTful APIs are scalable, reliable, and maintainable. Let's explore these constraints with examples:

1. **Client-Server Architecture**:
   - Constraint: Separation of concerns between client and server.
   - Example: A web application (client) communicates with a server through HTTP requests. The client is responsible for presenting data to the user, while the server is responsible for processing requests and managing resources.

2. **Statelessness**:
   - Constraint: Each request from a client must contain all the information necessary for the server to fulfill the request. The server does not store any client state between requests.
   - Example: In a RESTful API, authentication tokens are sent with each request to authenticate the client. The server does not maintain session state for individual clients.

3. **Cacheability**:
   - Constraint: Responses from the server must explicitly indicate whether they can be cached by clients or not.
   - Example: The server includes cache-control headers in its HTTP responses to specify caching behavior. Clients can cache responses for a certain period to reduce the need for repeated requests.

4. **Uniform Interface**:
   - Constraint: The interface between client and server must be uniform, simplifying the architecture and promoting scalability.
   - Example:
     - Resource Identification: Each resource in the API is identified by a unique URI (Uniform Resource Identifier).
     - Resource Manipulation: Clients interact with resources through standard HTTP methods like GET, POST, PUT, DELETE.
     - Self-Descriptive Messages: Responses include metadata (e.g., content type, cache directives) to describe how to process the payload.
     - Hypermedia as the Engine of Application State (HATEOAS): Responses contain hyperlinks that allow clients to navigate the API dynamically.

5. **Layered System**:
   - Constraint: The architecture must support a hierarchical layered system, allowing intermediaries (e.g., proxies, gateways) to be inserted between clients and servers without affecting the overall behavior.
   - Example: A client sends a request to a load balancer, which forwards the request to one of several identical server instances. The load balancer acts as an intermediary, distributing incoming requests among the servers.

6. **Code on Demand (Optional)**:
   - Constraint: Servers can provide executable code (e.g., JavaScript) to clients for extended functionality, but it is optional.
   - Example: A web server may send client-side scripts (e.g., JavaScript functions) to a web browser as part of an HTML response. The browser can execute these scripts to enhance user interactivity.

These constraints ensure that RESTful APIs are scalable, reliable, and maintainable. By adhering to these principles, developers can design APIs that are easily understood, interoperable, and adaptable to changing requirements.

#### Install REST CLIENT for http requests

- create a ecommerce.http file `GET http://localhost:5277`

#### URL? best practices when naming URL

1. **URL:** `https://www.amazon.com/gp/product/B07H1DWFLG/ref=s9_acsd_hps_bw_c_x_3_w?pf_rd_m=ATVPDKIKX0DER&pf_rd_s=merchandised-search-4&pf_rd_r=EK5R9ET1VB7E0M6X23T3&pf_rd_t=101&pf_rd_p=5f6a5c92-95cb-486c-aa05-69e0e2efeb50&pf_rd_i=15240825011`
   - **Scheme:** `https`
   - **Authority:** `www.amazon.com`
   - **Path:** `/gp/product/B07H1DWFLG/ref=s9_acsd_hps_bw_c_x_3_w`
   - **Query Parameters:** `pf_rd_m=ATVPDKIKX0DER&pf_rd_s=merchandised-search-4&pf_rd_r=EK5R9ET1VB7E0M6X23T3&pf_rd_t=101&pf_rd_p=5f6a5c92-95cb-486c-aa05-69e0e2efeb50&pf_rd_i=15240825011`
   - **Fragment Identifier:** None

2. **URL:** `https://www.example.com/blog/post?id=123#comments`
   - **Scheme:** `https`
   - **Authority:** `www.example.com`
   - **Path:** `/blog/post`
   - **Query Parameters:** `id=123`
   - **Fragment Identifier:** `comments`

Best Practices for URL Naming:

1. **Use Descriptive Names:**
   - **Good Example:** `/products` - Clearly indicates that this endpoint deals with products.
   - **Bad Example:** `/data` - Vague and unclear.

2. **Use Plural Nouns for Collections:**
   - **Good Example:** `/users`, `/products` - Represents collections of resources.
   - **Bad Example:** `/user`, `/product` - Singular form is less intuitive for collections.

3. **Use Singular Nouns for Specific Resources:**
   - **Good Example:** `/user/{userId}`, `/product/{productId}` - Represents individual instances of resources.
   - **Bad Example:** `/users/{userId}`, `/products/{productId}` - Confusing plural form for specific resources.

4. **Use Hyphens for Readability:**
   - **Good Example:** `/product-categories`, `/order-items` - Improves readability.
   - **Bad Example:** `/productcategories`, `/orderitems` - Less readable and harder to parse.

5. **Avoid Hard-Coding IDs:**
   - **Good Example:** `/users/{username}` - Uses a meaningful identifier instead of a database ID.
   - **Bad Example:** `/users/{userId}` - Exposes internal implementation details.

6. **Versioning:**
   - **Good Example:** `/v1/products`, `/v2/products` - Includes version number for backward compatibility.
   - **Bad Example:** `/products/v1`, `/products?version=1` - Less standardized and harder to manage.

7. **Use Consistent Naming Conventions:**
   - **Good Example:** `/customers`, `/orders`, `/payments` - Consistent use of nouns for resources.
   - **Bad Example:** `/customer`, `/order`, `/pay` - Inconsistent naming convention.

8. **Limit URL Depth:**
   - **Good Example:** `/users/{userId}/orders` - Concise and avoids excessive nesting.
   - **Bad Example:** `/users/{userId}/orders/{orderId}/items` - Excessive nesting increases complexity.

9. **Avoid Verbs in URL Paths:**
   - **Good Example:** `POST /products` - Uses HTTP methods for actions instead of verbs in URL.
   - **Bad Example:** `/createProduct`, `/deleteOrder` - Verb usage makes URLs less RESTful.

10. **Use Subresources for Relationships:**

- **Good Example:** `/users/{userId}/orders`, `/products/{productId}/reviews` - Represents relationships between resources.
- **Bad Example:** `/userOrders`, `/productReviews` - Less intuitive and violates REST principles.

By following these best practices, API designers can create URL structures that are intuitive, consistent, and easy to understand, improving the developer experience and usability of the API.

### DTO (Data Transfer Objects)

- dto is just a reperesentation of the resource
- some pople might name as contracts
- create a folder called Dtos-> ProductDto.cs
- we will create record cause they are immutable (non changeable after creating)

```csharp
  namespace EcommerceAPI;

  public record class ProductDto
  (int Id, string Name, double Price);
```

### GET /products and /products{id}

- now inside Program.cs

```csharp
using EcommerceAPI;

var builder = WebApplication.CreateBuilder(args);

var app = builder.Build();


List<ProductDto> products = [

    new ProductDto(1, "Iphone 13", 350.25),
    new ProductDto(2, "Samsung", 325.25),
    new ProductDto(3, "IPhone 14", 225.25)
];

app.MapGet("/products", () => products);

app.MapGet("/products/{id}", (int id) =>
{
  var foundProduct = products.Find(product => product.Id == id);
  return foundProduct is null ? Results.NotFound() : Results.Ok(foundProduct);
}).WithName("GetProduct");
```

### how to create API response

```csharp
// first create the template of the response outside the class
public record ApiResponse<T>(T Data, string Message);

// now create the response
var response = new ApiResponse<ProductDto>(foundProduct, "Product found successfully");

// use the response
 return foundProduct is null ? Results.NotFound() : Results.Ok(response);

 // so finally
  app.MapGet("/products/{id}", (int id) =>
    {
      var foundProduct = products.Find(product => product.Id == id);
      if (foundProduct != null)
      {
        var response = new ApiResponse<ProductDto>(foundProduct, "Product found successfully");
        return foundProduct is null ? Results.NotFound() : Results.Ok(response);
      }
      else
      {
        return Results.NotFound("Product not found");
      }

    }).WithName("GetProduct");
```

### POST /products

- CreateProductDto.cs another record

The CreateProductDto record in your example is a data transfer object (DTO) used for representing the data needed to create a new product. It has two properties:

Name: Represents the name of the product.
Price: Represents the price of the product.

```csharp
// Dtos/CreateProductDto
namespace EcommerceAPI;

public record class CreateProductDto
(string Name, double Price);

app.MapPost("/products", (CreateProductDto newProduct) =>
{
 ProductDto product = new(
        products.Count + 1,
        newProduct.Name,
        newProduct.Price
      );
  products.Add(product);
  // return products;
  return Results.CreatedAtRoute("GetProduct", new { id = product.Id }, product);
});
```

### PUT /products/{id}

```csharp
app.MapPut("/products/{id}", (int id, UpdateProductDto updateProduct) =>
{
  // find existing product 
  var foundProductIndex = products.FindIndex(product => product.Id == id);
  if (foundProductIndex == -1)
  {
    return Results.NotFound(); // create or not create if it is not found based on your own expectation
  }
  else
  {
    products[foundProductIndex] = new ProductDto(id, updateProduct.Name, updateProduct.Price);
    return Results.NoContent();
  }
  // replace with update data
});
```

### DELETE /products/{id}

```csharp
app.MapDelete("/products/{id}", (int id) =>
{
  products.RemoveAll(product => product.Id == id);
  return Results.Ok();
});

```

### Extension, combine all the endpoints

- create an EndPoints folder and move codes

```csharp
// EndPoints/ProductEndPoits class
namespace EcommerceAPI;

public static class ProductEndpoints
{
  private static readonly List<ProductDto> products = [
    new ProductDto(1, "Iphone 13", 350.25),
    new ProductDto(2, "Samsung", 325.25),
    new ProductDto(3, "IPhone 14", 225.25)
  ];

  public static WebApplication MapProductsEndPoints(this WebApplication app)
  {

    app.MapGet("/products", () => products);

    app.MapGet("/products/{id}", (int id) =>
    {
      var foundProduct = products.Find(product => product.Id == id);
      return foundProduct is null ? Results.NotFound() : Results.Ok(foundProduct);
    }).WithName("GetProduct");

    app.MapPost("/products", (CreateProductDto newProduct) =>
    {
      ProductDto product = new(
        products.Count + 1,
        newProduct.Name,
        newProduct.Price
      );
      products.Add(product);
      // return products;
      return Results.CreatedAtRoute("GetProduct", new { id = product.Id }, product);
    });

    app.MapPut("/products/{id}", (int id, UpdateProductDto updateProduct) =>
    {
      // find existing product 
      var foundProductIndex = products.FindIndex(product => product.Id == id);
      if (foundProductIndex == -1)
      {
        return Results.NotFound(); // create or not create if it is not found based on your own expectation
      }
      else
      {
        products[foundProductIndex] = new ProductDto(id, updateProduct.Name, updateProduct.Price);
        return Results.NoContent();
      }
      // replace with update data
    });

   app.MapDelete("/products/{id}", (int id) =>
    {
        var productToRemove = products.Find(p => p.Id == id);
        if (productToRemove != null)
        {
            products.Remove(productToRemove);
            return Results.Ok("Product deleted successfully");
        }
        else
        {
            return Results.NotFound("Product not found");
        }
    });


    return app;

  }

}

// now Program.cs
using EcommerceAPI;

var builder = WebApplication.CreateBuilder(args);

var app = builder.Build();

app.MapProductsEndPoints();

app.Run();

```

### grouping routes

```csharp
namespace EcommerceAPI;

public record ApiResponse<T>(T Data, string Message);
public static class ProductEndpoints
{
  private static readonly List<ProductDto> products = [
    new ProductDto(1, "Iphone 13", 350.25),
    new ProductDto(2, "Samsung", 325.25),
    new ProductDto(3, "IPhone 14", 225.25)
  ];

  public static RouteGroupBuilder MapProductsEndPoints(this WebApplication app)
  {

    var group = app.MapGroup("products");

    // GET -> /products
    group.MapGet("/", () => products);

    // GET -> /products/1
    group.MapGet("/{id}", (int id) =>
    {
      var foundProduct = products.Find(product => product.Id == id);
      if (foundProduct != null)
      {
        var response = new ApiResponse<ProductDto>(foundProduct, "Product found successfully");
        return foundProduct is null ? Results.NotFound() : Results.Ok(response);
      }
      else
      {
        return Results.NotFound("Product not found");
      }

    }).WithName("GetProduct");

    // POST -> /products
    group.MapPost("/", (CreateProductDto newProduct) =>
    {
     ProductDto product = new(
        products.Count + 1,
        newProduct.Name,
        newProduct.Price
      );
      products.Add(product);
      // return products;
      return Results.CreatedAtRoute("GetProduct", new { id = product.Id }, product);
    });

    group.MapPut("/{id}", (int id, UpdateProductDto updateProduct) =>
    {
      // find existing product 
      var foundProductIndex = products.FindIndex(product => product.Id == id);
      if (foundProductIndex == -1)
      {
        return Results.NotFound(); // create or not create if it is not found based on your own expectation
      }
      else
      {
        products[foundProductIndex] = new ProductDto(id, updateProduct.Name, updateProduct.Price);
        return Results.NoContent();
      }
      // replace with update data
    });

    group.MapDelete("/{id}", (int id) =>
    {
      var productToRemove = products.Find(p => p.Id == id);
      if (productToRemove != null)
      {
        products.Remove(productToRemove);
        return Results.Ok("Product deleted successfully");
      }
      else
      {
        return Results.NotFound("Product not found");
      }
    });
    return group;
  }

}
```

### Validation with Data Annotation / Handling Invalid Inputs

- what happen if you do not pass product name and it creates the product? it should be a bad request 400
- add the data annotation to the DTOs
- add the nuget package (MinimalApis.Extensions) from the package manager (add the vsextension)

```csharp
using System.ComponentModel.DataAnnotations;

namespace EcommerceAPI;

public record class CreateProductDto
(
  [Required][StringLength(50)] string Name,
  [Range(1, 1000)] double Price
);

using System.ComponentModel.DataAnnotations;

namespace EcommerceAPI;

public record class UpdateProductDto
(
  [Required][StringLength(50)] string Name,
  [Range(1, 1000)] double Price
);

```

### CRUD operations in React Now

```csharp

```

### .NET Framework - Entity Framework core

Entity Framework Core (EF Core) is an object-relational mapping (ORM) framework developed by Microsoft for .NET applications. It provides a set of tools and libraries for developers to interact with relational databases using .NET objects.

ORM, or Object-Relational Mapping, is a programming technique that enables developers to work with relational databases using object-oriented programming languages like C#. ORM frameworks like Entity Framework Core allow developers to map database tables to .NET classes and properties, making it easier to query and manipulate data in the database without having to write SQL queries directly.

- REST API (C# Objects) - Entity Framrwork CORE - DB (Table)

- defining the data Model

```csharp
// create the Categories Table
namespace EcommerceAPI;

public class Categories
{
  public int Id { get; set; }
  public required string Name { get; set; }
  public required string Description { get; set; }

}

// create the Product Table
namespace EcommerceAPI;

public class Products
{
  public int Id { get; set; }
  // public string? Name { get; set; } (can have null)

  // public string? Name { get; set; } = string.Empty; (empty string)

  public required string Name { get; set; }
  public int Price { get; set; }

  public int CategoryId { get; set; }
  public Categories? Category { get; set; } // populate the Category for the product

}
```

- add a package for entity framework
  - `Npgsql.EntityFrameworkCore.PostgreSQL`
  - `dotnet add package Npgsql.EntityFrameworkCore.PostgreSQL --version 9.0.0-preview.3`

## 37. C# .NET REST API

### basic setup

- create, build and run a web api

  ```csharp
    dotnet new webapi -o api
    dotnet build
    dotnet run
    dotnet watch run
  ```

  ```csharp
  // clean the code
  var builder = WebApplication.CreateBuilder(args);

  // Add services to the container.
  // Learn more about configuring Swagger/OpenAPI at https://aka.ms/aspnetcore/swashbuckle
  builder.Services.AddEndpointsApiExplorer();
  builder.Services.AddSwaggerGen();

  var app = builder.Build();

  // Configure the HTTP request pipeline.
  if (app.Environment.IsDevelopment())
  {
      app.UseSwagger();
      app.UseSwaggerUI();
  }

  app.UseHttpsRedirection();


  app.Run();
  ```

- Swagger API Doc -> `http://localhost:5097/swagger/index.html`

- add few routes `/api/users`

- Model (Explain MVC)

  ```csharp
  public class User
  {
    public Guid UserId { get; set; }
    public required string Name { get; set; }
    public required string Email { get; set; }
    public required string Password { get; set; }
    public string Address { get; set; } = string.Empty;
    public string Image { get; set; } = string.Empty;
    public bool IsAdmin { get; set; }
    public bool IsBanned { get; set; }
    public DateTime CreatedAt { get; set; }
  }
  ```

- Controllers & Services (Explain MVC)

  ```csharp
  // Controllers/UserController.cs
  using System;
  using System.Collections.Generic;
  using System.Linq;
  using System.Threading.Tasks;
  using Microsoft.AspNetCore.Mvc;

  namespace api.Controllers
  {
      [ApiController]
      [Route("/api/users")]
      public class UserController : ControllerBase
      {
          private readonly UserService _userService;
          public UserController()
          {
              _userService = new UserService();
          }

          [HttpGet]
          public IActionResult GetAllUsers()
          {
              var users = _userService.GetAllUsersService();
              return Ok(users);
          }

          [HttpGet("{userId}")]
          public IActionResult GetUser(string userId)
          {
              if (!Guid.TryParse(userId, out Guid userIdGuid))
              {
                  return BadRequest("Invalid user ID Format");
              }
              var user = _userService.GetUserById(userIdGuid);
              if (user == null)
              {
                  return NotFound();
              }
              else
              {
                  return Ok(user);
              }

          }

          [HttpPost]
          public IActionResult CreateUser(User newUser)
          {
              var createdUser = _userService.CreateUserService(newUser);
              return CreatedAtAction(nameof(GetUser), new { userId = createdUser.UserId }, createdUser);
          }


          [HttpPut("{userId}")]
          public IActionResult UpdateUser(string userId, User updateUser)
          {
              if (!Guid.TryParse(userId, out Guid userIdGuid))
              {
                  return BadRequest("Invalid user ID Format");
              }
              var user = _userService.UpdateUserService(userIdGuid, updateUser);
              if (user == null)
              {
                  return NotFound();
              }
              return Ok(user);
          }


          [HttpDelete("{userId}")]
          public IActionResult DeleteUser(string userId)
          {
              if (!Guid.TryParse(userId, out Guid userIdGuid))
              {
                  return BadRequest("Invalid user ID Format");
              }
              var result = _userService.DeleteUserService(userIdGuid);
              if (!result)
              {
                  return NotFound();
              }
              return NoContent();
          }

      }
  }

  // Services/UserService.cs
  public class UserService
  {
    // users api 
    public static List<User> _users = new List<User>() {
      new User{
          UserId = Guid.Parse("75424b9b-cbd4-49b9-901b-056dd1c6a020"),
          Name = "John Doe",
          Email = "john@example.com",
          Password = "password123",
          Address = "123 Main St",
          IsAdmin = false,
          IsBanned = false,
          CreatedAt = DateTime.Now
      },
      new User{
          UserId = Guid.Parse("24508f7e-94ec-4f0b-b8d6-e8e16a9a3b29"),
          Name = "Alice Smith",
          Email = "alice@example.com",
          Password = "password456",
          Address = "456 Elm St",
          IsAdmin = false,
          IsBanned = false,
          CreatedAt = DateTime.Now
      },
      new User{
          UserId = Guid.Parse("87e5c4f3-d3e5-4e16-88b5-809b2b08b773"),
          Name = "Bob Johnson",
          Email = "bob@example.com",
          Password = "password789",
          Address = "789 Oak St",
          IsAdmin = false,
          IsBanned = false,
          CreatedAt = DateTime.Now
      }
  };

    public IEnumerable<User> GetAllUsersService()
    {
      return _users;
    }
    public User? GetUserById(Guid userId)
    {
      return _users.Find(user => user.UserId == userId);
    }
    public User CreateUserService(User newUser)
    {
      newUser.UserId = Guid.NewGuid();
      newUser.CreatedAt = DateTime.Now;
      _users.Add(newUser); // store this user in our database
      return newUser;
    }
    public User UpdateUserService(Guid userId, User updateUser)
    {
      var existingUser = _users.FirstOrDefault(u => u.UserId == userId);
      if (existingUser != null)
      {
        existingUser.Name = updateUser.Name;
        existingUser.Email = updateUser.Email;
        existingUser.Password = updateUser.Password;
        existingUser.Address = updateUser.Address;
        existingUser.Image = updateUser.Image;
        existingUser.IsAdmin = updateUser.IsAdmin;
        existingUser.IsBanned = updateUser.IsBanned;
      }
      return existingUser;
    }
    public bool DeleteUserService(Guid userId)
    {
      var userToRemove = _users.FirstOrDefault(u => u.UserId == userId);
      if (userToRemove != null)
      {
        _users.Remove(userToRemove);
        return true;
      }
      return false;
    }

  }
  ```

- add few packages and Update Program.cs file for using MVC

  ```csharp
  // dotnet add package Microsoft.AspNetCore.OData --version 8.0.0-preview3
  // dotnet add package Microsoft.AspNetCore.Mvc.NewtonsoftJson --version 6.0.0-preview.6.21355.2
  // dotnet add package Swashbuckle.AspNetCore --version 6.2.3

  var builder = WebApplication.CreateBuilder(args);

  builder.Services.AddEndpointsApiExplorer();
  builder.Services.AddSwaggerGen();
  builder.Services.AddControllers();

  var app = builder.Build();

  // Configure the HTTP request pipeline.
  if (app.Environment.IsDevelopment())
  {
      app.UseSwagger();
      app.UseSwaggerUI();
  }

  app.UseHttpsRedirection();
  app.MapControllers();
  app.Run();

  ```

- [Validation with Data Annotation](https://learn.microsoft.com/en-us/aspnet/mvc/overview/older-versions-1/models-data/validation-with-the-data-annotation-validators-cs)

  - add validation with data annotation

  ```csharp
    using System.ComponentModel.DataAnnotations;

    public class User
    {
      public Guid UserId { get; set; }
      [StringLength(50)]public required string Name { get; set; }

      [Required(ErrorMessage = "Email is required")]
      [EmailAddress(ErrorMessage = "Invalid email address")]
      public required string Email { get; set; }

      [Required(ErrorMessage = "Password is required")]
      [MinLength(6, ErrorMessage = "Password must be at least 6 characters long")]
      public required string Password { get; set; }
      public string Address { get; set; } = string.Empty;
      public string Image { get; set; } = string.Empty;
      public bool IsAdmin { get; set; }
      public bool IsBanned { get; set; }
      public DateTime CreatedAt { get; set; }

      // [Range(1,100, ErrorMessage = "price has to be between 1 to 1000")]
  }
  ```

  - add MinimalApis.Extenstion by using nuget gallery extension in vscode

    ```csharp
    // to all the endpoints in Program.cs

    // app.MapControllers().WithParameterValidation();

    // to individual endpoints in Program.cs file
    // app.MapGet("/api/users", () => new UserController().GetAllUsers()).WithParameterValidation();
    // app.MapGet("/api/users/{userId}", (Guid userId) => new UserController().GetUser(userId)).WithParameterValidation();
    // app.MapPost("/api/users", (User newUser) => new UserController().CreateUser(newUser)).WithParameterValidation();
    // app.MapPut("/api/users/{userId}", (Guid userId, User updateUser) => new UserController().UpdateUser(userId, updateUser)).WithParameterValidation();
    // app.MapDelete("/api/users/{userId}", (Guid userId) => new UserController().DeleteUser(userId)).WithParameterValidation();
    ```

- Update the User

  ```csharp
     public Task<User?> UpdateUserService(Guid userId, User updateUser)
      {
        var existingUser = _users.FirstOrDefault(u => u.UserId == userId);
        if (existingUser != null)
        {
          existingUser.Name = updateUser.Name ?? existingUser.Name;
          existingUser.Email = updateUser.Email ?? existingUser.Email;
          existingUser.Password = updateUser.Password ?? existingUser.Password;
          existingUser.Address = updateUser.Address ?? existingUser.Address;
          existingUser.Image = updateUser.Image ?? existingUser.Image;
          // Check if IsAdmin is provided in updateUser, otherwise keep the existing value
          if (updateUser.IsAdmin != default)
          {
            existingUser.IsAdmin = updateUser.IsAdmin;
          }

          // Check if IsBanned is provided in updateUser, otherwise keep the existing value
          if (updateUser.IsBanned != default)
          {
            existingUser.IsBanned = updateUser.IsBanned;
          }
        }

        return Task.FromResult(existingUser);
      }

  ```

- Add asynchronous programming

  ```csharp
    using System;

    using System.Collections.Generic;
    using System.Linq;
    using System.Threading.Tasks;
    using Microsoft.AspNetCore.Mvc;

    namespace api.Controllers
    {
        [ApiController]
        [Route("/api/users")]
        public class UserController : ControllerBase
        {
            private readonly UserService _userService;
            public UserController()
            {
                _userService = new UserService();
            }

            [HttpGet]
            public async Task<IActionResult> GetAllUsers()
            {
                var users = await _userService.GetAllUsersService();
                return Ok(users);
            }

            [HttpGet("{userId}")]
            public async Task<IActionResult> GetUser(string userId)
            {
                if (!Guid.TryParse(userId, out Guid userIdGuid))
                {
                    return BadRequest("Invalid user ID Format");
                }
                var user = await _userService.GetUserById(userIdGuid);
                if (user == null)
                {
                    return NotFound();
                }
                else
                {
                    return Ok(user);
                }
            }

            [HttpPost]
            public async Task<IActionResult> CreateUser(User newUser)
            {
                var createdUser = await _userService.CreateUserService(newUser);
                return CreatedAtAction(nameof(GetUser), new { userId = createdUser.UserId }, createdUser);
            }

            [HttpPut("{userId}")]
            public async Task<IActionResult> UpdateUser(string userId, User updateUser)
            {
                if (!Guid.TryParse(userId, out Guid userIdGuid))
                {
                    return BadRequest("Invalid user ID Format");
                }
                var user = await _userService.UpdateUserService(userIdGuid, updateUser);
                if (user == null)
                {
                    return NotFound();
                }
                return Ok(user);
            }

            [HttpDelete("{userId}")]
            public async Task<IActionResult> DeleteUser(string userId)
            {
                if (!Guid.TryParse(userId, out Guid userIdGuid))
                {
                    return BadRequest("Invalid user ID Format");
                }
                var result = await _userService.DeleteUserService(userIdGuid);
                if (!result)
                {
                    return NotFound();
                }
                return NoContent();
            }
        }
    }
  ```

- handling exceptions

  ```csharp
     public async Task<IActionResult> GetAllUsers()
        {
            try
            {
                var users = await _userService.GetAllUsersService();
                if (users == null || !users.Any())
                {
                    return NoContent(); // Return 204 No Content if there are no users
                }
                return Ok(new { message = "Users retrieved successfully", data = users });
            }
            catch (Exception ex)
            {

                // Log the exception for debugging and monitoring purposes
                Console.WriteLine($"An error occurred while retrieving users: {ex.Message}");

                // Return a server error response with a meaningful error message
                return StatusCode(500, "An error occurred while processing your request. Please try again later.");
            }
        }
  ```

- customizing the success and error response

  ```csharp
  //Helpers/ErrorResponse.cs
  public class ErrorResponse

  {
    public bool Success { get; set; } = false;
    public string? Message { get; set; }
  }


  //Helpers/SuccessResponse.cs
  public class SuccessResponse<T>

  {
      public bool Success { get; set; } = true;
      public string? Message { get; set; }
      public T? Data { get; set; }
  }

  ```

- update the UserController now

  ```csharp
  using System;
  using System.Collections.Generic;
  using System.Linq;
  using System.Threading.Tasks;
  using Microsoft.AspNetCore.Mvc;

  namespace api.Controllers
  {
      [ApiController]
      [Route("/api/users")]
      public class UserController : ControllerBase
      {
          private readonly UserService _userService;

          public UserController()
          {
              _userService = new UserService();
          }

          [HttpGet]
          public async Task<IActionResult> GetAllUsers()
          {
              try
              {
                  var users = await _userService.GetAllUsersService();
                  if (users == null || !users.Any())
                  {
                      return NoContent(); // Return 204 No Content if there are no users
                  }
                  return Ok(new SuccessResponse<IEnumerable<User>>
                  {
                      Success = true,
                      Message = "Users retrieved successfully",
                      Data = users
                  });
              }
              catch (Exception ex)
              {
                  // Log the exception for debugging and monitoring purposes
                  Console.WriteLine($"An error occurred while retrieving users: {ex.Message}");

                  // Return a server error response with a meaningful error message
                  return StatusCode(500, new ErrorResponse
                  {
                      Success = false,
                      Message = "An error occurred while processing your request. Please try again later."
                  });
              }
          }

          [HttpGet("{userId}")]
          public async Task<IActionResult> GetUser(string userId)
          {
              if (!Guid.TryParse(userId, out Guid userIdGuid))
              {
                  return BadRequest("Invalid user ID Format");
              }

              try
              {
                  var user = await _userService.GetUserById(userIdGuid);
                  if (user == null)
                  {
                      return NotFound(new ErrorResponse
                      {
                          Success = false,
                          Message = "User not found"
                      });
                  }
                  else
                  {
                      return Ok(new SuccessResponse<User>
                      {
                          Success = true,
                          Message = "User retrieved successfully",
                          Data = user
                      });
                  }
              }
              catch (Exception ex)
              {
                  // Log the exception for debugging and monitoring purposes
                  Console.WriteLine($"An error occurred while retrieving user: {ex.Message}");

                  // Return a server error response with a meaningful error message
                  return StatusCode(500, new ErrorResponse
                  {
                      Success = false,
                      Message = "An error occurred while processing your request. Please try again later."
                  });
              }
          }

          [HttpPost]
          public async Task<IActionResult> CreateUser(User newUser)
          {
              try
              {
                  var createdUser = await _userService.CreateUserService(newUser);
                  return CreatedAtAction(nameof(GetUser), new { userId = createdUser.UserId }, new SuccessResponse<User>
                  {
                      Success = true,
                      Message = "User created successfully",
                      Data = createdUser
                  });
              }
              catch (Exception ex)
              {
                  // Log the exception for debugging and monitoring purposes
                  Console.WriteLine($"An error occurred while creating user: {ex.Message}");

                  // Return a server error response with a meaningful error message
                  return StatusCode(500, new ErrorResponse
                  {
                      Success = false,
                      Message = "An error occurred while processing your request. Please try again later."
                  });
              }
          }

          [HttpPut("{userId}")]
          public async Task<IActionResult> UpdateUser(string userId, User updateUser)
          {
              if (!Guid.TryParse(userId, out Guid userIdGuid))
              {
                  return BadRequest("Invalid user ID Format");
              }

              try
              {
                  var user = await _userService.UpdateUserService(userIdGuid, updateUser);
                  if (user == null)
                  {
                      return NotFound(new ErrorResponse
                      {
                          Success = false,
                          Message = "User not found"
                      });
                  }
                  else
                  {
                      return Ok(new SuccessResponse<User>
                      {
                          Success = true,
                          Message = "User updated successfully",
                          Data = user
                      });
                  }
              }
              catch (Exception ex)
              {
                  // Log the exception for debugging and monitoring purposes
                  Console.WriteLine($"An error occurred while updating user: {ex.Message}");

                  // Return a server error response with a meaningful error message
                  return StatusCode(500, new ErrorResponse
                  {
                      Success = false,
                      Message = "An error occurred while processing your request. Please try again later."
                  });
              }
          }

          [HttpDelete("{userId}")]
          public async Task<IActionResult> DeleteUser(string userId)
          {
              if (!Guid.TryParse(userId, out Guid userIdGuid))
              {
                  return BadRequest("Invalid user ID Format");
              }

              try
              {
                  var result = await _userService.DeleteUserService(userIdGuid);
                  if (!result)
                  {
                      return NotFound(new ErrorResponse
                      {
                          Success = false,
                          Message = "User not found"
                      });
                  }
                  else
                  {
                      return NoContent(); // Return 204 No Content if user deleted successfully
                  }
              }
              catch (Exception ex)
              {
                  // Log the exception for debugging and monitoring purposes
                  Console.WriteLine($"An error occurred while deleting user: {ex.Message}");

                  // Return a server error response with a meaningful error message
                  return StatusCode(500, new ErrorResponse
                  {
                      Success = false,
                      Message = "An error occurred while processing your request. Please try again later."
                  });
              }
          }
      }
  }
  
  ```

### Category API

- Add Slug to CategoryModel

```csharp
public class Category
{
  public Guid CategoryId { get; set; }

  [Required(ErrorMessage = "Category Name is required")]
  [MaxLength(32, ErrorMessage = "Category Name must be less than 32 characters")]
  public required string Name { get; set; }
  public string Slug { get; set; } = string.Empty;

  [MaxLength(255, ErrorMessage = "Category Description must be less than 255 characters")]
  public string Description { get; set; } = string.Empty;
  public DateTime CreatedAt { get; set; }
}
```

- Add slug to the exisiting categories and when creating the Category in CategoryService.cs

```csharp
  private string GenerateSlug(string name)
    {
        // Convert the category name to lowercase and replace spaces with dashes
        return name.ToLower().Replace(" ", "-");
    }
  
   public Category CreateCategoryService(Category newCategory)
    {
        newCategory.CategoryId = Guid.NewGuid();
        newCategory.CreatedAt = DateTime.Now;
        newCategory.Slug = GenerateSlug(newCategory.Name);
        _categories.Add(newCategory); // store this user in our database
        return newCategory;
    }
```

- Update the CategoryController with exception handling

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.AspNetCore.Mvc;

namespace api.Controllers
{
    [ApiController]
    [Route("/api/categories")]
    public class CategoryController : ControllerBase
    {
        private readonly CategoryService _categoryService;
        public CategoryController()
        {
            _categoryService = new CategoryService();
        }

        [HttpGet]
        public IActionResult GetAllCategories()
        {
            try
            {
                var categories = _categoryService.GetAllCategoryService();
                if (categories == null || !categories.Any())
                {
                    return NoContent(); // Return 204 No Content if there are no categories
                }
                return Ok(new SuccessResponse<IEnumerable<Category>>
                {
                    Success = true,
                    Message = "Categories retrieved successfully",
                    Data = categories
                });
            }
            catch (Exception ex)
            {
                // Log the exception for debugging and monitoring purposes
                Console.WriteLine($"An error occurred while retrieving categories: {ex.Message}");

                // Return a server error response with a meaningful error message
                return StatusCode(500, new ErrorResponse
                {
                    Success = false,
                    Message = "An error occurred while processing your request. Please try again later."
                });
            }
        }

        [HttpGet("{categoryId}")]
        public IActionResult GetCategory(string categoryId)
        {
            if (!Guid.TryParse(categoryId, out Guid categoryIdGuid))
            {
                return BadRequest(new ErrorResponse
                {
                    Success = false,
                    Message = "Invalid category ID Format"
                });
            }

            var category = _categoryService.GetCategoryById(categoryIdGuid);
            if (category == null)
            {
                return NotFound(new ErrorResponse
                {
                    Success = false,
                    Message = "Category not found"
                });
            }
            else
            {
                return Ok(new SuccessResponse<Category>
                {
                    Success = true,
                    Message = "Category retrieved successfully",
                    Data = category
                });
            }
        }

        [HttpPost]
        public IActionResult CreateCategory(Category newCategory)
        {
            try
            {
                var createdCategory = _categoryService.CreateCategoryService(newCategory);
                return CreatedAtAction(nameof(GetCategory), new { categoryId = createdCategory.CategoryId }, new SuccessResponse<Category>
                {
                    Success = true,
                    Message = "Category created successfully",
                    Data = createdCategory
                });
            }
            catch (Exception ex)
            {
                // Log the exception for debugging and monitoring purposes
                Console.WriteLine($"An error occurred while creating the category: {ex.Message}");

                // Return a server error response with a meaningful error message
                return StatusCode(500, new ErrorResponse
                {
                    Success = false,
                    Message = "An error occurred while processing your request. Please try again later."
                });
            }
        }

        [HttpPut("{categoryId}")]
        public IActionResult UpdateCategory(string categoryId, Category updateCategory)
        {
            if (!Guid.TryParse(categoryId, out Guid categoryIdGuid))
            {
                return BadRequest(new ErrorResponse
                {
                    Success = false,
                    Message = "Invalid category ID Format"
                });
            }

            try
            {
                var category = _categoryService.UpdateCategoryService(categoryIdGuid, updateCategory);
                if (category == null)
                {
                    return NotFound(new ErrorResponse
                    {
                        Success = false,
                        Message = "Category not found"
                    });
                }
                else
                {
                    return Ok(new SuccessResponse<Category>
                    {
                        Success = true,
                        Message = "Category updated successfully",
                        Data = category
                    });
                }
            }
            catch (Exception ex)
            {
                // Log the exception for debugging and monitoring purposes
                Console.WriteLine($"An error occurred while updating the category: {ex.Message}");

                // Return a server error response with a meaningful error message
                return StatusCode(500, new ErrorResponse
                {
                    Success = false,
                    Message = "An error occurred while processing your request. Please try again later."
                });
            }
        }

        [HttpDelete("{categoryId}")]
        public IActionResult DeleteCategory(string categoryId)
        {
            if (!Guid.TryParse(categoryId, out Guid categoryIdGuid))
            {
                return BadRequest(new ErrorResponse
                {
                    Success = false,
                    Message = "Invalid category ID Format"
                });
            }

            try
            {
                var result = _categoryService.DeleteCategoryService(categoryIdGuid);
                if (!result)
                {
                    return NotFound(new ErrorResponse
                    {
                        Success = false,
                        Message = "Category not found"
                    });
                }
                else
                {
                    return NoContent();
                }
            }
            catch (Exception ex)
            {
                // Log the exception for debugging and monitoring purposes
                Console.WriteLine($"An error occurred while deleting the category: {ex.Message}");

                // Return a server error response with a meaningful error message
                return StatusCode(500, new ErrorResponse
                {
                    Success = false,
                    Message = "An error occurred while processing your request. Please try again later."
                });
            }
        }
    }
}

```

- add rules to the endpoint

  In ASP.NET Core routing, you can specify various constraints and rules for route parameters to ensure that they match specific patterns or conditions. Some commonly used rules include:

  1. **Type Constraints**: As shown in `[HttpGet("{categoryId:guid}")]`, you can specify the type of the route parameter. In this case, `:guid` ensures that the `categoryId` route parameter must be a valid GUID.

  2. **Length Constraints**: You can specify the length constraints for string route parameters using `{parameter:length(min,max)}`. For example, `{slug:length(1,100)}` ensures that the `slug` route parameter length must be between 1 and 100 characters.

  3. **Regular Expression Constraints**: You can use regular expressions to specify more complex constraints for route parameters. For example, `{id:regex(\d{1,4})}` ensures that the `id` route parameter must be a string of 1 to 4 digits.

  4. **Optional Parameters**: You can mark route parameters as optional by adding a `?` suffix. For example, `{id?}` indicates that the `id` route parameter is optional.

  5. **Custom Constraints**: You can define custom constraint classes that implement `IRouteConstraint` interface and use them in routing. This allows you to define custom logic to determine if a route parameter is valid or not.

  These are some common rules used for routing in ASP.NET Core. You can mix and match these rules as needed to define precise routing patterns for your application's endpoints.

  To ensure that a route parameter consists of alphanumeric characters (0-9 and a-z) in ASP.NET Core routing, you can use a regular expression constraint. Here's how you can specify such a constraint:

```csharp
[HttpGet("{slug:regex(^[[0-9a-z]]+$)}")]
public IActionResult GetCategoryBySlug(string slug)
{
    // Your action logic here
}
```

In the above example:

- `{slug:regex(^[[0-9a-z]]+$)}` specifies the route parameter `slug` with a regular expression constraint. The `^` and `$` symbols indicate the start and end of the string, respectively. `[0-9a-z]` specifies that the characters must be alphanumeric (0-9 and a-z).

This constraint ensures that the `slug` route parameter consists only of alphanumeric characters (0-9 and a-z). If the parameter does not match this pattern, the route will not match, and the request will not be routed to this action method.

- get category by slug

```csharp
  public Category GetCategoryBySlug(string slug)
  {
      // Assuming _categories is your list of categories
      return _categories.FirstOrDefault(category => category.Slug == slug);
  }

```

- how to receieve query parameter with FormQuery

  ```csharp
  // https://example.com/api/products?page=1&pageSize=10
  using Microsoft.AspNetCore.Mvc;

  using Microsoft.AspNetCore.Http;

  namespace YourNamespace.Controllers
  {
      [ApiController]
      [Route("api/[controller]")]
      public class ProductController : ControllerBase
      {
          [HttpGet]
          public IActionResult GetProducts([FromQuery] int page = 1, [FromQuery] int pageSize = 10)
          {
              // Get the values of the query parameters
              int pageNumber = page; // Default value is 1 if not specified
              int itemsPerPage = pageSize; // Default value is 10 if not specified

              // Use the page and pageSize values to implement pagination logic
              // For example, you might use these values to retrieve products from a database

              return Ok($"Retrieving products for page {pageNumber} with {itemsPerPage} items per page.");
          }
      }
  }
  
  ```

### Product API

- ProductModel

```csharp
using System.ComponentModel.DataAnnotations;

public class Product
{
  public Guid ProductId { get; set; }
  public required string Name { get; set; }

  [Required(ErrorMessage = "Price is required")]
  [Range(0, double.MaxValue, ErrorMessage = "Price must be a positive number")]
  public required decimal Price { get; set; }
  public string Image { get; set; } = string.Empty;
  public string Description { get; set; } = string.Empty;
  public required int Quantity { get; set; }
  public required int Sold { get; set; } = 0;
  public required decimal Shipping { get; set; }

  [Required(ErrorMessage = "CategoryId is required")]
  public required Guid CategoryId { get; set; }
  public Category? category { get; set; }

  public DateTime CreatedAt { get; set; }
}
```

- ProductController
- ProductService

### Order API

- OrderModel
- OrderController
- OrderService
