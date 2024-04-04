**Concept: SQL Subqueries**

**Section 1: Introduction**

**What are Subqueries?**

* Subqueries are embedded queries within another query.
* They add additional filtering or manipulation to the main query.

**How SQL Processes Subqueries:**

* The subquery is executed first.
* Its result is used to filter or modify the main query.

**Section 2: Types of Subqueries**

**Scalar Subqueries:**
* Return a single value (e.g., maximum, minimum, count).
* Syntax: `SELECT (subquery)`

**Row Subqueries:**
* Return one or more rows.
* Syntax: `SELECT * FROM (subquery)`

**Table Subqueries:**
* Create a temporary table that can be referenced in the main query.
* Syntax: `(subquery) AS [alias]`

**Section 3: Common Uses of Subqueries**

**Filter Data:**
* Limit results based on conditions in the subquery.
* Example: `SELECT * FROM employees WHERE salary > (SELECT MAX(salary) FROM employees)`

**Group Data:**
* Combine data from multiple subqueries.**Group Data:**
* Combine data from multiple subqueries.
* Example: `SELECT SUM(sales) FROM (SELECT sales FROM orders WHERE product_id = 1) AS orders_product1`

**Create Temporary Tables:**
* Store intermediate results for complex operations.
* Example: `(SELECT * FROM customers WHERE city = 'New York') AS new_york_customers`

**Section 4: Where to Use Subqueries**

**SQL Clauses:**
* WHERE
* HAVING
* FROM

**SQL Commands:**
* SELECT
* INSERT
* UPDATE
* DELETE**Interactive Online Learning: Brilliant**

### Key Concepts

- Platform: Brilliant is an online platform offering interactive learning experiences.
- Subjects: Covers a wide range of subjects, including math, science, and computer science.
- Approach: Emphasizes interactive, visually appealing courses.

### Features

#### Visual and Interactive:
- Courses are designed to engage visual learners.
- Learners engage with puzzles, questions, and problems related to the concepts.

#### Free Access:
- Users can register for free to access basic content.- Users can register for free to access basic content.

#### Premium Subscription:
- Annual subscription unlocks additional features, including:
 - Unlimited access to all courses
 - Personalized learning paths
 - Progress tracking and analytics

### Benefits for Visual Learners

- Engaging format helps learners retain information better.
- Interactive exercises reinforce understanding.
- Puzzles and questions develop critical thinking skills.

### How to Use Brilliant

1. **Sign Up:** Use the provided link to create a free account.
2. **Choose a Course:** Explore the catalog and select a course that aligns with your interests.
3. **Start Learning:** Engage with the interactive content, solve puzzles, and answer questions.
4. **Track Your Progress:** Monitor your understanding and identify areas for improvement.
5. **Consider Premium:** If you want to unlock premium features, consider subscribing for additional benefits.

### Example: Math Course

**Topic:** Calculus

**Interactive Activity:****Topic:** Calculus

**Interactive Activity:**

- A step-by-step simulation demonstrates the concept of limits.
- Learners can adjust parameters and see the impact on the limit's value.

**Benefits:**

- Visualizes the abstract concept of limits.
- Allows learners to explore the concept hands-on.
- Reinforces the understanding of the limit's behavior.

### Conclusion

Brilliant provides an innovative learning platform that caters to visual learners. Through interactive courses and puzzles, it offers an engaging and effective approach to mastering various subjects. Consider using Brilliant to enhance your knowledge and embrace the benefits of visual learning.**Subqueries: An Introduction**

**Understanding Subqueries**

* A subquery is an SQL query nested within another SQL query.
* It is used to fetch data based on specific conditions in the outer query.

**Example**

Let's consider an employee table with columns:

* EmployeeID (Primary Key)
* EmployeeName
* Department
* Salary* EmployeeName
* Department
* Salary

**Objective:** Find employees with salaries above the average salary of all employees.

**Syntax:**

```sql
SELECT * 
FROM Employee 
WHERE Salary > (SELECT AVG(Salary) FROM Employee);
```

**Explanation:**

* The subquery `(SELECT AVG(Salary) FROM Employee)` calculates the average salary of all employees.
* The outer query `SELECT * FROM Employee` retrieves employee details.
* The condition `WHERE Salary > (SELECT AVG(Salary) FROM Employee)` filters employees whose salaries exceed the average salary.

**Components of a Subquery**

* **Outer Query:** The main query that uses the subquery's results.
* **Subquery:** The nested query that provides data for the outer query.
* **Connecting Clause:** Links the subquery to the outer query, typically using a comparison operator like `>`, `<`, or `=`.

**Benefits of Subqueries**

* Reduce query complexity and improve readability.
* Avoid repeating complex data retrieval logic.* Avoid repeating complex data retrieval logic.
* Enable dynamic data retrieval based on dynamic conditions.## Understanding SQL Queries: Breaking Down Complex Questions

### Introduction

SQL (Structured Query Language) is a powerful tool for retrieving and manipulating data from databases. When writing SQL queries, it's helpful to break down complex questions into smaller parts.

### Breaking Down the Question

Let's take the example question: "Find the average salary earned by all employees and filter out employees based on the average salary."

**Part 1: Calculate Average Salary**

1. Use the `AVG()` aggregate function to calculate the average salary: `AVG(salary)`
2. Alias the result as `average_salary` for clarity: `AVG(salary) AS average_salary`

**Part 2: Filter Employees**

1. Use the `WHERE` clause to filter the `employees` table based on the `average_salary`:
   ```sql
   WHERE salary >= average_salary
   ``````sql
   WHERE salary >= average_salary
   ```
2. This condition checks if each employee's salary is greater than or equal to the average salary.

### Putting It Together

The complete SQL query would look like this:

```sql
SELECT AVG(salary) AS average_salary
FROM employees;
```

```sql
SELECT *
FROM employees
WHERE salary >= (SELECT AVG(salary) FROM employees);
```

### Syntax

**Aggregate Function:**

```sql
AVG(column_name)
```

**Alias:**

```sql
AVG(salary) AS average_salary
```

**WHERE Clause:**

```sql
WHERE column_name condition value
```

### Example

Consider the following sample table:

| id | name | salary |
|---|---|---|
| 1 | John | 50000 |
| 2 | Mary | 40000 |
| 3 | Tom | 60000 |

**Part 1: Calculate Average Salary**

```sql
SELECT AVG(salary) AS average_salary
FROM employees;
```

**Output:**

| average_salary |
|---|---|
| 50000 |

**Part 2: Filter Employees**

```sql
SELECT *
FROM employees
WHERE salary >= 50000;
```

**Output:**

| id | name | salary |
|---|---|---|```

**Output:**

| id | name | salary |
|---|---|---|
| 1 | John | 50000 |
| 3 | Tom | 60000 |**Understanding Average Functions**

**What is an Average Function?**

* An average function calculates the central tendency of a set of values.
* It represents the typical value or "mean" within the dataset.

**Syntax:**

```sql
AVG(column_name)
```

**Example:**

```sql
SELECT AVG(salary) FROM employee;
```

**Output:**

```
Average salary: 5791
```

**Filtering Data Based on Average**

To filter data based on the average value, use the `WHERE` clause with the `>` or `<` operators.

**Syntax:**

```sql
SELECT column_name
FROM table_name
WHERE column_name > (SELECT AVG(column_name) FROM table_name);
```

**Example:**

```sql
SELECT name
FROM employee
WHERE salary > (SELECT AVG(salary) FROM employee);
```

**Output:**

This query will return the names of employees whose salary is greater than the average salary.**Understanding Dynamic SQL Queries**

**Introduction:****Introduction:**

Dynamic SQL queries allow you to create SQL queries that adapt based on input or data from a table. This ensures that your queries are flexible and can handle changes in data or requirements.

**Step-by-Step Example:**

Consider the following scenario:

You want to find all employees with salaries above the average salary. However, you don't want to hardcode the average salary value in your query since it can change in the future.

**How to Create a Dynamic Query:**

1. **Find the Average Salary:** Use a SQL query to calculate the average salary, e.g.:
   ```sql
   SELECT AVG(salary) AS avg_salary
   FROM employees;
   ```
2. **Store the Average Salary:** Store the result of the query (average salary) in a variable:
   ```sql
   @avg_salary = (SELECT AVG(salary) FROM employees);
   ```
3. **Build the Dynamic Query:** Replace the hardcoded average value in the original query with the variable:
   ```sql
   SELECT *
   FROM employees
   WHERE salary > @avg_salary;
   ```FROM employees
   WHERE salary > @avg_salary;
   ```

**Benefits of Dynamic Queries:**

* **Flexibility:** Queries can adapt to changing data or requirements without rewriting them.
* **Maintainability:** Easier to maintain and update as data changes.
* **Performance:** Can improve performance by avoiding unnecessary recalculations.

**Syntax:**

The syntax for dynamic SQL queries varies depending on the database system. However, the general approach involves:

* Declaring a variable to store the dynamic data.
* Using a special character (e.g., @ in T-SQL) to reference the variable in the query.
* Executing the query using a prepared statement or stored procedure.

**Example Code:**

**T-SQL:**
```sql
DECLARE @avg_salary DECIMAL(10, 2);
SET @avg_salary = (SELECT AVG(salary) FROM employees);
SELECT *
FROM employees
WHERE salary > @avg_salary;
```**Introduction to Subqueries**

**What is a Subquery?**```**Introduction to Subqueries**

**What is a Subquery?**
A subquery is a query within another query. It allows you to use the result of one query as a filter or condition in another.

**How to Use Subqueries**
Subqueries are used using the following syntax:

```sql
SELECT ...
FROM ...
WHERE ... IN (
  SELECT ...
  FROM ...
)
```

In the above syntax, the subquery is the query within parentheses. It is used to filter the results of the outer query.

**Example**
Suppose we have a table of employees with the following columns:

| EmployeeID | Salary |
|---|---|
| 1 | 1000 |
| 2 | 2000 |
| 3 | 3000 |

We can use a subquery to find all employees with a salary greater than the average salary:

```sql
SELECT EmployeeID
FROM Employee
WHERE Salary > (
  SELECT AVG(Salary)
  FROM Employee
)
```

The subquery calculates the average salary and returns it as a single value. This value is then used to filter the results of the outer query.

**Advantages of Using Subqueries****Advantages of Using Subqueries**
* **Dynamic Queries:** Subqueries allow you to write queries that can adapt to changing data. For example, if the average salary changes, the subquery will automatically recalculate it.
* **Cleaner Code:** Subqueries can make your code more concise and easier to read.
* **Improved Performance:** In some cases, subqueries can improve query performance by reducing the number of joins required.**Understanding Subqueries**

**Introduction**

A subquery, also known as an inner query, is a standalone SQL query embedded within a larger query (the outer query). The outer query uses the results of the subquery to filter or modify its own results.

**Example**

Consider the following example:

```
SELECT *
FROM customers
WHERE customer_id IN (
    SELECT customer_id
    FROM orders
    WHERE order_status = 'Completed'
);
```

In this example, the subquery:

```
SELECT customer_id
FROM orders
WHERE order_status = 'Completed'
```FROM orders
WHERE order_status = 'Completed'
```

returns a list of customer IDs for customers who have placed completed orders. The outer query then uses this list to filter the `customers` table and select only the customers who have placed completed orders.

**Syntax**

The general syntax for a subquery is:

```
[outer query]
[subquery]
```

**Types of Subqueries**

Subqueries can be categorized by their position in the outer query:

* **Correlated Subqueries:** These subqueries depend on the results of the outer query.
* **Non-Correlated Subqueries:** These subqueries do not depend on the outer query.

**Uses of Subqueries**

Subqueries are useful for:

* Filtering results based on complex conditions
* Aggregating data from another table
* Performing calculations on data from another table**Understanding Subqueries**

**Introduction:**

* A subquery is a query within another query.
* It allows you to perform multiple queries in a single SQL statement.

**Execution:****Execution:**

* The subquery is executed first, and its results are passed to the outer query.
* The outer query uses the subquery results to filter or modify its own data.

**Types of Subqueries:**

* **Correlated:** Accesses data from the outer query.
* **Non-correlated:** Does not access data from the outer query.

**Uses of Subqueries:**

* Filtering and selecting data based on specific criteria.
* Aggregating data from multiple tables.
* Performing complex operations that would be difficult with a single query.

**Example:**

```sql
SELECT *
FROM users
WHERE salary > (
    SELECT MAX(salary)
    FROM users
    WHERE department = 'Marketing'
);
```

**Explanation:**

* The subquery finds the maximum salary of employees in the Marketing department.
* The outer query then selects all users whose salary is greater than that maximum salary.

**Benefits of Using Subqueries:**

* Improves code readability.
* Reduces code redundancy.
* Allows for more complex data operations.

**Limitations:*** Allows for more complex data operations.

**Limitations:**

* Can slow down performance if not optimized properly.
* Can be difficult to understand and debug for beginners.**Markdown Notes on SQL Subqueries**

**Introduction**

Subqueries are a powerful way to enrich SQL statements by embedding one query within another. They enhance query functionality by allowing the inclusion of additional data or applying complex conditions.

**Types of Subqueries**

There are three main types of subqueries:

- **Scalar Subquery:**
  - **Definition:** Returns a single row with a single column.
  - **Example:** Finding the average age of users:
    ```
    SELECT AVG(age)
    FROM users
    WHERE age > (
      SELECT MAX(age)
      FROM users
    );
    ```

- **Multiple Row Subquery:**
  - **Definition:** Returns multiple rows and multiple columns.
  - **Example:** Listing users with a specific address:
    ```
    SELECT *
    FROM users
    WHERE address IN (
      SELECT address
      FROM addressesSELECT address
      FROM addresses
      WHERE city = 'New York'
    );
    ```

- **Correlated Subquery:**
  - **Definition:** References data from the outer query.
  - **Example:** Calculating the difference between each user's salary and the average salary:
    ```
    SELECT name, salary - (
      SELECT AVG(salary)
      FROM users
    ) AS salary_difference
    FROM users;
    ```

**Benefits and Use Cases**

Subqueries provide several advantages, including:

- **Data Filtering:** Excluding or including data based on conditions specified in the subquery.
- **Data Aggregation:** Combining or summarizing data across multiple rows.
- **Complex Conditions:** Expressing complex conditions that cannot be easily handled by a single query.
- **Data Comparison:** Comparing data between different tables or queries.
- **Nested Queries:** Creating hierarchical queries with subqueries within subqueries.**Nested Queries: Understanding Scalar Subqueries**

