# Data Manipulation Language

- DML is a subset of SQL used to insert, update, delete, and retrieve data within database tables.
- DML commands are essential for managing data stored in a database, allowing users to perform CRUD (Create, Read, Update, Delete) operations.

### 1. INSERT Command

- The INSERT command is used to add new rows of data to a table.

- Syntax :

  ```sql
  INSERT INTO table_name (column1, column2, column3, ...)
  VALUES (value1, value2, value3, ...);
  ```

- Examples :

  ```sql
  -- single row
  INSERT INTO employees (employee_id, first_name, last_name, hire_date, salary)
  VALUES (1, 'John', 'Doe', '2020-01-15', 60000);

  -- multiple rows at a time
  INSERT INTO employees (employee_id, first_name, last_name, hire_date, salary)
  VALUES
    (2, 'Jane', 'Smith', '2020-03-22', 75000),
    (3, 'Emily', 'Jones', '2020-05-30', 50000);
  ```

### 2. UPDATE Command

- The UPDATE command is used to modify existing records in a table.
- Syntax :

  ```sql
  UPDATE table_name
  SET column1 = value1, column2 = value2, ...
  WHERE condition;
  ```

- Example :

  ```sql
  -- updating single column value
  UPDATE employees
  SET salary = 65000
  WHERE employee_id = 1;

  -- updating multiple column values at once
  UPDATE employees
  SET salary = 70000, hire_date = '2021-01-01'
  WHERE employee_id = 2;
  ```

### 3. DELETE Command

- The DELETE command is used to remove existing records from a table.
- Here, WHERE is a clause.
- Syntax :

  ```sql
  DELETE FROM table_name
  WHERE condition;
  ```

- Example :

  ```sql
  -- deleting single record
  DELETE FROM employees
  WHERE employee_id = 3;

  -- deleting entire records at once
  DELETE FROM employees;

  -- Note: Use caution when deleting all records as this operation cannot be undone without a backup.
  ```

### 4. SELECT Command

- The SELECT command is used to retrieve data from one or more tables.
- It is the most commonly used DML command and can include various clauses to filter, sort, and group data.

- Syntax :
  ```sql
  SELECT columns FROM table_name;
  ```
- Example :

  ```sql
  SELECT first_name, last_name, salary
  FROM employees;
  ```

  #### **SELECT with WHERE clause**

  - The `WHERE` clause is used to filter records based on specific conditions.
  - It is applied before any grouping or aggregation.
  - Syntax :

  ```sql
  SELECT column1, column2, ...
  FROM table_name
  WHERE condition;
  ```

  - Example :

  ```sql
  SELECT first_name, last_name, salary
  FROM employees
  WHERE salary > 50000;

  ```

  - Explanation:
    - This query selects the first name, last name, and salary of employees whose salary is greater than 50,000.
    - The WHERE clause filters the rows based on the specified condition before the data is processed further.

  #### **SELECT with ORDER BY clause**

  - The `ORDER BY` clause is used to sort the result set of a query by one or more columns.
  - By default, it sorts in ascending order, but it can also sort in descending order.

  - Syntax :

  ```sql
  SELECT column1, column2, ...
  FROM table_name
  ORDER BY column1 [ASC|DESC], column2 [ASC|DESC], ...;
  ```

  - Example :

  ```sql
  SELECT first_name, last_name, salary
  FROM employees
  ORDER BY salary DESC;
  ```

  - Explaination :
    - This query selects the first name, last name, and salary of all employees and sorts the result set by salary in descending order.
