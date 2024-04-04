## SQL Database Project for Data Analysts

### Introduction

This guide will provide step-by-step instructions on how to design and build an SQL database, write custom SQL queries, and connect the database to a BI tool to create interactive dashboards.

### Database Design

**Step 1: Identify Data Requirements**

Gather information on the types of data that need to be stored, such as customer orders, stock levels, and staff details.

**Step 2: Normalize the Data**

Normalize data by breaking it down into smaller, more specific tables to avoid duplication and data inconsistencies.

**Step 3: Define Table Relationships**

Establish relationships between tables using foreign keys to ensure data integrity and maintain referential integrity.

### SQL Queries

**Step 1: Introduction to SQL**

Understand the basics of SQL, including data types, operators, and functions.

**Step 2: Write SELECT Queries**

Retrieve specific data from the database using the SELECT statement.

**Step 3: Filtering and Sorting Data**

Apply filters (WHERE clause) and sorting (ORDER BY clause) to refine the query results.

**Step 4: Joining Tables**

Combine data from multiple tables using JOIN statements to access related information.

**Step 5: Aggregate Functions**

Use aggregate functions (SUM(), COUNT(), AVG()) to summarize data and generate meaningful insights.

### Connecting to BI Tools

**Step 1: Choose a BI Tool**

Select a BI tool such as Tableau or Power BI that supports your data analysis needs.

**Step 2: Establish Data Connection**

Create a connection between the SQL database and the BI tool using the appropriate drivers and authentication mechanisms.

**Step 3: Build Interactive Dashboards**

Visualize and analyze data using charts, graphs, and interactive filters to create informative and visually appealing dashboards.

### Conclusion### Conclusion

By completing this project, you will gain hands-on experience in database design, SQL querying, and BI tool utilization, demonstrating your proficiency in data analytics skills.## Designing a Database

**Concept of a Primary Key**

* Every table should have a primary key, a unique identifier for each row.
* The row ID column is commonly used as a primary key.

**Database Design Using QuickDBD**

**Step 1: Define Tables and Fields**

* Specify table names and fields on the left panel.
* Indicate data types and primary keys (e.g., **pk**).

```
orders_table:
- row_id (pk)
- ... (other fields)
```

**Step 2: Normalize Data to Reduce Redundancy**

* Identify repeated data in rows.
* Create separate tables for reusable data (e.g., customers, delivery addresses, products).

**Step 3: Create Customer Table**

* **Table Name:** customers
* **Fields:**
    * cust_id (pk)
    * first_name
    * last_name

**Step 4: Replace Customer Fields with Identifier**

* In the orders table, replace customer_first_name and customer_last_name with cust_id.

```
orders_table:
- row_id (pk)
- cust_id (references customers.cust_id)
- ...
```

**Step 5: Specify Relationship**

* Drag from cust_id in the customers table to cust_id in the orders table.
* This establishes a foreign key constraint, ensuring data integrity.

**Step 6: Create Delivery Address Table**

* **Table Name:** address
* **Fields:**
    * address_id (pk)
    * ... (other address fields)

**Step 7: Add Address Field to Orders Table**

* Replace address fields in the orders table with address_id.
* Add a NOT NULL constraint to the delivery_address2 field (if needed).

**Step 8: Specify Relationship between Address and Orders Tables**

* Drag from address_id in the address table to address_id in the orders table.

**Step 9: Create Product Table**

* **Table Name:** item
* **Fields:**
    * item_id (pk)
    * skew
    * item_name
    * item_category
    * item_size
    * item_price

**Step 10: Specify Relationship between Item and Orders Tables*** Drag from item_id in the item table to item_id in the orders table.**Database Design for Pizza Ordering System**

**Stock Control Data**

* **Ingredient Table:**
    * Contains information about each ingredient, including:
        * Ingredient ID
        * Ingredient name
        * Weight sold in
* **Recipe Table:**
    * Contains the ingredients used in each pizza size and quantity:
        * Recipe ID
        * Pizza size
        * Ingredient ID
        * Quantity
* **Inventory Table:**
    * Tracks stock levels of each ingredient:
        * Inventory ID
        * Ingredient ID
        * Quantity on hand