**Introduction:****Introduction:**
Nested queries allow you to embed one query (subquery) within another (main query). A scalar subquery returns a single value, which can be used in the main query's WHERE, SELECT, or FROM clause.

**How to Use Scalar Subqueries:**
**1. In WHERE Clause:**
   - Compare the value returned by the subquery to a value or another column.
   - Example:
     ```sql
     SELECT *
     FROM products
     WHERE price > (SELECT MAX(price) FROM sales);
     ```
**2. In SELECT Clause:**
   - Use the subquery to calculate a value based on the main query's results.
   - Example:
     ```sql
     SELECT product_name, (SELECT SUM(quantity) FROM sales WHERE product_id = products.product_id) AS total_sales
     FROM products;
     ```
**3. In FROM Clause:**
   - Join the main query to the results of the subquery, based on a common column.
   - Example:
     ```sql
     SELECT *
     FROM products AS p- Example:
     ```sql
     SELECT *
     FROM products AS p
     JOIN (SELECT product_id, AVG(salary) AS average_salary FROM employees GROUP BY product_id) AS e ON p.product_id = e.product_id;
     ```

**Benefits of Scalar Subqueries:**
- Enhance query flexibility and avoid code duplication.
- Allow for complex calculations and comparisons across multiple tables.

**Tips for Using Scalar Subqueries:**
- Ensure the subquery returns a single value for each row in the main query.
- Use parentheses to enclose the subquery and alias the result for clarity.
- Test the subquery separately to verify it returns the expected value.**Inner Join with WHERE Clause**

**Concept**

An INNER JOIN with a WHERE clause allows you to retrieve data from multiple tables based on a specified condition. The WHERE clause filters the results based on the condition.

**Syntax**

```
SELECT *
FROM table1 INNER JOIN table2
ON table1.column1 = table2.column2
WHERE condition;
```

**Steps**WHERE condition;
```

**Steps**

1. **Identify the tables to join:** Specify the tables you want to join, separated by `INNER JOIN`.
2. **Specify the join condition:** Use the `ON` clause to specify the condition that links the two tables.
3. **Add a WHERE clause:** Include a `WHERE` clause after the `ON` clause to filter the results based on an additional condition.

**Example**

Suppose you have two tables: `employees` and `salaries` with the following data:

| **employees** | **salaries** |
|---|---|
| id | name | salary |
| 1 | John | 1000 |
| 2 | Mary | 1200 |
| 3 | Bob | 1500 |

To retrieve employees whose salary is greater than the average salary, you would use the following query:

```
SELECT *
FROM employees INNER JOIN salaries
ON employees.id = salaries.id
WHERE salaries.salary > (SELECT AVG(salary) FROM salaries);
```

**Output:**

| id | name | salary |
|---|---|---|
| 2 | Mary | 1200 |
| 3 | Bob | 1500 |

**Explanation**| 2 | Mary | 1200 |
| 3 | Bob | 1500 |

**Explanation**

* The `INNER JOIN` clause links the `employees` and `salaries` tables based on the common `id` column.
* The `WHERE` clause filters the results to include only employees whose salary is greater than the average salary.
* The subquery `(SELECT AVG(salary) FROM salaries)` calculates the average salary.**Concept: Scalar Subqueries in SQL**

**Introduction:**
A scalar subquery in SQL is a subquery that returns only a single value, both in terms of rows and columns. It acts like a placeholder for a constant value but is more dynamic, allowing you to use complex calculations or retrieve data from other tables.

**Types of Scalar Subqueries:**
There are two main types of scalar subqueries:
- **In the WHERE Clause:** Used to filter the outer query based on the result of the subquery.
- **In the FROM Clause (Join Condition):** Used to specify the join condition between the outer query and the result set of the subquery.

**Example:**

**Original Query:**
```sql**Example:**

**Original Query:**
```sql
SELECT *
FROM Employees
WHERE Salary > 50000;
```

**Scalar Subquery in WHERE Clause:**
```sql
SELECT *
FROM Employees
WHERE Salary > (SELECT MAX(Salary) FROM Employees);
```

**Scalar Subquery in FROM Clause (Join Condition):**
```sql
SELECT *
FROM Employees e
JOIN (SELECT EmployeeID, MAX(Salary) AS MaxSalary
      FROM Employees
      GROUP BY EmployeeID) subquery
ON e.EmployeeID = subquery.EmployeeID;
```

**Usage:**
Scalar subqueries can be used in various contexts, including:
- Filtering data based on values from another table
- Performing calculations and using the result as a constant
- Grouping data and aggregating values before joining

**Advantages:**
- **Code Reusability:** Allows you to reuse complex calculations or data retrieval logic across multiple queries.
- **Dynamic Results:** Subqueries can provide dynamic results, unlike fixed values.
- **Performance:** Can be more efficient than using multiple joins or complex CASE statements.

**Limitations:****Limitations:**
- Can only return a single value.
- Can be more complex to understand compared to simple queries.## Subqueries: Multiple Row Types

**Definition:**
A subquery is a query nested within another query. A multiple row subquery returns more than one row.

**Types:**

There are two main types of multiple row subqueries:

**1. Multiple Column, Multiple Row Subquery:**

- Returns multiple columns and multiple rows.
- Typically used to return a set of related data.

**Syntax:**

```sql
SELECT column1, column2, ...
FROM (
    SELECT column1, column2, ...
    FROM table_name
    WHERE condition
) AS subquery_alias;
```

**2. Single Column, Multiple Row Subquery:**

- Returns only one column but multiple rows.
- Often used to evaluate a condition or to aggregate data.

**Syntax:**

```sql
SELECT column1
FROM (
    SELECT column1
    FROM table_name
    WHERE condition
) AS subquery_alias;
```

**Usage:**

Multiple row subqueries are useful in a variety of situations, such as:- Retrieving related data from multiple tables
- Filtering data based on a subquery's results
- Grouping and aggregating data

**Example (Multiple Column, Multiple Row Subquery):**

```sql
-- Get all employees and their departments
SELECT employee_name, department_name
FROM employees AS e
INNER JOIN (
    SELECT employee_id, department_id, department_name
    FROM departments
) AS d ON e.department_id = d.department_id;
```

**Example (Single Column, Multiple Row Subquery):**

```sql
-- Check if any employees live in New York
SELECT EXISTS (
    SELECT *
    FROM employees
    WHERE city = 'New York'
);
```**Markdown Notes on Multiple Row Subqueries**

**Introduction**

A subquery is a query within a query. Multiple row subqueries return multiple rows of data, which can be used in the outer query.

**Types of Multiple Row Subqueries**

**1. Multiple Column, Single Row Subquery**

* Returns a single row with multiple columns.

**2. Single Column, Multiple Row Subquery****2. Single Column, Multiple Row Subquery**

* Returns multiple rows with a single column.

**Example: Finding Employees with Highest Salaries in Each Department**

**1. Identify the Highest Salary in Each Department (Subquery)**

```sql
SELECT MAX(salary)
FROM employees
GROUP BY department_id;
```

**2. Compare Salary and Department Information with Employee Table**

```sql
SELECT *
FROM employees
WHERE salary IN (
    SELECT MAX(salary)
    FROM employees
    GROUP BY department_id
);
```

**Explanation:**

* The subquery (inner query) finds the maximum salary for each department.
* The outer query (main query) selects all employees whose salaries match the maximum salaries found in the subquery.

**Benefits of Multiple Row Subqueries**

* Allow for complex data comparisons and manipulations.
* Simplify complex queries by breaking them down into smaller steps.
* Improve query performance by optimizing data retrieval.

**Tips for Using Multiple Row Subqueries****Tips for Using Multiple Row Subqueries**

* Use correlated subqueries when the outer query references data in the subquery.
* Use nested subqueries to handle complex relationships between tables.
* Ensure that the subquery returns the correct number and type of columns.
* Optimize the subquery to improve query performance.## Introduction to SQL GROUP BY

### Purpose

The GROUP BY statement in SQL allows you to group rows in a table based on common values in one or more columns. This helps you summarize and aggregate data for each group, providing insights into the distribution and trends within the dataset.

### Syntax

```sql
SELECT column_list
FROM table_name
GROUP BY group_by_column(s)
```

### Steps

1. **Identify Group-By Columns:** Determine which columns you want to group the data by. These columns should contain unique or common values that you're interested in analyzing.2. **Aggregate Functions:** Use aggregate functions (e.g., SUM(), MAX(), MIN(), AVG()) to calculate summary statistics for each group.

3. **Column Selection:** Select the columns you want to include in the output. These can be either group-by columns or other columns containing relevant information.

### Example

Consider the following table:

```
| Employee_ID | Department | Salary |
|---|---|---|
| 1 | Sales | 50000 |
| 2 | Marketing | 40000 |
| 3 | Sales | 60000 |
| 4 | Marketing | 50000 |
| 5 | Sales | 45000 |
```

**Query:** Find the highest salary for each department.

```sql
SELECT Department, MAX(Salary)
FROM Employee
GROUP BY Department;
```

**Output:**

```
| Department | MAX(Salary) |
|---|---|
| Sales | 60000 |
| Marketing | 50000 |
```

### Conclusion| Sales | 60000 |
| Marketing | 50000 |
```

### Conclusion

The GROUP BY statement is a powerful tool for data aggregation and summarization in SQL. By grouping rows by common values, you can extract meaningful insights and gain a better understanding of the data distribution in your table.## SQL: Group By with Aggregate Function (MAX)

### Understanding Group BY

- `GROUP BY` is an SQL command used to group rows with common values in a specified column.
- It creates a group for each distinct value in the column.

### Aggregate Functions

- Aggregate functions perform calculations on grouped data.
- The `MAX()` function returns the maximum value in a group.

### Finding Maximum Salary by Department

**Syntax:**

```sql
SELECT department_name, MAX(salary)
FROM employee_table
GROUP BY department_name;
```

**Explanation:**

- This query performs the following steps:
  - Groups rows by `department_name`.
  - For each department group, calculates the maximum salary using `MAX(salary)`.### Filtering Data Using the Grouped Query

**Syntax:**

```sql
SELECT *
FROM employee_table
WHERE department_name IN (
  SELECT department_name
  FROM employee_table
  GROUP BY department_name
  HAVING MAX(salary) = <desired_salary>
);
```

**Explanation:**

- This query filters the `employee_table` using the grouped query:
  - The subquery finds the department(s) with the maximum salary specified by `<desired_salary>`.
  - The `IN` clause ensures that the outer query only selects rows from departments with the maximum salary.# Filtering with Multiple Columns in SQL

## Introduction

SQL allows you to filter data based on multiple columns using parentheses. This is useful when you need to compare rows based on multiple criteria.

## Step 1: Identify the Columns

Determine which columns you want to use for filtering. In the example, we're using `department_name` and `salary`.

## Step 2: Use Parentheses

Enclose the column names in parentheses to indicate that they are being used together for filtering.```sql
WHERE (department_name, salary)
```

## Step 3: Specify the Comparison Operator

After the parentheses, specify the comparison operator. In this example, we're using `IN`.

```sql
WHERE (department_name, salary) IN
```

## Step 4: Provide the Subquery

After the `IN` clause, provide a subquery that returns the values to compare with.

## Example:

```sql
SELECT *
FROM employees
WHERE (department_name, salary) IN (
    SELECT department_name, salary
    FROM another_table
);
```

In this example, we're selecting employees whose `department_name` and `salary` match any combination of values in the subquery.

## Key Points

* Use parentheses to enclose multiple columns in the filter condition.
* Specify the comparison operator (`=`, `IN`, etc.) after the parentheses.
* Provide a subquery to specify the values to compare with.
* Subqueries can return multiple rows for comparison.**Understanding SQL Subqueries**

**What is a Subquery?****What is a Subquery?**

A subquery is a query that is nested within another query. It allows you to retrieve data from multiple tables or perform complex calculations within a single query.

**Types of Subqueries:**

* **Dependent Subqueries:** Require data from the outer query to function.
* **Independent Subqueries:** Do not rely on data from the outer query.

**Processing a Subquery:**

1. SQL first executes the subquery.
2. The result of the subquery is treated as a temporary table.
3. The outer query then uses the data from the temporary table.

**Example Query:**

```sql
SELECT *
FROM Employees
WHERE Salary = (SELECT MAX(Salary) FROM Employees);
```

This query finds employees with salaries equal to the maximum salary in the Employees table.

**How SQL Processes the Subquery:**

1. SQL executes the subquery `(SELECT MAX(Salary) FROM Employees)` to determine the maximum salary.
2. The result, `8000`, is stored in a temporary table.2. The result, `8000`, is stored in a temporary table.
3. The outer query filters the Employees table, selecting only employees whose salary matches the value in the temporary table.

**Understanding Subquery Relationships:**

* **Independent Subqueries:** Can be used to filter data, perform calculations, or retrieve data from unrelated tables.
* **Dependent Subqueries:** Require data from the outer query to compare or filter data.

**Tips for Using Subqueries:**

* Use subqueries when you need to retrieve data from multiple tables or perform complex calculations.
* Identify whether your subquery is dependent or independent.
* Ensure that subqueries are properly nested and have correct syntax.
* Use subqueries sparingly to avoid performance issues.**Markdown Notes: Multiple Row Subqueries**

**Introduction**

A subquery is a separate query that's embedded within another query. Multiple row subqueries return more than one row of data.

**How Multiple Row Subqueries Work**

1. The subquery is executed first.1. The subquery is executed first.
2. The results of the subquery are stored in a temporary table.
3. The outer query is executed, matching the values in its filter condition against the results of the subquery.
4. Any matching records from the outer query are returned as the results of the entire query.

**Example: Finding Employees with Matching Department and Salary**

```sql
SELECT *
FROM employees
WHERE (department_name, salary) IN (
    SELECT department_name, salary
    FROM (
        SELECT department_name, salary
        FROM employees
        WHERE department_name = 'Sales' OR department_name = 'Marketing'
    ) AS subquery
);
```

**Explanation:**

* The subquery selects department names and salaries from employees in the 'Sales' or 'Marketing' departments.
* The outer query uses the IN operator to match the department names and salaries in the employee table with the results of the subquery.* The query returns any employees whose department and salary match any of the combinations in the subquery.

**Key Points**

* Multiple row subqueries return multiple rows of data.
* The subquery is executed before the outer query.
* The outer query's filter condition must use an operator that handles multiple rows (e.g., IN, ANY).
* Subqueries can be nested to create complex queries.**Multiple Row Subqueries**

