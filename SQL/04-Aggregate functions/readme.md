# Aggregate functions in SQL

- Aggregate functions in SQL are used to perform calculations on a set of values and return a single value.
- These functions are commonly used with the GROUP BY clause to perform calculations on groups of rows.
- They are essential for summarizing data and generating reports.

#### **1. COUNT() Function**

- The COUNT() function returns the number of rows that match a specified condition.
- Syntax:

  ```sql
  SELECT COUNT(column_name)
  FROM table_name
  WHERE condition;
  ```

- Example:

  ```sql
  SELECT COUNT(*) AS total_employees
  FROM employees;
  ```

  - Explanation:
    - This query returns the total number of employees in the employees table.

#### **2. SUM() Function**

- The SUM() function returns the total sum of a numeric column.

- Syntax:

  ```sql
  SELECT SUM(column_name)
  FROM table_name
  WHERE condition;

  ```

- Example:

  ```sql
  SELECT SUM(salary) AS total_salaries
  FROM employees;

  ```

  - Explanation:
    - This query returns the total sum of all salaries in the employees table.

#### **3. AVG() Function**

- The AVG() function returns the average value of a numeric column.

- Syntax:

  ```sql
  SELECT AVG(column_name)
  FROM table_name
  WHERE condition;
  ```

- Example:

  ```sql
  SELECT AVG(salary) AS average_salary
  FROM employees;
  ```

  - Explanation:
    - This query returns the average salary of employees in the employees table

#### **4. MIN() Function**

- The MIN() function returns the smallest value in a specified column.

- Syntax:

  ```sql
  SELECT MIN(column_name)
  FROM table_name
  WHERE condition;
  ```

- Example:

  ```sql
  SELECT MIN(salary) AS lowest_salary
  FROM employees;
  ```

  - Explanation:
    - This query returns the smallest salary in the employees table.

#### **4. MAX() Function**

- The MAX() function returns the largest value in a specified column.

- Syntax:

  ```sql
  SELECT MAX(column_name)
  FROM table_name
  WHERE condition;
  ```

- Example:

  ```sql
  SELECT MAX(salary) AS Highest_salary
  FROM employees;
  ```

  - Explanation:
    - This query returns the highest salary in the employees table.

# 

#### **SELECT with GROUP BY clause**

- The **GROUP BY** clause groups rows that have the same values in specified columns into summary rows.
- It is often used with aggregate functions (COUNT, MAX, MIN, SUM, AVG).

- Syntax :

```sql
SELECT column1, aggregate_function(column2)
FROM table_name
GROUP BY column1, column2, ...;
```

- Example :

```sql
SELECT department_id, COUNT(*) AS num_employees
FROM employees
GROUP BY department_id;
```

- Explanation:
  - This query groups the rows by department_id and calculates the number of employees in each department.

#### **SELECT with HAVING clause**

- The `HAVING` clause is used to filter groups created by the GROUP BY clause based on a condition.
- It is similar to the `WHERE` clause, but it is used for filtering groups rather than individual rows.

- Syntax:

```sql
SELECT column1, aggregate_function(column2)
FROM table_name
GROUP BY column1, column2, ...
HAVING condition;
```

- Example:

```sql
SELECT department_id, AVG(salary) AS avg_salary
FROM employees
GROUP BY department_id
HAVING AVG(salary) > 60000;
```

- Explanation:
  - This query groups the rows by department_id, calculates the average salary for each department, and then filters the groups to include only those with an average salary greater than 60,000.