**Staff Data**

* **Staff Table:**
    * Information about staff members:
        * Staff ID
        * First name
        * Last name
        * Position
        * Hourly rate
* **Shift Table:**
    * Defines work shifts:
        * Shift ID
        * Day of week
        * Start time
        * Finish time
* **Roster Table:**
    * Indicates which staff members are working on each shift:
        * Row ID
        * Shift ID
        * Date
        * Staff ID

**Relationships Between Tables**

* Recipe ID in the Recipe table matches Item ID in the Ingredient table.
* Ingredient ID in both the Ingredient and Recipe tables.
* Shift ID in the Shift table matches Shift ID in the Roster table.
* Staff ID in the Staff table matches Staff ID in the Roster table.
* Date in the Roster table matches Created Date in the Orders table.

**How to Create the Database**

1. **Design the Database Structure:** Use QuickDBD or a similar tool to create a database schema.
2. **Export SQL Code:** Generate SQL code for creating the tables.
3. **Install MySQL Server:** Refer to online tutorials or YouTube videos for instructions.
4. **Create New Database:** Use a database management tool (e.g., Navicat) to create a new database and import the SQL code.

**Example SQL Code**

To create the Ingredient table in MySQL:

```sql
CREATE TABLE Ingredient (
  IngredientID INT PRIMARY KEY,
  IngredientName VARCHAR(255),
  WeightUnit VARCHAR(50)IngredientName VARCHAR(255),
  WeightUnit VARCHAR(50)
);
```

## How to Create Database Tables and Import Data

**Creating Tables:**

- Right-click in the database and select "Execute SQL file."
- Choose the MySQL file and run it.
- The tables will be created in the database.

**Importing Data:**

- Download the data in a CSV file.
- Use the Navicat import wizard:
  - Select CSV.
  - Add the file.
  - Specify the target table.
  - Check the fields.
  - Use "append" or "copy" method.
  - Click "start."

**Benefits:**

- Once the tables are set up, SQL queries can be written to create views.
- Views allow dashboards to be built.

## SQL Queries for Data Analysis

**Requirements:**

- Orders, menu items, customers, delivery addresses tables.

**Queries:**

1. **Total orders:** `SELECT COUNT(order_id) FROM orders;`
2. **Total sales:** `SELECT SUM(i.item_price) FROM orders o JOIN item i ON o.item_id = i.item_id;`
3. **Total items sold:** `SELECT SUM(o.quantity) FROM orders o;`
4. **Average order value:** `/` (Total sales / Total orders)
5. **Sales by category:** `SELECT i.item_cat, SUM(i.item_price) FROM orders o JOIN item i ON o.item_id = i.item_id GROUP BY i.item_cat;`
6. **Top selling items:** `SELECT i.item_name, SUM(o.quantity) FROM orders o JOIN item i ON o.item_id = i.item_id GROUP BY i.item_name ORDER BY SUM(o.quantity) DESC;`
7. **Orders by hour:** `SELECT DATE_FORMAT(o.created_at, '%H:00') AS hour, COUNT(o.order_id) FROM orders o GROUP BY hour;`
8. **Sales by hour:** `SELECT DATE_FORMAT(o.created_at, '%H:00') AS hour, SUM(i.item_price) FROM orders o JOIN item i ON o.item_id = i.item_id GROUP BY hour;`
9. **Orders by address in a map:** `SELECT a.delivery_address_one, a.delivery_address_two, a.delivery_city, a.delivery_zip_code, COUNT(o.order_id) FROM orders o JOIN address a ON o.address_id = a.address_id GROUP BY a.delivery_address_one, a.delivery_address_two, a.delivery_city, a.delivery_zip_code;`10. **Orders by delivery method:** `SELECT o.delivery_method, COUNT(o.order_id) FROM orders o GROUP BY o.delivery_method;`

**Joining Tables:**

- Use `JOIN` to connect related tables.
- Specify the joining condition using `ON`.
- Create table aliases for simplicity (`e.g., o.item_id`).
- Use different join types as needed (e.g., `LEFT JOIN`).**Notes on Data Modeling and Views**

**Introduction**

* Data modeling is the process of organizing data in a way that makes it easy to use and understand.
* Views are virtual tables that present a subset of data from one or more tables.