**Introduction**
- Multiple row subqueries retrieve multiple rows of data from a subquery to use in the outer query.

**Types of Multiple Row Subqueries**

**1. Multiple Column and Multiple Row Subquery**
- Retrieves multiple rows and multiple columns from a subquery.
- Syntax:
```
SELECT <column_list>
FROM <outer_table>
WHERE <condition> IN (
    SELECT <subquery_column_list>
    FROM <subquery_table>
    WHERE <subquery_condition>
)
```

**2. Single Column and Multiple Row Subquery**
- Retrieves multiple rows but only a single column from a subquery.
- Syntax:
```
SELECT <column_list>- Syntax:
```
SELECT <column_list>
FROM <outer_table>
WHERE <condition> IN (
    SELECT <subquery_column>
    FROM <subquery_table>
    WHERE <subquery_condition>
)
```

**Example: Finding Departments Without Employees**

**Problem:**
- Find departments that do not have any employees.

**Tables:**
- Department: (dept_id, dept_name, location)
- Employee: (emp_id, emp_name, dept_id)

**Query:**
```
SELECT dept_name
FROM Department
WHERE dept_id NOT IN (
    SELECT dept_id
    FROM Employee
)
```

**Explanation:**
- The outer query filters the Department table to select department names.
- The subquery returns the dept_ids of all departments that have at least one employee.
- The NOT IN operator compares the dept_id from the outer query to the dept_ids in the subquery, excluding departments represented in the subquery result (i.e., those with employees).# Finding Empty Departments in a Database

## Introduction## Introduction

This tutorial will guide you through writing a SQL query to identify departments that have no employees in a database.

## Step 1: Select the Department Table

```sql
SELECT * FROM department;
```

This query retrieves all the rows from the `department` table.

## Step 2: Subquery to Find Occupied Departments

```sql
SELECT department_name
FROM employee
GROUP BY department_name;
```

This subquery finds the names of all departments that have at least one employee. It uses the `GROUP BY` clause to group rows by department name, effectively eliminating duplicate department names.

## Step 3: Left Join to Identify Empty Departments

```sql
SELECT *
FROM department
LEFT JOIN (
    SELECT department_name
    FROM employee
    GROUP BY department_name
) AS occupied_departments
ON department.department_name = occupied_departments.department_name
WHERE occupied_departments.department_name IS NULL;
```WHERE occupied_departments.department_name IS NULL;
```

This query uses a left join between the `department` table and the subquery from Step 2. The `LEFT JOIN` clause matches rows from the `department` table with those in the subquery.

The `ON` clause specifies that the join should be performed based on the `department_name` column in both tables.

The `WHERE` clause filters the results to include only departments that are not present in the subquery (i.e. departments where there are no employees).

## Example

Consider the following `department` and `employee` tables:

```
| department |
|------------|
| Sales      |
| Marketing   |
| Engineering |

| employee | department |
|----------|------------|
| John      | Sales      |
| Mary      | Marketing   |
| Peter      | Engineering |
```

The above SQL query would return the following result:

```
| department |
|------------|
| Engineering |
``````
| department |
|------------|
| Engineering |
```

This indicates that the `Engineering` department is empty, as it does not have any employees in the `employee` table.**Markdown Notes on Advanced SQL Query Techniques: Using Subqueries and Comparisons**

**Introduction**

In this lesson, we'll explore advanced SQL query techniques using subqueries and comparisons. We'll learn how to:

- Use subqueries to retrieve data from nested tables
- Compare values between tables using subqueries
- Enhance the precision and efficiency of your queries

**Subqueries**

A subquery is a nested query that returns a subset of data from a table. Subqueries can be used to filter, aggregate, or manipulate data before it's used in the main query.

**Syntax:**

```sql
SELECT column(s)
FROM table(s)
WHERE condition
```

For example, to retrieve the distinct department names from the `employee` table:

```sql
SELECT DISTINCT department_name
FROM employee;
```

**Using Subqueries in Comparisons**FROM employee;
```

**Using Subqueries in Comparisons**

Subqueries can be used to compare values between tables. This allows you to filter data based on relationships between multiple tables.

**Syntax:**

```sql
SELECT column(s)
FROM table1
WHERE NOT EXISTS (
  SELECT 1
  FROM table2
  WHERE condition
);
```

For example, to select all departments in the `department` table that are not present in the `employee` table:

```sql
SELECT department_name
FROM department
WHERE NOT EXISTS (
  SELECT 1
  FROM employee
  WHERE department_name = department.department_name
);
```

**Example**

Let's use a subquery to find all departments in the `department` table that do not have any employees.

**Main Query:**

```sql
SELECT department_name
FROM department
WHERE department_name NOT IN (
  SELECT DISTINCT department_name
  FROM employee
);
```

**Subquery:**

```sql
SELECT DISTINCT department_name
FROM employee;
```

**Result:**FROM employee;
```

**Result:**

This query will return a list of all department names in the `department` table that are not present in the `employee` table, indicating which departments have no employees.**Understanding Single-Column, Multi-Row Subqueries**

**Core Concept:**

* Subqueries allow you to embed queries within other queries.
* Single-column, multi-row subqueries return multiple rows with only one column.

**Step-by-Step Explanation:**

1. **Identify the main query:** The main query is the query that contains the subquery. In this example, the main query is:
```sql
SELECT department_name
FROM department
WHERE department_name NOT IN (
`;

2. **Define the subquery:** The subquery is the query inside the parentheses in the main query. In this example, the subquery is:
```sql
SELECT department_name
FROM employee
`;```sql
SELECT department_name
FROM employee
`;

3. **Understand the subquery's purpose:** In this case, the subquery identifies departments that have employees. By excluding these departments from the main query, we find departments that do not have any employees.

4. **Execute the query:** When you execute the query, it returns two departments: Marketing and Sales. These are the departments that do not have any employees.

**Why Single-Column, Multi-Row Subqueries are Useful:**

* They allow you to filter data using multiple values without creating multiple conditions in the main query.
* They can simplify complex queries and improve readability.

**Example:**

The following query uses a single-column, multi-row subquery to find all products with a price below the minimum price for any product in the "Electronics" category:
```sql
SELECT product_name
FROM product
WHERE price < (
    SELECT MIN(price)
    FROM product
    WHERE category = "Electronics"
);
`;**Understanding Subqueries**

**Introduction**);
`;**Understanding Subqueries**

**Introduction**

Subqueries are nested queries that provide additional information or restrictions to an outer query. They allow for more complex data retrieval and manipulation.

**Types of Subqueries**

There are three main types of subqueries:

1. **Single-Row Subqueries:** Return a single row and a single column, which can be compared to a column in the outer query.
```sql
SELECT * FROM table WHERE id = (SELECT id FROM subquery);
```

2. **Multiple-Row Subqueries:** Return multiple rows, often with a single column. These rows can be used for comparison or other operations in the outer query.
```sql
SELECT * FROM table WHERE id IN (SELECT id FROM subquery);
```

3. **Correlated Subqueries:** Refer to values from the outer query in their definition. This creates a dependency between the subquery and the outer query.
```sql
SELECT name FROM people WHERE id = (SELECT max(id) FROM people WHERE city = 'London');
```

**Uses of Subqueries**```

**Uses of Subqueries**

Subqueries can be used in various scenarios:

* Filtering data based on specific criteria
* Comparing data values across multiple tables
* Aggregating data from multiple sources
* Performing complex calculations

**Syntax of Subqueries:**

```sql
SELECT column_name(s)
FROM table_name(s)
WHERE condition
AND/OR (SELECT column_name(s)
FROM subquery_table_name(s)
WHERE subquery_condition)
```

**Example:**

```sql
SELECT name
FROM customers
WHERE city = (SELECT city FROM addresses WHERE customer_id = customers.id);
```
This subquery retrieves the city for each customer from the `addresses` table and uses it to filter customers who live in a specific city in the `customers` table.## Correlated Subqueries in SQL

### Understanding Correlated Subqueries

A correlated subquery is a subquery whose execution depends on the values returned from the outer query. The outer query provides input values to the subquery, and the subquery returns a result based on the outer query input.### Types of Correlated Subqueries

As with other subqueries, there are two types of correlated subqueries:

* **Scalar Subquery:** Returns a single value (e.g., a count, maximum, minimum).
* **Multiple Row Subquery:** Returns multiple rows of data.

### Execution Flow

When SQL encounters a statement that contains a correlated subquery:

1. SQL executes the subquery first, providing it with input values from the outer query.
2. SQL then uses the results of the subquery to execute the outer query.

### Example of a Correlated Subquery

```sql
SELECT employee_name
FROM employees
WHERE salary > (
  SELECT MAX(salary)
  FROM employees
  WHERE department = 'Sales'
);
```

In this example, the subquery selects the maximum salary for employees in the Sales department. The outer query then uses this result to select employees whose salary exceeds the maximum salary in Sales.

### Key Points

* Correlated subqueries are dependent on the outer query.* Correlated subqueries are dependent on the outer query.
* The subquery is executed first, providing input values to the outer query.
* Scalar subqueries return a single value, while multiple row subqueries return multiple rows.
* Subqueries are executed only once during the processing of the outer query.**Markdown Notes on Correlated Subqueries**

**Introduction**

A correlated subquery is a subquery (a nested query within another query) that references columns from the outer query. Unlike regular subqueries, which are evaluated once, correlated subqueries are evaluated for each row of the outer query.

**Definition**

A correlated subquery is a subquery that:

* Is nested within another query (the outer query).
* References columns from the outer query in its WHERE clause.

**Purpose**

Correlated subqueries are used when you need to compare data from the outer query with data from a related table.

**Setup**

To create a correlated subquery:

1. Write the outer query.To create a correlated subquery:

1. Write the outer query.
2. Use the `EXISTS` or `IN` operator to compare a column from the outer query with a subquery.
3. Write the subquery to retrieve the related data.

**Syntax**

```
SELECT column_list
FROM outer_table
WHERE column_name IN (SELECT column_list FROM subquery)
```

**Example**

Find employees who earn more than the average salary in their department:

```sql
SELECT name
FROM employees
WHERE salary > (
  SELECT AVG(salary)
  FROM employees
  WHERE department = employees.department
);
```

**Explanation**

1. The outer query selects the names of employees.
2. The subquery calculates the average salary for each department.
3. The main query compares each employee's salary to the average salary for their department.

**Benefits**

* Allows for complex comparisons between related data.
* Can be used to retrieve data that would otherwise be difficult or impossible to obtain.

**Considerations****Considerations**

* Correlated subqueries can be more efficient than regular subqueries because they only retrieve the necessary data.
* However, they can also be more complex to write and understand.## Correlated Subqueries in SQL

### Concept

A correlated subquery is a subquery that references columns from the outer query in its WHERE clause. This allows us to compare values from the outer query to values calculated in the subquery, which can be used to filter data dynamically.

### Syntax

```
SELECT column_list
FROM outer_table
WHERE column_name IN (
    SELECT subquery_column
    FROM subquery_table
    WHERE subquery_table.column_name = outer_table.column_name
)
```

### Example: Finding Employees with Salaries Above Department Average

**Problem:** Find employees whose salary is greater than the average salary in their department.

**Solution:**

```sql
SELECT *
FROM employee
WHERE salary > (
    SELECT AVG(salary)
    FROM employee
    WHERE department_id = employee.department_id
)
```WHERE department_id = employee.department_id
)
```

**Breakdown:**

1. The main query selects all columns from the `employee` table.
2. The WHERE clause uses a correlated subquery to calculate the average salary for each department.
3. The subquery selects the average salary from the `employee` table, grouped by department ID.
4. The outer query then compares each employee's salary to the average salary for their department and returns only those employees whose salaries are higher.

### Explanation

1. The correlated subquery calculates the average salary for each department, which is stored in a temporary table.
2. The outer query then iterates through each employee and retrieves the average salary for their department from the temporary table.
3. By comparing each employee's salary to the department average, the outer query selects only those employees whose salaries are above the average.**Understanding Correlated Subqueries**

**What is a Subquery?****What is a Subquery?**

A subquery is a query within a query. It allows you to retrieve data from one or more tables and use that data in the parent query.

**What is a Correlated Subquery?**

A correlated subquery is a subquery that references a column from the outer query. This means that the result of the subquery depends on the value of the outer query.

**Understanding the Problem**

The provided code aims to find all employees whose salary is greater than the average salary in their department.

**Creating a Correlated Subquery**

To solve this problem using a correlated subquery, we can use the following steps:

**Step 1: Select the Employees**

`SELECT * FROM Employees`

This retrieves all the employees from the Employees table.

**Step 2: Filter Employees Based on Condition**

`WHERE Salary > (SELECT AVG(Salary) FROM Employees WHERE DepartmentName = Employees.DepartmentName)`* The subquery `(SELECT AVG(Salary) FROM Employees WHERE DepartmentName = Employees.DepartmentName)` calculates the average salary for each department.
* The `WHERE` clause compares each employee's salary with the average salary for their department.

**Example**

`SELECT * FROM Employees
WHERE Salary > (SELECT AVG(Salary)
FROM Employees
WHERE DepartmentName = Employees.DepartmentName)`

This query will retrieve all employees whose salary is greater than the average salary in their respective departments.

**Advantages of Using Correlated Subqueries**

* Can be used to perform complex filtering based on multiple conditions.
* Avoids the need for joins or temporary tables.

**Limitations of Correlated Subqueries**

* Can be inefficient for large datasets, as the subquery is executed for each row in the outer query.**Subqueries in SQL**

**Introduction:**

* Subqueries are nested queries within a main query.
* They allow you to embed multiple queries into a single statement.

**Purpose:****Purpose:**

* Filter data based on specific criteria.
* Perform calculations or aggregations using data from the main query.

**Structure:**

* **Main Query:** The outer query that executes the main operation.
* **Subquery:** The nested query that provides additional data or conditions.

**Example:**

Consider the following scenario:

* You have an employee table with columns like `EmployeeID`, `Name`, `Department`, and `Salary`.
* You want to find employees whose salaries are greater than the average salary in their respective departments.

**Subquery to Calculate Average Salary:**

```sql
SELECT AVG(Salary)
FROM employee
WHERE Department = <department>
```

**Main Query to Filter Employees:**

```sql
SELECT EmployeeID, Name
FROM employee
WHERE Salary > (SELECT AVG(Salary)
                 FROM employee  -- Subquery
                 WHERE Department = <department>)
