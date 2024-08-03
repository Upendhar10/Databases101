# Data Definition Language

- Data Definition Language (DDL) is used to define and manage the structure of database objects such as tables, indexes, and schemas.
- DDL commands are concerned with the structure of the database itself.
- They are used to create, modify, and delete these database objects

### 1. CREATE Command

- The CREATE command is used to create new database objects such as tables, indexes, views, schemas, etc.

  ```sql
  CREATE TABLE employees (
      employee_id INT PRIMARY KEY,
      first_name VARCHAR(50),
      last_name VARCHAR(50),
      hire_date DATE,
      salary DECIMAL(10, 2)
  );
  ```

### 2. ALTER Command

- The ALTER command is used to modify the structure of an existing database object.
- This can include adding, deleting, or modifying columns in a table, or adding and removing constraints.

  **1. Adding a new column**

  ```sql
  ALTER TABLE employees
  ADD email VARCHAR(100);
  ```

  **2. Modifying a Column:**

  ```sql
  ALTER TABLE employees
  MODIFY salary DECIMAL(12, 2);
  ```

  **3. Dropping a Column:**

  ```sql
  ALTER TABLE employees
  DROP COLUMN email;
  ```

  **4. Adding a Constraint:**

  ```sql
  ALTER TABLE employees
  ADD CONSTRAINT chk_salary CHECK (salary > 0);
  ```

### 3. DROP Command

- The DROP command is used to delete database objects such as tables, indexes, views, etc.
- This action is irreversible.

  ```sql
  DROP TABLE employees;
  ```

### 4. TRUNCATE Command

- The TRUNCATE command is used to delete all rows from a table without removing the table structure.
- This operation is fast and cannot be rolled back in some databases because it doesn't log individual row deletions.

  ```sql
  TRUNCATE TABLE employees;
  ```

### 5. RENAME Command

- The RENAME command is used to change the name of a database object.

  ```sql
  ALTER TABLE employees
  RENAME TO staff;
  ```

## Data Types :

- Data types in SQL define the type of data that can be stored in a column.

  **1. Numeric Data Types:**

  - INT: Integer values.
  - FLOAT: Floating-point numbers.
  - DECIMAL: Fixed-point numbers, useful for precise calculations, typically in financial applications.
    > DECIMAL(p, s), NUMERIC(p, s) where, p = precision and s = scale

  **2. Character Data Types:**

  - CHAR: Fixed-length character strings.
  - VARCHAR: Variable-length character strings.

## Constraints :

- Constraints in SQL are used to specify rules for data in a table.
- These rules ensure the integrity and accuracy of the data.

  **1. PRIMARY KEY:**

  - Ensures that each value in a column or set of columns is unique and not null.
  - This uniquely identifies each row in a table.

    ```sql
    CREATE TABLE employees (
        id INT PRIMARY KEY,
        name VARCHAR(100)
    );
    ```

  **2. FOREIGN KEY:**

  - Ensures that the value in a column (or a set of columns) matches values in another table, establishing a relationship between tables.

    ```sql
    CREATE TABLE orders (
        order_id INT PRIMARY KEY,
        customer_id INT,
        FOREIGN KEY (customer_id) REFERENCES customers(id)
    );
    ```

  **3. NOT NULL :**

  - Ensures that a column cannot have a NULL value.

    ```sql
    CREATE TABLE products (
        product_id INT PRIMARY KEY,
        product_name VARCHAR(100) NOT NULL
    );
    ```