**Benefits of Using Views**

* Improves performance by limiting the amount of data that needs to be processed.
* Enhances security by restricting access to sensitive data.
* Provides a consistent interface to data, simplifying data retrieval.

**When to Use Views**

* When you need to present a specific subset of data.
* When you want to improve data security.
* When you need to enhance data performance.

**Creating Views**

* **Syntax:** `CREATE VIEW view_name AS SELECT * FROM table_name WHERE condition;`

**Subqueries**

* Used to nest queries within other queries.
* Allows you to perform complex calculations or retrieve data from multiple tables in a single query.

**Example: Calculating Total Quantity by Ingredient**

**Step 1: Create a view to get order quantity per pizza.**

```sql
CREATE VIEW order_quantity_per_pizza AS
SELECT
  O.item_id,
  I.skew,
  I.item_name,
  SUM(O.quantity) AS order_quantity
FROM
  orders AS O
JOIN
  item AS I ON O.item_id = I.item_id
GROUP BY
  O.item_id, I.skew, I.item_name;
```

**Step 2: Create a view to get ingredient quantity and cost.**

```sql
CREATE VIEW ingredient_quantity_and_cost AS
SELECT
  OQP.item_id,
  OQP.skew,
  OQP.item_name,
  OQP.order_quantity,
  R.ing_id,
  R.quantity AS recipe_quantity,
  I.ing_name,
  I.ing_weight,
  I.ing_price
FROM
  order_quantity_per_pizza AS OQP
JOIN
  recipe AS R ON OQP.skew = R.recipe_id
JOIN
  ingredient AS I ON R.ing_id = I.ing_id;
```JOIN
  ingredient AS I ON R.ing_id = I.ing_id;
```

**Step 3: Use subqueries to calculate total ingredient quantity and cost.**

```sql
SELECT
  iqac.ing_id,
  iqac.ing_name,
  SUM(iqac.order_quantity * iqac.recipe_quantity) AS total_quantity,
  SUM(iqac.ing_weight * iqac.order_quantity * iqac.recipe_quantity * iqac.ing_price) AS total_cost
FROM
  ingredient_quantity_and_cost AS iqac
GROUP BY
  iqac.ing_id, iqac.ing_name;
```

**Custom SQL Queries for Data Analysis**

**Objectives:**

* Understand the basics of writing custom SQL queries
* Learn how to perform calculations and manipulate data
* Create views to simplify complex operations

**Step 1: Querying Data**

* **SELECT:** Use the SELECT statement to select specific columns from a table.
* **FROM:** Specify the table(s) from which to retrieve data.
* **WHERE:** Filter the results based on specific criteria.

**Step 2: Calculations**

* **Arithmetic Operators:** Use operators like `+`, `-`, `*`, and `/` to perform calculations on numeric data.
* **Aliases:** Assign temporary names to calculations for clarity.

**Step 3: Combining Data**

* **JOIN:** Combine rows from multiple tables based on common columns.
* **LEFT JOIN:** Include all rows from the left table, even if there are no matching rows in the right table.

**Example:**

```sql
SELECT
  s1.itemname,
  s1.ingid,
  s1.ingname,
  s1.ingweight,
  s1.ingprice,
  s1.orderquantity * s1.recipequantity AS ordered_weight,
  s1.ingprice / s1.ingweight AS unit_cost,
  (s1.ingprice / s1.ingweight) * (s1.orderquantity * s1.recipequantity) AS ingredient_cost
FROM ingredients AS s1;
```

**Explanation:**

* This query calculates the ordered weight, unit cost, and ingredient cost for each ingredient.
* The `ordered_weight` column is calculated by multiplying the order quantity by the recipe quantity.
* The `unit_cost` column is calculated by dividing the ingredient price by the ingredient weight.
* The `ingredient_cost` column is calculated by multiplying the unit cost by the ordered weight.

**Step 4: Views****Step 4: Views**

* **CREATE VIEW:** Define a view to store a custom query for future reference.
* **Benefits:** Views simplify complex operations, improve readability, and enhance performance.

**Example:**

```sql
CREATE VIEW stock_one AS
SELECT
  ing_name,
  SUM(ordered_weight) AS total_ordered_weight