```

**Explanation:**

* The subquery calculates the average salary for each department.* The main query uses this average salary in the `WHERE` clause to filter employees whose salaries exceed that average.

**Code Syntax:**

The general syntax for a subquery is:

```sql
SELECT <columns>
FROM <table name>
WHERE <condition>
```

* `<columns>`: The columns to be retrieved from the subquery.
* `<table name>`: The table being queried.
* `<condition>`: The filter condition for the subquery.

**Tips for Using Subqueries:**

* Keep subqueries as simple and efficient as possible.
* Use aliases for subqueries to make the main query easier to read.
* Ensure that the columns in the subquery match the columns in the main query.**Understanding Average Salary Calculation**

**Step 1: Calculate the Average Salary for All Employees**

```
SELECT AVG(salary)
FROM employee;
```

This query calculates the average salary of all employees in the database and returns the result as a single value.

**Step 2: Subquery to Calculate Department-Specific Average Salary**

```
(SELECT AVG(salary)
FROM employee```
(SELECT AVG(salary)
FROM employee
WHERE department_id = E1.department_id)
```

This subquery calculates the average salary for the department of the current employee being processed in the main query. We alias this subquery as `E2`.

**Modified Query**

```
SELECT *
FROM employee AS E1
WHERE salary > (
    SELECT AVG(salary)
    FROM employee
    WHERE department_id = E1.department_id
);
```

**Explanation**

* The `SELECT *` clause retrieves all columns for employees.
* The `FROM employee AS E1` clause aliases the employee table to `E1` for easier reference.
* The `WHERE` clause uses the subquery to compare the salary of each employee (`E1`) with the average salary of their department (`E2`).
* Employees whose salaries exceed the department-specific average salary will be returned.**Correlated Subqueries in SQL**

**Concept:**

* A correlated subquery is an inner query that references columns from the outer query.
* It depends on the values returned by the outer query to execute itself.**Execution Process:**

1. SQL executes the outer query.
2. For each record returned by the outer query:
   - SQL executes the inner (correlated) subquery.
   - The inner subquery uses the values from the outer query record to filter its results.

**Example:**

Consider the following SQL statement:

```
SELECT *
FROM table1
WHERE id IN (SELECT id FROM table2 WHERE name = 'John');
```

* The inner subquery selects all `id` values from `table2` where `name` is 'John'.
* The outer query uses these `id` values to filter the results from `table1`.

**Why Correlated Subqueries Matter:**

* They allow complex filtering and data retrieval based on values from the outer query.
* They can be used to perform aggregations (e.g., MIN, MAX) or join data from multiple tables.

**Syntax:**

```
SELECT column_list
FROM table1
WHERE <condition> IN (
    SELECT <column_list>
    FROM table2
    WHERE <condition>
);
```

**Note:** The inner subquery must be enclosed in parentheses.**Understanding Subqueries in SQL****Core Concept:**

* A subquery is a nested query that returns a set of rows used as input for the outer query.

**Key Concepts:**

**Execution Order:**

* Subqueries are executed before the outer query.
* The result of the subquery is temporarily stored in a temporary table.

**Usage:**

* Subqueries are used to filter, aggregate, or manipulate data based on conditions from another table.
* They allow for complex data retrieval without using joins.

**Example:**

Consider a query that calculates the average salary for each department:

```sql
SELECT department_name, AVG(salary)
FROM employee
GROUP BY department_name;
```

**How the Subquery Works:**

In this example, the subquery is:

```sql
(SELECT AVG(salary)
FROM employee
WHERE department_name = 'admin')
```

* The subquery retrieves the average salary for the 'admin' department.
* The result of the subquery is used in the outer query to calculate the average salary for each department.

**Steps of Execution:****Steps of Execution:**

1. The subquery is executed first, returning a single row with the average salary for the 'admin' department.
2. The average salary from the subquery is assigned to the temp table.
3. The outer query then iterates through each department in the employee table.
4. For each department, the outer query retrieves the average salary from the temp table based on the department name.
5. The outer query then calculates the overall average salary for each department.

**Benefits of Subqueries:**

* **Efficiency:** Avoids multiple joins and reduces the number of rows processed.
* **Flexibility:** Allows for complex filtering and aggregation without modifying the main query.
* **Readability:** Encapsulates complex logic into a separate subquery.

**Note:**

* Always enclose subqueries in parentheses.
* Subqueries can be used in various clauses, such as WHERE, HAVING, and FROM.
* Subqueries can also be nested within other subqueries.**Correlated Subqueries**

**Definition:****Definition:**
A correlated subquery is a subquery that refers to columns from the outer query.

**Purpose:**
Used to compare data from different rows in the outer query.

**Syntax:**

```sql
SELECT ...
FROM ...
WHERE ... (SELECT ... FROM ... WHERE ...)
```

**Breakdown:**

**Step 1: Execute the Outer Query**
- The main query retrieves data from a table or multiple tables.

**Step 2: Evaluate the Subquery for Each Row**
- The subquery is executed once for each row in the outer query.
- The subquery uses columns from the current row in the outer query.

**Step 3: Comparison**
- The result of the subquery is compared with the specified condition.

**Example:**

Let's say we have an "Employees" table with the following columns:

- `EmpID`
- `DeptID`
- `Salary`

To find employees in the "Admin" department with salaries above the average salary in that department, we can use the following correlated subquery:

```sql
SELECT EmpID, Salary
FROM Employees```sql
SELECT EmpID, Salary
FROM Employees
WHERE DeptID = (SELECT DeptID FROM Employees WHERE JobTitle LIKE '%Admin%')
  AND Salary > (SELECT AVG(Salary) FROM Employees WHERE DeptID = (SELECT DeptID FROM Employees WHERE JobTitle LIKE '%Admin%'));
```

**Explanation:**

- The outer query retrieves employees where the `DeptID` matches the `DeptID` of employees with the "Admin" job title.
- The subquery retrieves the average salary for employees in the "Admin" department.
- The `Salary` column of each employee in the outer query is then compared to the average salary from the subquery.
- Records where the `Salary` exceeds the average are returned as the result.**Understanding Correlated Subqueries**

Correlated subqueries are a type of subquery that references values from the outer query in its own WHERE clause. This means that the subquery is executed multiple times, each time with a different value from the outer query.

**Advantages of Correlated Subqueries****Advantages of Correlated Subqueries**

* Can be used to retrieve data from multiple tables based on a relationship between the tables.

**Disadvantages of Correlated Subqueries**

* Performance: Correlated subqueries can be inefficient if the outer query has a large number of rows, as the subquery will be executed multiple times.
* Complexity: Correlated subqueries can be difficult to write and understand.

**Alternatives to Correlated Subqueries**

* Joins: Joins can be used to perform similar operations as correlated subqueries, but can be more efficient.
* Scalar or multi-row subqueries: These types of subqueries return a single value or multiple rows of data, respectively, and can be used to avoid the performance issues associated with correlated subqueries.

**Syntax**

```sql
SELECT column_name
FROM table_name
WHERE column_name IN (SELECT column_name
                      FROM subquery_table_name
                      WHERE subquery_column_name = outer_query_column_name);
```

**Example**```

**Example**

Find the average salary of employees in the `Admin` department:

```sql
SELECT department_name, AVG(salary)
FROM employee_table
WHERE department_name = (SELECT department_name
                         FROM employee_table
                         WHERE employee_id = 1);
```

This query will calculate the average salary for each department, but it will be inefficient if the `employee_table` has a large number of rows, as the subquery will be executed multiple times. A more efficient alternative would be to use a self-join:

```sql
SELECT department_name, AVG(salary)
FROM employee_table et1
JOIN employee_table et2 ON et1.department_name = et2.department_name
WHERE et1.employee_id = 1
GROUP BY department_name;
```## Understanding Correlated Subqueries

### Overview```## Understanding Correlated Subqueries

### Overview

Correlated subqueries are a type of subquery that executes multiple times, once for each row in the outer query. The results of the subquery depend on the values in the outer query, which makes them useful for processing data in complex ways.

### How Correlated Subqueries Work

For each record in the outer query:

- The subquery is executed using the current value from the outer query.
- The results of the subquery are used to perform operations on the outer query record.

### Use Cases

Correlated subqueries are particularly useful in situations where:

- Data processing requires comparing each row in the outer query to another set of related data.
- The subquery returns different results for different rows in the outer query.

### Advantages and Disadvantages

**Advantages:**

- Can solve complex data processing problems efficiently.
- Allows for flexible data manipulation based on values in the outer query.

**Disadvantages:****Disadvantages:**

- Can slow down query execution time due to multiple subquery executions.

### Syntax

**SQL:**

```
SELECT column_name FROM outer_table
WHERE (SELECT subquery_column FROM subquery_table
       WHERE subquery_condition = outer_query_value)
       operator comparison_value;
```

### Example

Consider the following example:

**Question:** Find the employees in the "Marketing" department with salaries above the average salary for the department.

**SQL Query with Correlated Subquery:**

```
SELECT employee_name
FROM employee_table
WHERE salary > (
    SELECT AVG(salary)
    FROM employee_table
    WHERE department = 'Marketing'
);
```

In this query, the subquery calculates the average salary for the "Marketing" department, which is then compared to the salary of each employee.

### Correlated Subqueries vs. Multi-Row Subqueries

- **Correlated subqueries:** Execute multiple times, with each execution depending on the values from the outer query.- **Multi-row subqueries:** Return multiple rows as a single result, which can be used directly in the outer query.## Understanding Correlated Subqueries

### What are Correlated Subqueries?

A correlated subquery is a subquery that references columns from the outer query in its WHERE clause. This allows us to filter the outer query's results based on the values of specific rows.

### Example: Finding Departments Without Employees

**Problem:** Find all departments that do not have any employees.

**Solution Using Correlated Subquery:**

```sql
SELECT *
FROM department
WHERE NOT EXISTS (
    SELECT 1
    FROM employee
    WHERE employee.department_name = department.department_name
);
```

### Explanation:

* The outer query selects all columns from the `department` table.
* The `NOT EXISTS` operator is used to filter out departments that have at least one employee.
* The correlated subquery within the `NOT EXISTS` clause selects one row from the `employee` table for each department in the outer query.* If the subquery returns at least one row, the `NOT EXISTS` condition is false and the department is excluded from the results.
* If the subquery returns no rows, the `NOT EXISTS` condition is true and the department is included in the results.

### Step-by-Step Explanation:

1. Start with the outer query to select all columns from the `department` table: `SELECT * FROM department`.
2. Add the `WHERE` clause with `NOT EXISTS` to exclude departments with employees: `WHERE NOT EXISTS`.
3. Create the correlated subquery within the parentheses:
   * Select one row from the `employee` table: `SELECT 1`
   * From the `employee` table: `FROM employee`
   * Where the `department_name` column in the employee table matches the `department_name` column in the outer query: `WHERE employee.department_name = department.department_name`## Understanding NOT EXISTS in SQL

### Introduction

`NOT EXISTS` is a logical operator in SQL that checks if a subquery returns no records for each row in the outer query.

### Syntax### Syntax

```sql
SELECT column_list
FROM table1
WHERE NOT EXISTS (subquery);
```

### How it Works

`NOT EXISTS` evaluates a subquery for each row in the outer query. If the subquery returns no records (i.e., an empty set), `NOT EXISTS` evaluates to `TRUE` and the row is included in the final result. Otherwise, it evaluates to `FALSE` and the row is excluded.

### Example

Consider the following tables:

```
**Department Table**
| dep_id | department_name |
|---------|-------------------|
| 1       | Admin           |
| 2       | Support         |

**Employee Table**
| emp_id | dep_id | emp_name |
|---------|--------|----------|
| 1       | 1       | John     |
| 2       | 2       | Jane     |
```

The following query uses `NOT EXISTS` to find employees who do not work in the "Admin" department:

```sql
SELECT *
FROM Employee
WHERE NOT EXISTS (SELECT *
                   FROM Department
                   WHERE Department.department_name = 'Admin' AND Department.dep_id = Employee.dep_id);
``````

The subquery checks if there is any department with the name "Admin" and `dep_id` that matches the `dep_id` of the current employee. If such a department is not found (i.e., the subquery returns no records), the employee is included in the result.

### Benefits of Using NOT EXISTS

* **Ensures data integrity:** By eliminating rows based on conditions in a subquery, `NOT EXISTS` helps maintain referential integrity in your database.
* **Improves performance:** By using `NOT EXISTS` instead of a correlated subquery, you can often improve query execution performance.
* **Simplifies code:** `NOT EXISTS` provides a more concise and readable way to express certain conditions compared to using correlated subqueries.

### Note

* `NOT EXISTS` checks for the existence of records, not for their values.
* If the subquery returns more than one record, `NOT EXISTS` still evaluates to `FALSE`.**Understanding NOT EXISTS Subquery**

**Concept:****Concept:**

NOT EXISTS subquery is a way to check if a specific condition does not exist in a related table. It returns TRUE if the subquery returns no records and FALSE if it returns any records.

**Structure:**

```
SELECT ...
FROM table1
WHERE NOT EXISTS (
    SELECT ...
    FROM table2
    WHERE ...
)
```

**Example:**

Let's say we have a table called "Department" and we want to find all departments that do not have any employees assigned to them.

```
SELECT *
FROM Department
WHERE NOT EXISTS (
    SELECT *
    FROM Employee
    WHERE DepartmentID = Department.DepartmentID
)
```

**How it Works:**

1. For each record in the "Department" table, the subquery checks if there are any matching records in the "Employee" table based on the DepartmentID field.
2. If the subquery returns any records, the NOT EXISTS condition becomes FALSE.
3. If the subquery returns no records, the NOT EXISTS condition becomes TRUE, indicating that the department does not have any employees assigned to it.**Important Notes:**

* The subquery must return a single column (typically a primary key or unique column) for comparison.
* The comparison operator in the WHERE clause of the subquery is usually "=".
* NOT EXISTS is more efficient than using a LEFT JOIN and checking for NULL values in the joined column.
* NOT EXISTS can be used with other logical operators, such as AND and OR, to combine multiple conditions.**Correlated Subqueries**

**Concept:**
A correlated subquery is a subquery that references columns from the outer query. This allows the subquery to be evaluated for each row in the outer query, providing dynamic filtering or aggregation based on the current row.

**Key Details:**

* Connects two tables through a common column reference.
* Evaluates the subquery for each row in the outer query, creating a dynamic filter or calculation.
* Uses the keyword `EXISTS` to check for record existence or `NOT EXISTS` for non-existence.* Returns a Boolean value (True/False) that determines whether the outer query includes the current row.

**Steps to Use Correlated Subqueries:**

1. **Identify the relationship:** Determine which column(s) in the outer query should be used to connect to the subquery.
2. **Create the outer query:** Write the main query that includes the comparison with the subquery.
3. **Create the correlated subquery:** Construct the subquery that references the columns from the outer query. Use `EXISTS` or `NOT EXISTS` to check for record existence.
4. **Execute the query:** Combine the outer query and the subquery to retrieve the desired results.

**Example:**

**Syntax:**

```
SELECT column_list
FROM outer_table
WHERE EXISTS (SELECT 1
                FROM subquery_table
                WHERE subquery_column = outer_table.reference_column);
```

**Example:**

Find all departments that do not have any employees:

```
SELECT department_name
FROM department
WHERE NOT EXISTS (SELECT 1
                    FROM employeeWHERE NOT EXISTS (SELECT 1
                    FROM employee
                    WHERE department_id = department.department_id);
```

**Applications:**

* Checking for record existence or non-existence
* Filtering records based on dynamic criteria
* Aggregating data based on row-specific conditions
* Complex joins and data comparisons## Understanding Correlated Subqueries

### Introduction
- Correlated subqueries refer to subqueries whose execution depends on the values returned by the outer query.
- Unlike other subqueries, correlated subqueries are not executed independently but rather for each row processed in the outer query.

### Key Difference from Other Subqueries
- In standard subqueries, the subquery is executed only once and its result is used in the outer query.
- In correlated subqueries, the subquery is executed for each row processed in the outer query.
- This distinction is crucial because it affects the performance and behavior of the query.

### Syntax
```
SELECT column_list### Syntax
```
SELECT column_list
FROM outer_table
WHERE column_name IN (
    SELECT column_name
    FROM subquery
    WHERE subquery_column_name = outer_table.column_name
);
```

### How Correlated Subqueries Work
- The outer query retrieves a row and its values are used to compose the subquery.
- The subquery is executed for the current row and returns a result.
- The outer query continues to the next row and repeats the process until all rows are processed.

### Benefits of Correlated Subqueries
- Enable more complex data retrieval by allowing the subquery to depend on the outer query.
- Provide flexibility by customizing the subquery's behavior for each row in the outer query.

### Example
Consider the following query:

```
SELECT customer_name
FROM customers
WHERE customer_id IN (
    SELECT customer_id
    FROM orders
    WHERE product_id = 5
);
```

- The outer query retrieves customer names.
- The subquery finds customer IDs for orders with product ID 5.- The subquery finds customer IDs for orders with product ID 5.
- The outer query uses the customer IDs returned by the subquery to filter its results.

### Performance considerations
- Correlated subqueries can be less performant than standard subqueries due to multiple executions.
- Optimizations like indexing and query planning can improve performance.**Nested Subqueries**

**Overview:**

A nested subquery is a subquery that is embedded within another subquery. It can be used to solve complex data retrieval problems.

**Syntax:**

```
SELECT column_list
FROM outer_table
WHERE condition1 IN (
    SELECT column_list
    FROM subquery1
    WHERE condition2
);
```

**Example:**

Suppose we have a table of employees and a table of departments. We want to find the employees who work in departments with more than 5 employees.

```
SELECT employee_id, employee_name
FROM employees
WHERE department_id IN (
    SELECT department_id
    FROM departments
    WHERE num_employees > 5
);
```

**How it Works:**WHERE num_employees > 5
);
```

**How it Works:**

* The outer query retrieves employees from the `employees` table.
* The subquery `(SELECT department_id FROM departments WHERE num_employees > 5)` returns a set of department IDs with more than 5 employees.
* The `IN` condition compares the `department_id` column of the outer query with the subquery results.
* Employees with matching `department_id` values are selected.

**Benefits of Nested Subqueries:**

* Allow for complex data retrieval operations that are not possible with single subqueries.
* Increase SQL code readability and maintainability.
* Reduce the need for multiple joins, which can improve performance.

**Considerations:**

* Nested subqueries can be computationally expensive if the subquery is complex or the outer query returns a large number of rows.
* It's important to optimize subqueries using indexes and appropriate query plans.**Subqueries**

**Concept:****Concept:**
A subquery is a nested query within another query. It returns a set of data that is used in the outer query.

**Syntax:**
```
SELECT column_name
FROM table_name
WHERE condition IN (subquery)
```

**Example:**
```sql
-- Get stores with sales above average
SELECT store_name
FROM sales
WHERE sales > (
    SELECT AVG(sales)
    FROM sales
)
```

**Step-by-Step Explanation:**

**Step 1: Find the average sales across all stores**
```sql
SELECT AVG(sales)
FROM sales
```

**Step 2: Use the average sales value as a threshold**
```sql
WHERE sales > (
```

**Step 3: Execute the subquery**
```sql
SELECT AVG(sales)
FROM sales
)
```

**Step 4: Retrieve store names with sales above the threshold**
```sql
SELECT store_name
```

**Relevance:**
Subqueries are useful for combining data from multiple tables or for filtering data based on complex conditions. They provide a concise and efficient way to perform complex data analysis.## How to Calculate Store Sales Performance**Objective:** Determine which stores have sales that exceed the average sales across all stores.

### Step 1: Calculate Total Sales for Each Store

- **Reason:** To determine the average sales across all stores, we first need to know the total sales for each individual store.

- **Example:**
   - Store A:
     - Sale 1: 16,500
     - Sale 2: 7,500
     - Total Sales: 24,000

### Step 2: Calculate Average Sales Across All Stores

- **Formula:** Average Sales = Total Sales Across All Stores / Number of Stores

- **Example:**
   - Total Sales Across All Stores: 100,000
   - Number of Stores: 5
   - Average Sales: 100,000 / 5 = 20,000

### Step 3: Compare Store Sales to Average Sales

- **Criteria:**
   - Stores with Total Sales > Average Sales are considered performing better than average.

- **Example:**
   - Store A Total Sales: 24,000
   - Average Sales: 20,000
   - Store A Performance: Better than average**Structured Markdown Notes on SQL Aggregation**

**Concept 1: Data Segregation and Grouping****Concept 1: Data Segregation and Grouping**

* **Purpose:** To organize data into groups based on common attributes.
* **Syntax:** `GROUP BY column_name`
* **Example:** To find the total sales for each store, we can group the data by store name:
```
SELECT store_name, SUM(price) AS total_sales
FROM sales
GROUP BY store_name;
```

**Concept 2: Aggregation Functions**

* **Purpose:** To calculate summary statistics from grouped data.
* **Common Functions:**
    * SUM: Adds values
    * COUNT: Counts values
    * AVG: Calculates the average value
* **Syntax:** `AGGREGATE_FUNCTION(column_name) AS alias`
* **Example:** To find the average sales for each store, we can use the AVG function:
```
SELECT store_name, AVG(price) AS avg_sales
FROM sales
GROUP BY store_name;
```

**Step-by-Step Explanation:**

1. **Segregate Data:** Use the `GROUP BY` clause to group the data based on the desired attribute (e.g., store name).2. **Calculate Summary Statistics:** Use aggregation functions like SUM or AVG to calculate the desired statistics for each group.
3. **Alias the Result:** Use the `AS` keyword to assign a meaningful name to the calculated value (e.g., `total_sales` or `avg_sales`).
4. **Execute the Query:** Run the SQL query to retrieve the summarized data.**How to Calculate Average Sales Across Stores**

**Concept:**

* To calculate the average sales across multiple stores, we need to consider only one unique sales record per store and then find the mean of those individual store sales.

**Steps:**

1. **Create a subquery:**

   ```
   (SELECT DISTINCT store_id, SUM(sales) AS total_sales FROM sales_table GROUP BY store_id)
   ```

   This subquery identifies each unique store ID and calculates the total sales for each store.

2. **Use the subquery:**

   ```
   SELECT AVG(total_sales) AS average_sales FROM (SELECT DISTINCT store_id, SUM(sales) AS total_sales FROM sales_table GROUP BY store_id)
   ``````

   This query uses the subquery as its data source and calculates the average sales by taking the mean of the `total_sales` column.

3. **Alias the result:**

   ```
   SELECT AVG(total_sales) AS average_sales FROM (SELECT DISTINCT store_id, SUM(sales) AS total_sales FROM sales_table GROUP BY store_id) AS store_sales
   ```

   This aliases the result to `average_sales` for easy reference.

4. **Execute the query:**

   Once the query is executed, the result will be the average sales across all the stores.**Understanding Subqueries and Joins**

**What is a Subquery?**

* A subquery is a nested query within another query.
* It can be used to retrieve data that is used within the main query.
* Subqueries are enclosed in parentheses `()`.

**What is a Join?**

* A join is used to combine rows from multiple tables based on a common field or condition.
* Joins create a new table with the combined rows.

**Example of Subquery and Join****Example of Subquery and Join**

The given text demonstrates how to compare the results of two subqueries using a join:

**Step 1: Subquery 1**
```sql
SELECT store_id, SUM(sales) AS total_sales
FROM sales_table
GROUP BY store_id;
```
* Retrieves the total sales for each store.

**Step 2: Subquery 2**
```sql
SELECT store_id, AVG(sales) AS average_sales
FROM sales_table
GROUP BY store_id;
```
* Retrieves the average sales for each store.

**Step 3: Join**
```sql
SELECT sales.store_id, sales.total_sales, average_sales.average_sales
FROM (
  SELECT store_id, SUM(sales) AS total_sales
  FROM sales_table
  GROUP BY store_id
) AS sales
JOIN (
  SELECT store_id, AVG(sales) AS average_sales
  FROM sales_table
  GROUP BY store_id
) AS average_sales
ON sales.store_id = average_sales.store_id;
```
* Compares the total sales and average sales for each store by joining the two subqueries on the `store_id` column.

**Result:**
```
| store_id | total_sales | average_sales |
|---|---|---|
| 1 | 1000 | 200 ||---|---|---|
| 1 | 1000 | 200 |
| 2 | 2000 | 400 |
```

By using subqueries and joins, you can perform complex data comparisons and retrieve the desired information efficiently.**Understanding SQL Subqueries with Greater Than Comparisons**

**Introduction:**
In SQL, subqueries allow us to embed a query within another query. This enables us to perform complex analysis and data comparisons. One common use case is to compare values from a subquery to the values in the outer query.

**Greater Than Comparison:**
To compare values using the greater than operator (>), we use the following syntax:

```sql
SELECT * FROM table
WHERE column_name > (subquery);
```

**Example:**
Consider the following example where we want to find the stores with total sales greater than the average sales:

```sql
SELECT *
FROM sales
WHERE total_sales > (
    SELECT AVG(sales)
    FROM sales
);
```

**Explanation:**
- The outer query selects all rows from the 'sales' table.- The outer query selects all rows from the 'sales' table.
- The subquery calculates the average sales using the AVG() function.
- The outer query uses the greater than operator to compare the total sales of each row with the average sales.

**Step-by-Step Breakdown:**

1. **Identify the Outer Query Table:** The outer query operates on the 'sales' table, which contains sales data.
2. **Define the Subquery:** The subquery calculates the average sales using the AVG() function, which is applied to the 'sales' column.
3. **Compare Values:** The outer query uses the greater than operator (>), which compares the 'total_sales' column with the average sales calculated in the subquery.
4. **Execute the Query:** When executed, the query returns only the rows from 'sales' where the total sales are higher than the average.

**Additional Notes:**

- Ensure that the columns being compared have compatible data types.
- Use parentheses to clearly group the subquery within the WHERE clause.- Consider using aliases for subqueries to make the code more readable.**Nested Subqueries**

**Concept:**

Nested subqueries involve embedding subqueries within other queries. Multiple subqueries can be combined to retrieve complex data.

**Example:**

The provided query uses multiple nested subqueries to filter data based on various conditions. It consists of an outer query with three subqueries:

```
SELECT *
FROM table
WHERE field IN (
  SELECT field
  FROM subquery1
  WHERE condition1
)
AND field2 IN (
  SELECT field2
  FROM subquery2
  WHERE condition2
)
AND field3 IN (
  SELECT field3
  FROM subquery3
  WHERE condition3
);
```

**Execution Order:**

Nested subqueries are executed from the innermost subquery outwards:

1. **subquery3** retrieves field3 values based on condition3.
2. **subquery2** retrieves field2 values based on condition2 and the results of subquery3.
3. **subquery1** retrieves field values based on condition1 and the results of subquery2.4. The **outer query** selects rows from the "table" table where field satisfies the conditions specified in subquery1.

**Nested Depth:**

The example query has three nested subqueries, but it is possible to have even deeper levels of nesting. However, excessive nesting can make queries harder to read and debug.

**Performance Considerations:**

Nested subqueries can impact performance, especially when they are complex or involve large datasets. It's recommended to avoid unnecessary nesting and explore alternative query optimization techniques.**Notes on Using the WITH Clause in SQL**

**Introduction:**

The WITH clause allows you to define temporary named queries, which can be reused multiple times within a larger query. This can improve performance and simplify complex queries.

**Syntax:**

```
WITH <query name> AS (<subquery>)
SELECT ...
FROM ...
```

**Steps to Use the WITH Clause:**

1. **Define the Named Subquery:**1. **Define the Named Subquery:**
   Use the WITH clause to define a named subquery. The subquery can be any SELECT statement.
2. **Assign a Name to the Subquery:**
   Give the subquery a unique name, which you will use to reference it later.
3. **Use the Name in the Main Query:**
   In the main SELECT statement, replace the subquery with its name from the WITH clause.

**Example:**

Consider the following query:

```
SELECT SUM(sales)
FROM (
  SELECT SUM(amount) AS sales
  FROM sales_table
  WHERE region = 'North'
);
```

We can rewrite this query using the WITH clause:

```
WITH sales AS (
  SELECT SUM(amount) AS sales
  FROM sales_table
  WHERE region = 'North'
)
SELECT SUM(sales)
FROM sales;
```

**Benefits of Using the WITH Clause:**

* **Improved Performance:** By defining the subquery once in the WITH clause, the database engine only needs to execute it once, even if it is used multiple times in the main query.* **Simplified Queries:** The WITH clause makes complex queries easier to read and understand by separating the subquery from the main query.
* **Reusability:** Named subqueries can be reused in different queries, reducing the need to repeat code.**Nested Subqueries**

**Introduction**
- Nested subqueries are queries within queries that can enhance data retrieval and manipulation capabilities.

**Using the WITH Clause**

- **What is it?** A WITH clause allows you to define a temporary named subquery that can be referenced later in the main query.
- **Syntax:**
```
WITH <Subquery Name> AS (
  <Subquery>
)
SELECT ... FROM ... WHERE ...;
```

**Example**
- In the provided text, the subquery used multiple times in the main query is extracted and defined as a named subquery within the WITH clause:
```
WITH sales AS (
  SELECT ... FROM ... WHERE ...
)
SELECT ... FROM ... WHERE ...;
```

**Benefits of using WITH Clause**```

**Benefits of using WITH Clause**
- **Code Reusability:** Avoids repeating the same subquery multiple times in the main query, improving code readability and maintainability.
- **Optimized Execution:** By pre-calculating and storing the subquery's result in a temporary named relation, the database can improve query performance.

**Additional Tips**

- Give meaningful names to your named subqueries for easy identification and understanding.
- Use the WITH clause judiciously, only when necessary, to avoid excessive nesting and complexity.
- Remember to define the named subquery before referencing it in the main query.**SQL Subqueries**

**Introduction**

A subquery is a query within another query. It allows us to perform advanced data retrieval and manipulation operations.

**Clauses Where Subqueries Can Be Used**

SQL provides four clauses where subqueries can be utilized:

1. **SELECT**
2. **FROM**
3. **WHERE**
4. **HAVING**

**Syntax**

Subqueries typically use the following syntax:

```sqlSubqueries typically use the following syntax:

```sql
SELECT [columns]
FROM (
    [subquery]
)
[alias];
```

**Examples**

**1. Subquery in SELECT Clause:**

Retrieve employees with salaries greater than the average salary.

```sql
SELECT employee_id, name, salary
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```

**2. Subquery in FROM Clause:**

Create a view of employees with their respective department names.

```sql
CREATE VIEW employee_view AS
SELECT e.employee_id, e.name, d.department_name
FROM employees e
JOIN departments d ON e.department_id = d.department_id;
```

**3. Subquery in WHERE Clause:**

Find orders placed by customers who have made more than two purchases.

```sql
SELECT order_id, customer_id
FROM orders
WHERE customer_id IN (
    SELECT customer_id
    FROM customers
    GROUP BY customer_id
    HAVING COUNT(*) > 2
);
```

**4. Subquery in HAVING Clause:**);
```

**4. Subquery in HAVING Clause:**

Group employees by department and display only those departments with an average salary above a certain threshold.

```sql
SELECT department_id, AVG(salary) AS avg_salary
FROM employees
GROUP BY department_id
HAVING avg_salary > (
    SELECT AVG(salary) FROM employees
);
```**Subqueries in SQL**

**Introduction:**

A subquery is a nested query that returns a dataset that is used in the main query. It allows you to perform complex data retrieval operations within a single query.

**Using a Subquery in the SELECT Clause:**

**Note:** Using a subquery in the SELECT clause is generally not recommended due to performance implications.

**Syntax:**

```
SELECT column_name,
       (SELECT other_column_name FROM other_table WHERE ...) AS subquery_alias
FROM table_name;
```

**Example:**

```
SELECT employee_name,
       (SELECT MAX(salary) FROM salaries WHERE employee_id = employee_id) AS max_salary
FROM employees;
```

**Alternative Approach:**FROM employees;
```

**Alternative Approach:**

A better practice is to use a JOIN instead of a subquery in the SELECT clause.

**Syntax:**

```
SELECT employee_name,
       MAX(salary) AS max_salary
FROM employees
JOIN salaries ON employees.employee_id = salaries.employee_id
GROUP BY employee_name;
```

**Using a Subquery in the HAVING Clause:**

**Syntax:**

```
SELECT column_name
FROM table_name
GROUP BY grouping_column
HAVING (SELECT aggregate_function(other_column_name) FROM other_table WHERE ...) AS subquery_alias;
```

**Example:**

```
SELECT department_name
FROM employees
GROUP BY department_name
HAVING (SELECT COUNT(*) FROM employees WHERE department_name = department_name) > 5;
```

This query fetches all department names where the number of employees in each department is greater than 5.**Markdown Notes on SQL Query to Identify Employees Earning Above Average Salary**

**Objective:**

* Learn how to use SQL to identify employees earning more than the average salary.

**Steps:****Steps:**

1. **Select All Employee Data**

```sql
SELECT *
FROM Employee;
```