FROM ingredients
GROUP BY
  ing_name;
```

**Explanation:**

* This view calculates the total ordered weight for each ingredient.
* It can be used in subsequent queries to simplify operations related to stock management.**Structured Query Language (SQL): A Comprehensive Guide for Beginners**

**1. Introduction to SQL**

* SQL (Structured Query Language) is a powerful database programming language used to create, manage, and query data in relational database management systems (RDBMS).
* An RDBMS stores data in tables with rows and columns.

**2. Basic SQL Syntax**

* **SELECT:** Retrieves specific columns from a table.
* **FROM:** Specifies the table to query.
* **WHERE:** Filters the results based on a condition.
* **ORDER BY:** Sorts the results by a specific column.
* **LIMIT:** Restricts the number of results returned.

**3. Data Retrieval**

* Use `SELECT *` to retrieve all columns from a table.
* To select specific columns, use `SELECT column1, column2, ...`.
* Filter results using `WHERE` clauses, e.g.:
```sql
SELECT * FROM staff WHERE first_name = 'John';
```

**4. Data Manipulation**

* **INSERT:** Adds new data into a table.
* **UPDATE:** Modifies existing data.
* **DELETE:** Removes data from a table.
* Example: To insert new staff data:
```sql
INSERT INTO staff (first_name, last_name, hourly_rate) VALUES ('Jane', 'Doe', 25);
```

**5. Joins**

* Combines data from multiple tables by matching common columns.
* Use `JOIN` to join tables using the `ON` clause, e.g.:
```sql
SELECT * FROM staff AS S JOIN rotor AS R ON S.staff_id = R.staff_id;
```

**6. Data Aggregation**

* **COUNT:** Counts the number of rows.
* **SUM:** Sums the values in a column.
* **AVG:** Calculates the average value.* **AVG:** Calculates the average value.
* Example: To calculate the total hourly rate for staff:
```sql
SELECT SUM(hourly_rate) FROM staff;
```

**7. Data Manipulation Functions**

* Manipulate and transform data within SQL queries.
* Common functions include:
    * `DATE()`: Returns the current date.
    * `TIME()`: Returns the current time.
    * `STRFTIME()`: Formats dates and times.

**8. Advanced Concepts**

* **Subqueries:** Queries within queries.
* **Views:** Virtual tables based on complex queries.
* **Transactions:** Groups multiple SQL statements to ensure data consistency.

**Example SQL Query:**

```sql
SELECT S.first_name, S.last_name, R.shift_id, SH.start_time, SH.end_time,
S.hourly_rate,
(JULIANDAY(SH.end_time) - JULIANDAY(SH.start_time)) * 24 * 60 +
(TIME(SH.end_time) - TIME(SH.start_time)) / 60 AS total_hours
FROM staff AS S
JOIN rotor AS R ON S.staff_id = R.staff_id
JOIN shift AS SH ON R.shift_id = SH.shift_id;
```

This query combines data from staff, rotor, and shift tables to calculate the total hours worked by each staff member.**Data Studio: Custom Query and Data Source Configuration**

**Custom Query**

* Allows you to define specific data retrieval criteria for your report.

**Data Source Schema**

* Represents the structure of your data source, including fields and their data types.

**Data Type Mapping**

* Ensure that each field in your data source is assigned the appropriate data type:
    * **Date and time:** Fields that represent dates and times
    * **Boolean:** Fields with true/false values
    * **Text:** Fields that contain non-numeric data
    * **Geo address/Geo postcode:** Fields that represent geographical locations
    * **Currency USD:** Fields that contain monetary values in US dollars
    * **Number:** Fields that contain numeric data

**Creating a Custom Data Source**

1. Copy the custom query from the provided source.
2. Paste the query into the Data Studio interface.
3. Connect to your data source.
4. Review and correct data type assignments for all fields.4. Review and correct data type assignments for all fields.
5. Give the data source a name.
6. Create a report using the new data source.

**Phase 1: Query Building**

* Focused solely on creating the 10 visualizations specified in the brief.
* Design considerations will be addressed in a later phase.

**Distinctive Count**

* A distinct count returns the number of unique values in a column.
* Used to calculate the total number of orders.

**Calculated Field**

* Allows you to create new fields based on calculations using existing fields.
* Used to calculate total sales by multiplying item price by quantity.

**Next Steps**

* Continue building the remaining visualizations as per the brief.
* Once all visualizations are created, proceed to Phase 2: Design.**Dashboard Design: A Step-by-Step Guide**

**Phase 1: Queries**

* **Average Order Value:**
    * Formula: Sum(Total Sales) / Count Distinct(Order ID)
    * Aggregator: Sum for total sales; Count Distinct for order ID
* **Sales by Category:**
    * Metric: Total Sales
    * Dimension: Item Category
* **Top Selling Items:**
    * Metric: Total Sales
    * Dimension: Item Name
* **Orders/Sales by Hour:**
    * Metric 1: Total Orders
    * Dimension 1: Hour
    * Metric 2: Total Sales
    * Dimension 2: Hour

**Phase 2: Design**

**Chart Types:**

* **Donut Chart:** Used when there are few values (e.g., Sales by Category)
* **Bar Chart:** Shows values vertically, evoking hierarchy (e.g., Top Selling Items)
* **Line Chart:** Used for time-series data (e.g., Orders/Sales by Hour)
* **Map:** Displays data on a geographical location (e.g., Orders by Address)

**Design Considerations:**

* **Data Integrity:** Ensure data is accurate and reliable.
* **Ink-to-Data Ratio:** Optimize the use of space to display data effectively.
* **Sorting:** Organize data in a sensible order (e.g., hour descending for time-series charts).* **Y-Axis Scaling:** Adjust the Y-axis to accommodate different scales of metrics (e.g., creating a right Y-axis for Total Orders in the Orders/Sales by Hour chart).
* **Metric/Dimension Pairing:** Select appropriate metrics and dimensions for each chart type.
**Topic: Working with Address Data in Data Studio**

**Introduction**
Data Studio allows you to create visualizations and dashboards using data from various sources. When working with address data, it's essential to understand how to manipulate it for accurate and meaningful visualizations.

**Concatenating Address Fields**

**Step 1: Create a new field**
Sometimes, Data Studio requires a single field to plot locations on a map, but you may have multiple address fields. To solve this, create a new field that combines the necessary address fields.

**Step 2: Use the CONCAT function**
Use the CONCAT function to concatenate the address fields. The syntax is:
```
CONCAT(field1, ", ", field2, ", ", field3, ...)
```

**Step 3: Add additional information**
If necessary, add additional information like country or state to the concatenated field to ensure accurate plotting.

**Example:**
To create a "Full Address" field that concatenates delivery address, city, zip code, and country:
```
CONCAT(Delivery Address 1, ", ", Delivery City, ", ", Delivery Zip Code, ", ", "United States")
```

**Applying the New Field**

**Step 1: Replace the current dimension**
Once the new field is created, replace the current dimension used for plotting locations with the new "Full Address" field.

**Step 2: Zoom in for accuracy**
Zoom in on the map to ensure that all bubbles are plotted correctly. Investigate any outliers or discrepancies in the data.

**Adding Metrics to Map**

**Step 1: Add total sales to size metric**
To represent the total sales associated with each location, add the total sales metric to the size metric of the bubble map. This will provide a visual representation of the sales volume at different locations.

**Creating Pie Chart with Delivery and Pickup Data****Creating Pie Chart with Delivery and Pickup Data**

**Step 1: Add delivery dimension to pie chart**
To create a pie chart showing the breakdown of orders by delivery and pickup, add the delivery dimension to a pie chart.

**Step 2: Create distinct key**
Use the distinct key function to create a metric that counts the number of unique orders, eliminating duplicates.

**Step 3: Add distinct count of order ID**
Add the distinct count of order ID as the metric to the pie chart.

**Conclusion**

By following these steps, you can effectively manipulate address data in Data Studio for accurate and meaningful visualizations. This allows you to gain insights into your data's geographical distribution and sales performance.**Creating a Custom Filter on a Data Table**

**Step 1: Name the Filter**

* Click on the "Filters" icon in the top right corner of the data table.
* Enter a name for your filter, such as "Pizza Only".

**Step 2: Specify Filter Criteria**

* Under "Filter Type", select "Item Name".
* Under "Filter Options", select "Contains".
* Enter the value you want to filter for, such as "pizza".

**Step 3: Apply Filter**

* Click "Apply" to apply the filter.

**Additional Considerations:**

* **Data Type:** You can change the data type of the filtered column, such as to currency (USD).
* **Sorting:** You can sort the data by any column, such as "Cost" to list the most expensive pizzas.
* **Highlighting:** You can use conditional formatting to highlight specific rows or cells based on the filter criteria.

**Example Code:**

```
// Create a filter
var filter = dataStudio.createFilter();
filter.setName('Pizza Only');
filter.setDimensionName('Item Name');
filter.setType('TEXT_CONTAINS');
filter.setValue('pizza');