2. **Create a Remarks Column**

```sql
SELECT *,
(CASE WHEN Salary > (SELECT AVG(Salary) FROM Employee) THEN 'Earning above average salary' ELSE 'Earning below average salary' END) AS Remarks
FROM Employee;
```

**Explanation:**

* The outer `SELECT` statement retrieves all columns from the `Employee` table.
* The inner `SELECT` statement calculates the average salary menggunakan the `AVG()` function.
* The `CASE` statement checks if the employee's salary (`Salary`) is greater than the average salary.
* If true, the Remarks column displays "Earning above average salary."
* If false, the Remarks column displays "Earning below average salary."

**Example:**

Given the following `Employee` table:

| ID | Name | Salary |
|---|---|---|
| 1 | John Smith | 5000 |
| 2 | Jane Doe | 6000 |
| 3 | Mark Jones | 4000 |

**Output:**

| ID | Name | Salary | Remarks |
|---|---|---|---|
| 1 | John Smith | 5000 | Earning below average salary || 1 | John Smith | 5000 | Earning below average salary |
| 2 | Jane Doe | 6000 | Earning above average salary |
| 3 | Mark Jones | 4000 | Earning below average salary |**Markdown Notes on Subqueries**

**Introduction**
- Subqueries are nested queries used within another SQL statement.
- They allow you to retrieve data from multiple tables or perform complex calculations.

**Types of Subqueries**
- **Scalar Subqueries:** Return a single value (one row, one column). Used in conditions and arithmetic expressions.
- **Row Subqueries:** Return multiple rows, forming a temporary table. Used in operations like IN, EXISTS, and ANY.

**Scalar Subquery Example: Comparing Salary to Average**

```
CASE
  WHEN salary > (SELECT AVG(salary) FROM employee)
  THEN 'Higher than average'
  ELSE 'Lower than or equal to average'
END
```

- Compares each employee's salary to the average salary.
- Returns a single column with values 'Higher than average' or 'Lower than or equal to average'.

**Syntax:**

```
CASE**Syntax:**

```
CASE
  WHEN <condition>1 THEN <result>1
  WHEN <condition>2 THEN <result>2
  ...
  ELSE <default_result>
END
```

**Key Points:**

- Use scalar subqueries when you need to compare values or perform calculations using data from another table.
- Ensure the subquery returns a single record and column.
- Scalar subqueries can be used in WHERE, HAVING, and ORDER BY clauses.## SQL: Using Subqueries in the SELECT Clause

### Core Concepts

- A subquery is a query nested within another query.
- Subqueries can be used to perform more complex data retrieval and manipulation.

### Types of Subqueries

There are two main types of subqueries:

- **Correlated Subqueries:** Refer to the outer query's table in their WHERE clause.
- **Scalar Subqueries:** Return a single value that is used in the outer query.

### Using Subqueries in the SELECT Clause

To use a subquery in a SELECT clause:

1. Write the outer query.
2. Use `SELECT` to define the columns you want to retrieve.2. Use `SELECT` to define the columns you want to retrieve.
3. Include the subquery as an expression within the `SELECT` clause.

### Example: Adding a Flag to Employees Based on Salary

**Query:**

```sql
SELECT
    name,
    salary,
    CASE
        WHEN salary > (SELECT AVG(salary) FROM employees)
        THEN 'Higher than average'
        ELSE NULL
    END AS salary_flag
FROM
    employees;
```

**Explanation:**

- The outer query selects the `name`, `salary`, and a new column called `salary_flag`.
- `salary_flag` is a `CASE` expression that compares the employee's salary to the average salary (obtained through the subquery).
- If the salary is greater than the average, it displays "Higher than average." Otherwise, it displays `NULL`.

### Advantages of Using Subqueries

- Allows for more flexibility and data manipulation.
- Simplifies complex queries by encapsulating additional logic.

### Alternatives to Subqueries### Alternatives to Subqueries

In some cases, you may be able to rewrite a query with a subquery using alternative methods, such as:

- **Joins:** Linking tables based on common columns.
- **Derived tables (CTEs):** Creating temporary tables to store intermediate results.## Avoiding Subqueries in SELECT Clauses

**Problem:**
Using a SELECT query inside another SELECT clause (known as a subquery) can slow down query execution.

**Solution:**
Instead of using a subquery in the SELECT clause, move the subquery to the JOIN condition.

**Reason:**
When a subquery is used in the SELECT clause, it is executed for every row in the outer query, resulting in redundant processing.

## Example

**Original Query with Subquery:**

```sql
SELECT
  employee_id,
  employee_name,
  (SELECT AVG(salary) FROM salary_details WHERE employee_id = employee_table.employee_id) AS average_salary
FROM
  employee_table;
```

**Modified Query with Subquery in JOIN Condition:**

```sql
SELECT
  employee_id,
  employee_name,```sql
SELECT
  employee_id,
  employee_name,
  avg_salary.average_salary
FROM
  employee_table
JOIN
  (SELECT employee_id, AVG(salary) AS average_salary FROM salary_details GROUP BY employee_id) AS avg_salary
  ON employee_table.employee_id = avg_salary.employee_id;
```

In this modified query, the subquery is moved to the JOIN condition, where it is executed only once. This avoids redundant processing and improves query performance.**Expert Notes on Nested Queries: Using Subqueries in the FROM Clause**

**What is a Nested Query?**

* A query within another query
* Allows you to use the results of one query in a larger query

**Using a Subquery in the FROM Clause**

* Step 1: Create a subquery (an inner query) that returns a specific set of data
* Step 2: Assign an alias (a name) to the subquery
* Step 3: Use the alias to reference the subquery in the FROM clause of the outer query

**Example:**

```sql
-- Subquery to find average salary for each department
SELECT
  dept_id,
  AVG(salary) AS average_salarySELECT
  dept_id,
  AVG(salary) AS average_salary
FROM employees
GROUP BY dept_id;

-- Outer query using the subquery in the FROM clause
SELECT
  *
FROM (
  -- Subquery alias: avg_salaries
  SELECT
    dept_id,
    AVG(salary) AS average_salary
  FROM employees
  GROUP BY dept_id
) AS avg_salaries;
```

**Benefits of Using a Subquery in the FROM Clause:**

* Simplifies complex queries
* Improves performance by avoiding unnecessary joins
* Makes queries more readable and maintainable

**Additional Notes:**

* The subquery must return at least one column
* The alias must be unique and not conflict with other table names
* Subqueries in the FROM clause can be used in the SELECT, WHERE, HAVING, and ORDER BY clauses**Markdown Notes: Finding Stores with Above-Average Sales Units**

**Introduction:**
The goal is to identify stores that have sold more units than the average number of units sold by all stores. To achieve this, we'll use a subquery in the HAVING clause.

**Steps:**

1. **Select Store Information:****Steps:**

1. **Select Store Information:**
   - Start by selecting the relevant information from the sales table, which contains store information:
     ```sql
     SELECT * FROM sales;
     ```

2. **Group by Store:**
   - Use the GROUP BY clause to group the data by the store name:
     ```sql
     SELECT store_name,
     ```

3. **Calculate Sold Units:**
   - Calculate the total number of units sold for each store using the SUM() aggregate function:
     ```sql
     SUM(quantity) AS total_units_sold
     ```

4. **Calculate Average Units Sold:**
   - In a subquery, calculate the average number of units sold across all stores:
     ```sql
     (SELECT AVG(total_units_sold) FROM sales) AS avg_units_sold
     ```

5. **Filter Stores:**
   - Use the HAVING clause to filter the stores based on whether their total units sold exceed the average:
     ```sql
     HAVING total_units_sold > avg_units_sold
     ```

**Complete Query:**

```sql
SELECT store_name
FROM sales
GROUP BY store_name```sql
SELECT store_name
FROM sales
GROUP BY store_name
HAVING SUM(quantity) > (SELECT AVG(total_units_sold) FROM sales);
```

**Example:**

Consider a sales table with the following data:

| store_name | quantity |
|---|---|
| Store A | 100 |
| Store B | 150 |
| Store C | 200 |
| Store D | 120 |

The average units sold is 142.5 (100 + 150 + 200 + 120) / 4.

Using the above query, the result would be:

| store_name |
|---|---|
| Store C |

Store C sold 200 units, which is greater than the average units sold, hence it is selected.## Advanced SQL: Grouping and Aggregation with Average Calculations

**Objective:**

To understand how to group data, calculate aggregate values (like sum), and filter results using average calculations.

**Grouping Data:**

* Use the `GROUP BY` clause to group rows with similar values.
* Example: `SELECT store_name, SUM(quantity) FROM sales GROUP BY store_name;`

**Aggregation Functions:**

* `SUM()`: Calculates the total of a specified column.* `SUM()`: Calculates the total of a specified column.
* Example: `SUM(quantity)` adds up the quantity of items sold for each store.

**Finding Average Values:**

* Calculate the average using the `AVG()` function.
* Example: `AVG(quantity)` returns the average quantity sold across all stores.

**Filtering Results:**

* Use `HAVING` to filter grouped results based on aggregate conditions.
* Example: `HAVING SUM(quantity) > AVG(quantity)` returns stores with above-average sales.

**Putting It All Together:**

To find stores with above-average sales:

```
SELECT store_name, SUM(quantity) AS total_quantity
FROM sales
GROUP BY store_name
HAVING total_quantity > (SELECT AVG(quantity) FROM sales);
```

**Explanation:**

* Group sales by store name and calculate the total quantity sold.
* Find the average quantity sold across all stores.
* Filter the results to show only stores with total sales greater than the average.**Markdown Notes on Subquery Usage**

**Concept: Subqueries****Concept: Subqueries**

* A subquery is a nested query that can be used inside another query.
* It allows you to incorporate complex filtering or calculations into the main query.

**Types of Subqueries:**

* **Scalar Subqueries:** Return a single value (e.g., average, count, maximum).
* **Correlated Subqueries:** Reference values from the outer query in their WHERE clause.

**Example of a Scalar Subquery:**

```sql
SELECT store_id, SUM(quantity) AS sold
FROM sales
GROUP BY store_id
HAVING sold > (
    SELECT AVG(quantity)
    FROM sales
);
```

**Explanation:**

* This query selects store IDs and the total quantity sold by each store.
* The HAVING clause uses a subquery to compare the total quantity sold with the average quantity sold across all stores.
* Only stores with sales above the average are returned.

**Advantages of Using Subqueries:**

* Enhanced data filtering and aggregation
* Simplification of complex queries
* Improved performance (compared to multiple JOINs)

**Syntax:**

```sql**Syntax:**