// Apply the filter
dataStudio.applyFilter('tableID', filter);
```

**How to Combine Multiple Data Tables**

**Step 1: Select Tables**

* Select the two data tables you want to combine.

**Step 2: Right-Click and Blend**

* Right-click on the tables and select "Blend Data".* Right-click on the tables and select "Blend Data".

**Step 3: Delete Original Tables**

* Once the tables are blended, delete the original tables to create a single, combined table.

**Example Code:**

```
// Blend two tables
var blendedTable = dataStudio.blendTables([table1, table2], ['Ingredient Name']);

// Delete original tables
dataStudio.deleteTables([table1, table2]);
```

## Creating a Dashboard in Google Data Studio
### Step 1: Set Up Data Source

- Select "Data" -> "Create New Data Source".
- Choose "Google Sheets" and connect to your data.

### Step 2: Create Metrics and Dimensions

- Drag and drop the desired fields from the data source to the "Metrics" and "Dimensions" panels.
```
Example:
- Metric: "Total Sales"
- Dimension: "Product Category"
```

### Step 3: Add Visualizations

- Select a visualization type from the "Chart" menu.
```
Example:
- Visualization: "Bar Chart"
```

### Step 4: Configure Visualization

- Drag and drop metrics and dimensions to the chart area.
- Configure chart settings (e.g., color, labels).
```
Example:
- X-axis: "Product Category"
- Y-axis: "Total Sales"
```

### Step 5: Create Filters and Segments

- Use filters to narrow down the data displayed.
- Create segments to group data by specific criteria.
```
Example:
- Filter: "Date Range" -> "Last 30 Days"
- Segment: "Region" -> "North America"
```

### Step 6: Add Interactivity

- Enable "Exploration Controls" to allow users to interact with the dashboard.
- Add "Date Range Control" to allow users to select a specific date range.

### Step 7: Design and Layout

- Customize the dashboard appearance by modifying colors, fonts, and layout.
- Add a title and other text elements for clarity.
```
Example:
- Title: "Sales Dashboard"
- Subtitle: "Overview of sales performance"
```

### Step 8: Publish and Share

- Publish the dashboard to make it available to others.
- Share the dashboard link with authorized users.**Dashboard Design Tips**

**1. Cell Formatting****1. Cell Formatting**

* **Cell Border Color:** Choose a light gray color to enhance cell visibility without overwhelming the data.

**2. Text Elements**

* **Titles:** Use titles sparingly and only when necessary to clarify visualization content.
* **Axis Titles:** Add x-axis and y-axis titles to provide context for the data.
* **Text Boxes:** Add small text boxes to provide additional information, such as metric descriptions.

**3. Assessing Visualizations**

* **Legends:** Ensure legends provide clear information about each data series.
* **Context:** Use chart or axis titles to provide context for the data being displayed.

**4. Visual Emphasis**

* **Line Charts:** Axis titles can suffice instead of chart titles if the data is easily interpretable from the legend.
* **Bar Charts:** Legends provide metric information, while axis titles indicate categories or time periods.
* **Donut Charts:** Text boxes can be used to specify the metric being displayed.

**Additional Tips**

* Review dashboards to ensure all necessary titles and text are present for clarity.
* Avoid adding excessive text or titles that unnecessarily clutter the visualization.
* Choose concise and informative text that enhances understanding without overwhelming the viewer.