```sql
SELECT [columns]
FROM [table]
[WHERE [conditions]]
[GROUP BY [columns]]
[HAVING [conditions that include a subquery]]
```

**Additional Tips:**

* Subqueries are enclosed in parentheses.
* The subquery's columns must have compatible data types with the columns being compared in the outer query.
* Use parentheses around the subquery's name in the HAVING clause to avoid ambiguity with other column names.**Subqueries in HAVING Clause**

**Prerequisites:**
- Understanding of SQL subqueries
- Familiarity with the HAVING clause

**Concept:**
The HAVING clause is used in conjunction with a GROUP BY clause to filter the grouped results. A subquery can be used within the HAVING clause to apply more complex filtering conditions.

**Example:**

Suppose we have a table called `sales` with the following columns:
```
store_name | units_sold
```

To find all stores that have sold more than the average number of units:

```sql
SELECT store_name
FROM sales
GROUP BY store_name```sql
SELECT store_name
FROM sales
GROUP BY store_name
HAVING units_sold > (SELECT AVG(units_sold) FROM sales);
```

**Explanation:**

- The outer query groups the sales by store and selects the store names.
- The subquery in the HAVING clause calculates the average units sold for all stores.
- The HAVING clause then checks if the units sold for the current store is greater than the average.

**Benefits of Using Subqueries in HAVING Clause:**

- Allows for more complex filtering conditions.
- Can be used to compare group results with values from other tables or queries.
- Provides a flexible way to filter grouped data based on custom criteria.**SQL Subqueries in Various Commands**

**Introduction**
In SQL, a subquery is a nested query that returns a result set used within another query. While subqueries are commonly used in SELECT statements, they can also be employed in other commands such as INSERT, UPDATE, and DELETE.

**Subqueries in INSERT****Subqueries in INSERT**
- Subqueries can be used in the INSERT command to selectively insert data into a table based on specific criteria.
- Syntax:
```
INSERT INTO table_name (column1, column2, ...)
SELECT column1, column2, ...
FROM subquery;
```
- Example: Inserting unique employee history records:
```
INSERT INTO employee_history (employee_id, hire_date, ...)
SELECT employee_id, hire_date, ...
FROM subquery
WHERE NOT EXISTS (
    SELECT 1
    FROM employee_history
    WHERE employee_id = subquery.employee_id
);
```

**Subqueries in UPDATE**
- Subqueries can be used in the UPDATE command to modify data in a table based on conditions defined by the subquery.
- Syntax:
```
UPDATE table_name
SET column1 = subquery_expression, ...
WHERE subquery_condition;
```
- Example: Updating employee salaries:
```
UPDATE employees
SET salary = (
    SELECT MAX(salary)
    FROM employee_history
    WHERE employee_id = employees.employee_id
);
```

**Subqueries in DELETE**);
```

**Subqueries in DELETE**
- Subqueries can be used in the DELETE command to remove data from a table based on criteria defined by the subquery.
- Syntax:
```
DELETE FROM table_name
WHERE subquery_condition;
```
- Example: Deleting duplicate employee records:
```
DELETE FROM employees
WHERE employee_id IN (
    SELECT employee_id
    FROM (
        SELECT employee_id, ROW_NUMBER() OVER (PARTITION BY employee_id ORDER BY hire_date DESC) AS rn
        FROM employees
    ) AS subquery
    WHERE rn > 1
);
```

**Conclusion**
Subqueries provide a powerful way to enhance the functionality of SQL commands beyond SELECT statements. By understanding how to use subqueries in INSERT, UPDATE, and DELETE, you can efficiently insert, modify, and delete data while maintaining data integrity and avoiding duplicates.## How to Populate a History Table

**Core Concept:**
- A history table is a separate table used to store past or historical data of a related entity.

### Step-by-Step Explanation:### Step-by-Step Explanation:

**1. Create a History Table:**
- Design and create a table specifically for storing historical data.
- Include relevant fields to track the required information.

**2. Referential Integrity:**
- Establish foreign key relationships between the history table and the original data source table(s).
- This ensures that data in the history table can be traced back to the original records.

**3. Populate the History Table:**
- Insert historical data into the history table on a regular basis (e.g., daily, weekly).
- This can be done through automated processes (e.g., SQL scripts, ETL tools) or manually.

**4. Clean Up Original Table:**
- Regularly purge or archive old data from the original data source table to maintain performance and storage efficiency.
- Move the purged data to the history table for retention and historical analysis.

### Example:

**Original Table:** Employee
| EmployeeID | EmployeeName | DepartmentID | Salary | Location |
|---|---|---|---|---||---|---|---|---|---|
| 1 | John Smith | 10 | 50,000 | New York |

**History Table:** EmployeeHistory
| EmployeeID | EmployeeName | DepartmentID | Salary | Location | Date |
|---|---|---|---|---|---|
| 1 | John Smith | 10 | 50,000 | New York | 2023-06-01 |

### Syntax (SQL):

```sql
-- Insert data into History Table
INSERT INTO EmployeeHistory (EmployeeID, EmployeeName, DepartmentID, Salary, Location, Date)
SELECT EmployeeID, EmployeeName, DepartmentID, Salary, Location, GETDATE()
FROM Employee;

-- Clean Up Original Table
DELETE FROM Employee
WHERE EmployeeID IN (SELECT EmployeeID FROM EmployeeHistory);
```**Topic: Data Migration Using SQL Subqueries**

## Step-by-Step Guide

### 1. Define Your Objective
- You want to populate a new table, `employee_history`, with data from existing tables, `employee` and `department`.

### 2. Create an INSERT Statement with a Subquery
- Use the `INSERT` statement to specify the target table, `employee_history`.- Within the `INSERT` statement, use a subquery to select the necessary data from the `employee` and `department` tables.

### 3. Construction of the Subquery
- Start with the `SELECT` statement to specify the columns to be fetched.
- From the `employee` table, select the required columns.
- Join the `employee` table with the `department` table using a suitable join condition.
- Select the necessary column from the `department` table, such as `location`.

**Syntax:**

```sql
INSERT INTO employee_history (column1, column2, ...)
SELECT column1, column2, ...
FROM employee
JOIN department ON employee.department_id = department.department_id;
```

**Example:**

```sql
INSERT INTO employee_history (employee_id, name, location)
SELECT employee_id, name, location
FROM employee
JOIN department ON employee.department_id = department.department_id;
```**Markdown Notes on Inserting Data into 'Employee History' Table**

**Introduction****Introduction**

The task at hand is to insert data from table `E` (employees) into table `D` (departments) based on certain conditions and constraints. Let's break down the process into clear steps:

**1. Selecting Specific Columns**

To insert data, we must specify the columns that we want to transfer from table `E` to table `D`. From the text, we identify the following columns:

- `E.employee_ID`
- `E.emp_name`
- `D.department_name`
- `E.salary`
- `D.location`

**2. Insert Statement with Conditions**

The `INSERT` statement will follow this syntax:

```sql
INSERT INTO D (column1, column2, ...)
SELECT column1, column2, ...
FROM E
WHERE ...
```

The `WHERE` clause ensures that only specific rows are inserted based on the following criteria:

- `D.department_name` should match `E.department_name`

**3. Preventing Duplicate Insertions****3. Preventing Duplicate Insertions**

To prevent inserting duplicate employee information, we add a `NOT EXISTS` clause as a subquery. This checks if the employee's information already exists in the `Employee History` table before inserting.

```sql
INSERT INTO D (column1, column2, ...)
SELECT column1, column2, ...
FROM E
WHERE NOT EXISTS (SELECT 1 FROM EmployeeHistory WHERE ...)
```

**4. Correlated Subquery**

A correlated subquery is used to compare data from the current row we're inserting into table `D` with the data in the `Employee History` table. This ensures that the `NOT EXISTS` clause operates on data related to the specific department being inserted.

**Example**

Assuming the `Employee History` table has columns `employee_ID`, `department_name`, and `start_date`, the correlated subquery would look like this:

```sql
NOT EXISTS (SELECT 1 FROM EmployeeHistory WHERE employee_ID = E.employee_ID AND department_name = D.department_name)
```

**Conclusion**```

**Conclusion**

By following these steps and syntax, you can ensure that employee data from table `E` is inserted into table `D` while preventing duplicate insertions and maintaining data integrity.**Understanding JOIN Queries with WHERE Conditions**

**Introduction**

* A JOIN query combines rows from two or more tables based on a common field.
* A WHERE condition filters the rows retrieved from the joined tables.

**Core Concepts**

**JOIN Query:**

* Connects two or more tables based on a common field.
* Syntax: `SELECT columns FROM table1 JOIN table2 ON table1.field = table2.field`

**WHERE Condition:**

* Filters the rows retrieved from the JOIN query.
* Syntax: `WHERE condition`

**Example: Employee History Table**

* **Objective:** Insert employee details from the Employee (E) and Department (D) tables into the Employee History (EH) table.
* **Query:**
```
SELECT * FROM EH
WHERE
  EH.EMP_ID = E.EMP_ID;
```

**Explanation:**

* This query joins the EH and E tables on the EMP_ID field.* This query joins the EH and E tables on the EMP_ID field.
* It retrieves all columns from the EH table for each employee in the E table.

**Preventing Duplicate Insertions**

* Without a WHERE condition, the same employee details could be inserted multiple times into the EH table if the query is executed multiple times.
* **WHERE Condition with NOT EXISTS:**
```
SELECT * FROM EH
WHERE
  NOT EXISTS (
    SELECT * FROM EH
    WHERE
      EH.EMP_ID = E.EMP_ID
  );
```

**Explanation:**

* This modified query uses a nested WHERE condition with NOT EXISTS to check if an employee record already exists in the EH table.
* If a record exists, the row is not inserted.
* This ensures that duplicate records are not inserted, even if the query is executed multiple times.**Concept: Using NOT EXISTS to Check for Missing Data**

**Objective:** To understand how to use NOT EXISTS to check if a record exists in a table.

**Step 1: NOT EXISTS Subquery****Step 1: NOT EXISTS Subquery**

* Use a subquery to query a table (e.g., employee_history) for a specific value (e.g., employee ID).
* If the subquery returns any records, the NOT EXISTS condition is 'false'.
* If the subquery returns no records, the NOT EXISTS condition is 'true'.

**Syntax:**

```sql
SELECT *
FROM table_1
WHERE NOT EXISTS (
  SELECT *
  FROM table_2
  WHERE condition
);
```

**Example:**

```sql
SELECT *
FROM employees
WHERE NOT EXISTS (
  SELECT *
  FROM employee_history
  WHERE employee_id = employees.id
);
```

This query returns all employees who do not have any records in the employee_history table.

**Step 2: Combining with AND/OR**

* The NOT EXISTS condition can be combined with AND or OR operators to filter results further.
* For example, the following query returns employees who have a salary greater than $50,000 and are not in the employee_history table:

```sql
SELECT *
FROM employees
WHERE salary > 50000
AND NOT EXISTS (
  SELECT *
  FROM employee_historyAND NOT EXISTS (
  SELECT *
  FROM employee_history
  WHERE employee_id = employees.id
);
```## Subqueries in SQL INSERT and UPDATE Statements

### Subqueries in INSERT Statements

**Purpose:** To insert data into a table based on the results of a subquery.

**Syntax:**

```sql
INSERT INTO target_table (column1, column2, ...)
SELECT column1, column2, ...
FROM subquery;
```

**Explanation:**
* `target_table` is the table where the data will be inserted.
* `column1`, `column2`, ... are the columns in the target table that will receive the data.
* `subquery` is a query that returns the data to be inserted.

**Example:**

```sql
INSERT INTO employee_history (location_id, employee_id, start_date)
SELECT location_id, employee_id, start_date
FROM new_employee_data
WHERE location_id NOT IN (SELECT location_id FROM employee_history);
```
This query inserts location data from the `new_employee_data` table into the `employee_history` table, excluding locations that already exist in `employee_history`.### Subqueries in UPDATE Statements

**Purpose:** To update data in a table based on the results of a subquery.

**Syntax:**

```sql
UPDATE target_table
SET column1 = subquery_value1, column2 = subquery_value2, ...
WHERE condition;
```

**Explanation:**
* `target_table` is the table whose data will be updated.
* `column1`, `column2`, ... are the columns in the target table that will be updated.
* `subquery_value1`, `subquery_value2`, ... are the values to be assigned to the corresponding columns.
* `condition` is a filter to specify which rows will be updated.

**Example:**

```sql
UPDATE employee_table
SET salary = (SELECT MAX(salary) FROM employee_table)
WHERE job_title = 'Manager';
```
This query updates the salaries of all employees with the job title 'Manager' to be the maximum salary in the `employee_table`.**Markdown Notes: Employee Salary Increment**

**Objective:**
Increment the salary of all employees in the Banglore location by 10% based on the maximum salary in their department.**Step-by-Step Guide:**

1. **Find Maximum Salary in Each Department:**

```sql
SELECT department_id, MAX(salary) AS max_salary
FROM employee_history
GROUP BY department_id
```

2. **Calculate 10% Increment:**

```sql
SELECT department_id, max_salary * 0.10 AS increment_amount
FROM (
    SELECT department_id, MAX(salary) AS max_salary
    FROM employee_history
    GROUP BY department_id
) AS subquery
```

3. **Update Salary for Banglore Location Employees:**

```sql
UPDATE employee
SET salary = CASE
    WHEN department_id IN (
        SELECT department_id
        FROM (
            SELECT department_id, MAX(salary) AS max_salary
            FROM employee_history
            GROUP BY department_id
        ) AS subquery
    ) AND location = 'Banglore' AND department_id IN (
        SELECT department_id
        FROM employee_history
    )
    THEN salary + increment_amount
    ELSE salary
END
WHERE location = 'Banglore';
```

**Explanation:**END
WHERE location = 'Banglore';
```

**Explanation:**

* The subquery in step 1 retrieves the maximum salary for each department.
* The subquery in step 2 calculates the 10% increment based on the maximum salaries.
* The CASE statement in step 3 updates the employee's salary only if they are in the Banglore location and have data in the employee_history table.

**Note:** This solution assumes that the employee's current salary is not already increased by 10%.## Updating a Table with a Subquery

### Understanding the Need for a Subquery

In SQL, a subquery is used when the value used to update a column depends on calculations or data from other tables.

### Step-by-Step Update Query

1. **Update Table Statement:** Specifies the table to be updated.
   ```sql
   UPDATE table_name
   ```

2. **Set Command:** Defines the column to be updated and the new value.
   ```sql
   SET column_name = new_value
   ```

3. **Where Command:** Filters the rows to be updated.
   ```sql
   WHERE condition
   ``````sql
   WHERE condition
   ```

### Using a Subquery in the Set Command

When the new value depends on values from other tables, a subquery is used within the Set command.

### Example: Updating Salaries with 10% Hike

**Objective:** Update the salaries of employees in the Department with the maximum salary, giving them a 10% hike.

```sql
UPDATE employee_table
SET salary = (
    SELECT MAX(salary)
    FROM employee_history_table
    WHERE employee_id = employee_table.employee_id
) * 1.10;
```

**Breakdown:**

* The subquery `(SELECT MAX(salary) ...)` finds the maximum salary for each employee.
* The result of the subquery is multiplied by 1.10 to apply the 10% hike.
* The Set command sets the salary column to this calculated value.

### Tips

* Ensure that the subquery returns a compatible value type to the column being updated.
* Use parentheses around the subquery for clarity and improved readability.
**Correlated Subqueries Tutorial**

**1. Introduction****Correlated Subqueries Tutorial**

**1. Introduction**

A correlated subquery is a subquery (nested query) that refers to columns from the outer query in its WHERE clause.

**2. Syntax**

```sql
SELECT ...
FROM ...
WHERE column_name (subquery)
```

**3. Example**

**Objective:** Increase the salaries of all employees by 10% based on the maximum salary in their department.

**Employee Table (E):**

| EmployeeID | DepartmentName | Salary |
|---|---|---|
| 1 | Sales | 5000 |
| 2 | Marketing | 4000 |
| 3 | IT | 6000 |

**Employee History Table (EH):**

| EmployeeID | DepartmentName | Salary |
|---|---|---|
| 1 | Sales | 5500 |
| 2 | Marketing | 4200 |
| 3 | IT | 6500 |

**SQL Query:**

```sql
UPDATE E
SET Salary = Salary + Salary * 0.1
WHERE DepartmentName IN
    (SELECT EH.DepartmentName
    FROM EH
    WHERE EH.DepartmentName = E.DepartmentName
    GROUP BY EH.DepartmentName
    HAVING MAX(EH.Salary));
```

**4. Explanation**HAVING MAX(EH.Salary));
```

**4. Explanation**

* The correlated subquery finds the maximum salary for each department in the Employee History table (EH).
* The outer query (E) then uses the correlated subquery to increase the salaries of all employees in those departments based on the maximum salary.

**5. Important Notes**

* The subquery must be enclosed in parentheses.
* The subquery can only refer to columns from the outer query that are specified in the ON or WHERE clause of the subquery.
* Correlated subqueries can be computationally expensive, especially for large tables.## Notes on Correlated Subqueries with Salary Increments

### Understanding the Concept

Correlated subqueries are used to retrieve data from a subquery that is dependent on the values of the outer query. In this case, we are using a correlated subquery to find the maximum salary for each department in the employee table. We then use this value to calculate a 10% salary increase for employees in a specific location.### Step-by-Step Explanation

1. **Identify the Outer Query:** The outer query is responsible for selecting employees and their salaries.

2. **Create the Correlated Subquery:** The correlated subquery is used to find the maximum salary for each department. It is defined using the `EXISTS` keyword and refers to the outer query to determine which department to search.

3. **Calculate the Salary Increase:** We use the `COALESCE` function to check if the maximum salary is not null, and if so, we calculate the 10% salary increase.

4. **Filter by Location:** We filter the results of the outer query to only include employees working in the 'Bank Road' location by comparing the department name of each employee with the location in the department table.

### Syntax

```sql
SELECT e.employee_id, e.salary,
COALESCE((
  SELECT MAX(salary)
  FROM employee_history eh
  WHERE eh.employee_id = e.employee_id
), 0) AS max_salary,
COALESCE((
  SELECT MAX(salary)
  FROM employee_history ehCOALESCE((
  SELECT MAX(salary)
  FROM employee_history eh
  WHERE eh.employee_id = e.employee_id
) * 0.1, 0) AS salary_increase
FROM employee e
WHERE e.department_id IN (
  SELECT department_id
  FROM department
  WHERE location = 'Bank Road'
);
```

### Example

**Employee Table**

| employee_id | salary | department_id |
|---|---|---|
| 1 | 50000 | 1 |
| 2 | 60000 | 2 |
| 3 | 70000 | 1 |
| 4 | 80000 | 3 |
| 5 | 90000 | 2 |

**Employee History Table**

| employee_id | salary | date |
|---|---|---|
| 1 | 55000 | 2022-01-01 |
| 1 | 60000 | 2022-07-01 |
| 2 | 65000 | 2022-01-01 |
| 2 | 70000 | 2022-07-01 |
| 3 | 75000 | 2022-01-01 |
| 3 | 80000 | 2022-07-01 |
| 4 | 85000 | 2022-01-01 |
| 4 | 90000 | 2022-07-01 |
| 5 | 95000 | 2022-01-01 |
| 5 | 100000 | 2022-07-01 |

**Department Table**

| department_id | department_name | location |
|---|---|---|
| 1 | Marketing | Head Office |
| 2 | Sales | Bank Road |
| 3 | Engineering | Tech Park |

**Output**

| employee_id | salary | max_salary | salary_increase || employee_id | salary | max_salary | salary_increase |
|---|---|---|---|
| 1 | 50000 | 60000 | 6000 |
| 2 | 60000 | 70000 | 7000 |
| 3 | 70000 | 80000 | 8000 |
| 4 | 80000 | 90000 | 9000 |
| 5 | 90000 | 100000 | 10000 |**Markdown Notes on Using Subqueries in UPDATE Statements**

**Introduction:**

Subqueries allow you to use a nested query within another query to retrieve data that is then used in the outer query. This can be used to filter rows or update data in the outer query.

**Syntax:**

```sql
UPDATE table_name
SET column_name = (subquery)
WHERE condition;
```

**Steps:**

1. **Identify the Primary Query:** Determine the table and columns you want to update.

2. **Define the Subquery:** Write a separate query that returns the data you want to use as the update value or filter condition.

3. **Include the Subquery:** Enclose the subquery within parentheses `()` and either use it in the `SET` or `WHERE` clause.

**Example:****Example:**

**Objective:** Update the salaries of employees in Bangalore who have a recent employee history record.

**Steps:**

1. **Primary Query:**
   - Update `employees` table
   - Set column: `salary`

2. **Subquery to Retrieve Employees in Bangalore:**
   - Select `employee_id` from `employee_history` table
   - Filter: Where `location` equals 'Bangalore'

3. **Subquery to Filter Employees with Recent History:**
   - Select `employee_id` from `employee_history` table
   - Filter: Where `employee_id` exists in the first subquery

4. **Final Query:**
   ```sql
   UPDATE employees
   SET salary = (
       SELECT salary
       FROM employee_history
       WHERE location = 'Bangalore' AND employee_id IN (
           SELECT employee_id
           FROM employee_history
           WHERE employee_id = employee_id
       )
   )
   WHERE employee_id IN (
       SELECT employee_id
       FROM employee_history
       WHERE location = 'Bangalore'
   );
   ```

**Explanation:**);
   ```

**Explanation:**

* The main query (update `employees`) updates the `salary` column.
* The subquery in the `SET` clause calculates the new salary based on the `employee_id` and `location` conditions.
* The subquery in the `WHERE` clause filters the employees who are in the `employee_history` table and satisfy the Bangalore location condition.**Understanding the WHERE Clause in UPDATE and DELETE Statements**

**WHERE Clause in UPDATE Statements**

* The WHERE clause in an UPDATE statement is optional.
* It allows you to specify which rows to update based on specific conditions.
* You can use the WHERE clause to:
    * Update only specific columns in the table.
    * Update rows based on a specific value or range of values.
    * Update rows based on a comparison with another column or subquery.

**Subqueries in WHERE Clauses**

* Subqueries are queries that are embedded within other queries.
* In an UPDATE statement, you can use a subquery in the WHERE clause to:* Update rows that meet a specific condition in the subquery.
    * Perform complex filtering or calculations using the subquery.

**Syntax:**

```
UPDATE table_name
SET column_name = new_value
WHERE condition (using subquery);
```

**Example:**

```
UPDATE employees
SET salary = salary * 1.10
WHERE employee_id IN (
    SELECT employee_id
    FROM sales
    WHERE sales_amount > 100000
);
```

**WHERE Clause in DELETE Statements**

* The WHERE clause in a DELETE statement is used to specify which rows to delete.
* It operates similarly to the WHERE clause in an UPDATE statement.
* You can use the WHERE clause to delete rows based on:
    * A specific value or range of values.
    * A comparison with another column or a subquery.

**Syntax:**

```
DELETE FROM table_name
WHERE condition (using subquery);
```

**Example:**

```
DELETE FROM customers
WHERE customer_id IN (
    SELECT customer_id
    FROM orders
    WHERE order_status = 'Cancelled'
);
```FROM orders
    WHERE order_status = 'Cancelled'
);
```

**Types of Subqueries in DELETE and UPDATE Statements**

* **Correlated Subqueries:** Dependent on the outer query for one or more values.
* **Multi-Row Subqueries:** Return multiple rows, and typically used to update or delete multiple rows.
* **Single-Column Multi-Row Subqueries:** Return multiple rows, but only a single column is used for the comparison.**Markdown Notes: Correlated Subquery for Deleting Departments Without Employees**

**Concept:**

A correlated subquery is a subquery that refers to columns in its outer query. It can be used to filter data in the outer query based on specific criteria.

**Step-by-Step Explanation:**

1. **Identify the goal:** To delete departments that do not have any employees.

2. **Craft the subquery:**
```sql
SELECT department_name
FROM department
WHERE department_id NOT IN (SELECT department_id FROM employee);
``````
- This subquery finds the department names that are not associated with any employee records in the `employee` table.

3. **Incorporate the subquery:**
```sql
DELETE FROM department
WHERE department_name IN (SELECT department_name FROM department
                             WHERE department_id NOT IN (SELECT department_id FROM employee));
```
- This query uses the subquery to filter the `department` table and delete departments without any employees.

**Example:**

Assuming the following tables:

```sql
department:
+-------------+-------------+
| department_id | department_name |
+-------------+-------------+
| 1             | Sales          |
| 2             | Marketing       |
| 3             | Finance        |
| 4             | HR             |
+-------------+-------------+

employee:
+-------------+-------------+----------+
| employee_id | employee_name | department_id |
+-------------+-------------+----------+
| 1             | John Smith     | 1         || 1             | John Smith     | 1         |
| 2             | Jane Doe       | 3         |
| 3             | Bob Green      | 4         |
+-------------+-------------+----------+
```

When executing the `DELETE` query:

```sql
DELETE FROM department
WHERE department_name IN (SELECT department_name FROM department
                             WHERE department_id NOT IN (SELECT department_id FROM employee));
```

It will delete the `Marketing` department because it does not have any associated employees.**Correlated Subquery in SQL DELETE Statements**

**Key Concept:**

* A correlated subquery is a subquery that references columns from the outer query in its WHERE clause.

**Purpose:**

* To filter data in the outer query based on the results of the subquery.

**Syntax:**

```sql
DELETE FROM <outer_table>
WHERE <outer_table_column> IN (
    SELECT <subquery_column>
    FROM <subquery_table>
    WHERE <subquery_condition>
)
```

**Explanation:**WHERE <subquery_condition>
)
```

**Explanation:**

* The outer table is the table from which you want to delete records.
* The outer_table_column is the column in the outer table that you are filtering.
* The subquery is a separate query that returns a set of values that will be used to filter the outer query.
* The subquery_column is the column in the subquery that you are comparing to the outer_table_column.
* The subquery_condition is the condition that determines which rows to return from the subquery.

**Real-World Example:**

Consider a database with a "Departments" table and an "Employees" table. The "Departments" table has a column called "DeptID" and the "Employees" table has a column called "DeptID".

You want to delete all the records from the "Departments" table that do not have any employees. To do this, you would use the following SQL statement:

```sql
DELETE FROM Departments
WHERE DeptID NOT IN (
    SELECT DeptID
    FROM Employees
)
```

**Explanation:**SELECT DeptID
    FROM Employees
)
```

**Explanation:**

* The outer table is the "Departments" table.
* The outer_table_column is the "DeptID" column.
* The subquery is the query that selects all the "DeptID" values from the "Employees" table.
* The subquery_column is the "DeptID" column in the subquery.
* The subquery_condition is empty, which means that all rows will be returned from the subquery.

This query will delete all the records from the "Departments" table that do not have a corresponding record in the "Employees" table.## Subqueries in SQL

**Concept:**

A subquery, also known as a nested query, is a query within another query. It allows you to retrieve data from one table based on the results of another query.

**Usage:**

Subqueries are used in SQL to:

* Filter data based on multiple criteria
* Combine data from multiple tables
* Perform aggregate functions on subsets of data

**Syntax:**

```sql
SELECT *
FROM outer_table
WHERE condition = (SELECT ... FROM inner_table);
```

**Example:**```

**Example:**

Find all employees in the 'Sales' department who have a salary greater than the average salary for the department:

```sql
SELECT *
FROM employees
WHERE department = 'Sales'
AND salary > (SELECT AVG(salary) FROM employees WHERE department = 'Sales');
```

### Types of Subqueries

**Correlated Subqueries:**

* Reference columns from the outer query in the subquery.

**Non-Correlated Subqueries:**

* Do not reference columns from the outer query in the subquery.

### Step-by-Step Explanation

1. **Define the outer query:** This is the main query that will use the subquery.
2. **Create the subquery:** Write a separate query within parentheses that returns the data you need.
3. **Connect the queries:** Use a comparison operator (e.g., `=`, `>`, `<`) to compare the result of the subquery to a column or condition in the outer query.
4. **Execute the query:** The database will execute the subquery first and then use the result to filter the data in the outer query.

### Benefits of Subqueries### Benefits of Subqueries

* **Data filtering:** Subqueries allow you to access and filter data across multiple tables.
* **Data aggregation:** You can perform aggregate functions (e.g., SUM, AVG) on data returned by the subquery.
* **Complex data manipulation:** Subqueries provide a way to perform complex data manipulation tasks that would be difficult or impossible with a single query.