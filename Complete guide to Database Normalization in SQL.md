**Normalization in SQL**

**Introduction**

* Normalization is the process of organizing data in a database in a way that reduces redundancy and ensures data integrity.
* It involves breaking down data into smaller, more manageable tables that are linked together through foreign keys.

**Levels of Normalization**

* **First Normal Form (1NF)**:
    * Each row in a table is unique and can be identified by a primary key.
    * No two rows have the same combination of values for the primary key.
    * Example: Table with columns ID, Name, and Age

* **Second Normal Form (2NF)**:
    * All attributes are fully dependent on the primary key.
    * No attributes are dependent on non-key attributes.
    * Example: Add a column Address, which is dependent only on ID (not Name).

* **Third Normal Form (3NF)**:
    * No attributes are transitively dependent on the primary key.
    * Each non-key attribute depends directly on the primary key.* Example: Remove any attributes that depend on Address (such as Phone Number).

**Example of Normalization**

**Denormalized Table:**

| OrderID | ProductID | ProductName | Quantity | UnitPrice |
|---|---|---|---|---|
| 1 | 100 | Apple | 10 | 1.00 |
| 2 | 101 | Orange | 15 | 0.75 |
| 3 | 102 | Banana | 20 | 0.50 |

**Normalized Tables:**

**Orders Table:**

| OrderID | CustomerID | OrderDate |
|---|---|---|
| 1 | 10 | 2023-02-10 |
| 2 | 11 | 2023-02-15 |
| 3 | 12 | 2023-02-20 |

**Products Table:**

| ProductID | ProductName | UnitPrice |
|---|---|---|
| 100 | Apple | 1.00 |
| 101 | Orange | 0.75 |
| 102 | Banana | 0.50 |

**OrderItems Table:**

| OrderID | ProductID | Quantity |
|---|---|---|
| 1 | 100 | 10 |
| 1 | 101 | 5 |
| 2 | 101 | 10 |
| 3 | 102 | 20 |

**Anomalies in Denormalized Data**

* **Insertion Anomaly:** Unable to add new rows when some information is missing.
* **Deletion Anomaly:** Deleting a row removes related information from other tables.* **Updation Anomaly:** Updating a value in multiple tables creates inconsistencies.

**Benefits of Normalization**

* Reduces redundancy, saving storage space.
* Improves data integrity by eliminating anomalies.
* Makes data easier to query and understand.
* Facilitates data modification by allowing updates or deletions in only one table.**Markdown Notes on Data Redundancy in Database Design**

**Key Concepts**

* Data Redundancy: Duplication of data within a database.
* Primary Key: A unique identifier for each record in a table.
* Anomalies: Errors or inconsistencies that arise due to data redundancy.

**Types of Data Redundancy**

* **Record-level Redundancy:** Exact duplicate records exist in the database.
* **Column-level Redundancy:** Column values repeat across multiple records, even if the records have unique primary keys.

**Example of Column-Level Redundancy**

Consider a table with the following columns:

```
| Customer ID | Customer Name | Address | Phone Number |
|---|---|---|---||---|---|---|---|
| 1 | John Doe | 123 Main St. | 555-123-4567 |
| 2 | Jane Doe | 456 Oak St. | 555-234-5678 |
| 3 | Mary Smith | 789 Elm St. | 555-345-6789 |
| 4 | John Smith | 123 Main St. | 555-456-7890 |
```

Notice that the address "123 Main St." appears in both records 1 and 4. This is an example of column-level redundancy because the address column is repeating the same value for different customers.

**Consequences of Data Redundancy**

* Wasted storage space
* Increased risk of anomalies (discussed later)
* Difficulty in maintaining data consistency

**Avoidance of Data Redundancy**

* **Normalization:** A process of organizing data in a database to eliminate redundancy while preserving data integrity.
* **Referential Integrity:** Constraints that ensure relationships between data in different tables, avoiding duplication.

**Examples of Normalization**

Consider the following table:

```
| Product ID | Product Name | Category | Supplier ID |
|---|---|---|---|
| 1 | Pen | Office Supplies | 2 ||---|---|---|---|
| 1 | Pen | Office Supplies | 2 |
| 2 | Paper | Office Supplies | 1 |
| 3 | Stapler | Office Supplies | 2 |
| 4 | Coffee | Beverages | 3 |
| 5 | Tea | Beverages | 3 |
```

This table is not normalized because the category information is duplicated for each product. We can normalize the table by creating a separate category table and using foreign keys to link categories to products:

```
| Category ID | Category Name |
|---|---|
| 1 | Office Supplies |
| 2 | Beverages |

| Product ID | Product Name | Category ID | Supplier ID |
|---|---|---|---|
| 1 | Pen | 1 | 2 |
| 2 | Paper | 1 | 1 |
| 3 | Stapler | 1 | 2 |
| 4 | Coffee | 2 | 3 |
| 5 | Tea | 2 | 3 |
```

Normalization eliminates the duplication of category information, resulting in a more efficient and accurate data structure.## Understanding Database Normalization and Table Design

### Database Normalization

- **Definition:** Process of organizing data to minimize redundancy and maintain data integrity.
- **Benefits:**- **Benefits:**
    - Reduces storage space requirements
    - Improves data consistency and accuracy
    - Simplifies data management and querying

### Database Design

- **Objective:** Create a logical and efficient structure to store and retrieve data.
- **Steps:**
    1. Identify the entities (objects) involved in the data.
    2. Determine the attributes (properties) of each entity.
    3. Establish relationships between different entities.

### Importance of Tables

- **Tables:** Primary data structures used in databases to store data.
- **Purpose:** Organize data into rows (records) and columns (attributes).
- **Structure:**
    - Each row represents a single record of data.
    - Column headings define the attributes associated with each record.

### Avoiding Data Redundancy

- **Data Redundancy:** Repetition of identical data in multiple tables.
- **Example:** Storing customer addresses in multiple tables, such as "Orders" and "Invoices".
- **Consequences:**
    - Wasted storage space- **Consequences:**
    - Wasted storage space
    - Data inconsistencies (e.g., different addresses for the same customer)
    - Difficulty in maintaining up-to-date information

### Normalization Process

- **Purpose:** To eliminate data redundancy by creating multiple tables based on entity types.
- **Steps:**
    1. Identify repeating data elements across tables.
    2. Create separate tables to store the repeating data (e.g., a "Customer" table with customer addresses).
    3. Establish relationships between the new tables to link related data (e.g., foreign keys referencing customer IDs).

### Example

Consider a database with tables for "Orders" and "Customers":

- **Original Design (Redundant):**
    - Order Table: Contains customer address for each order
    - Customer Table: Contains customer address for each customer

- **Normalized Design:**
    - Order Table: Contains order details (e.g., item, quantity, price)
    - Customer Table: Contains customer details (e.g., name, address)- OrderCustomerLink Table: Links orders to customers via foreign keys (e.g., customer ID)

By normalizing the database, we eliminate data redundancy and improve data integrity.## Understanding Database Normalization

### Introduction

Normalization is a critical concept in database design that aims to eliminate data redundancy and ensure data integrity.

### Steps Involved in Normalization

1. **Identify Denormalized Dataset:** Examine the existing dataset to identify columns that contain a mix of unrelated data.
2. **Decompose Data:** Break down the dataset into smaller tables based on the different types of data present.
3. **Establish Relationships:** Define relationships between the tables. This can be done using keys and foreign keys.
4. **Apply Normalization Levels:** Follow the levels of normalization to further refine the database design.

### Levels of Normalization

**1. First Normal Form (1NF)**

* Eliminates duplicate rows within a table.* Eliminates duplicate rows within a table.
* Each row must be uniquely identifiable by its primary key.

**2. Second Normal Form (2NF)**

* Meets all 1NF requirements.
* Ensures that each non-key attribute is dependent on the entire primary key.

**3. Third Normal Form (3NF)**

* Meets all 1NF and 2NF requirements.
* Removes non-key attributes that are dependent on other non-key attributes.

### Benefits of Normalization

* Reduces data redundancy, saving storage space and improving performance.
* Ensures data integrity by eliminating duplicate and inconsistent data.
* Simplifies database maintenance and updates.
* Improves data security by separating sensitive data into different tables.**Normalization in Database Design**

**Introduction:**
Databases are organized in various ways, referred to as "normal forms," which determine the efficiency and integrity of data storage and retrieval. Normalization aims to decompose a database into smaller, simpler tables to minimize data redundancy and inconsistencies.**Levels of Normalization:**

**1. First Normal Form (1NF):**
- Each cell in a table should contain a single atomic value.
- No two rows should be identical.
- Example: A table with columns "Student ID," "Name," and "Marks" is in 1NF.

**2. Second Normal Form (2NF):**
- Every non-key column must depend on the entire primary key, not just a portion of it.
- Example: A table with columns "Order ID," "Item ID," and "Quantity" may not be in 2NF if "Item ID" is not part of the primary key.

**3. Third Normal Form (3NF):**
- Every non-key column must depend only on the primary key, not on any other non-key columns.
- Example: A table with columns "Employee ID," "Department ID," "Manager ID," and "Salary" may not be in 3NF if "Manager ID" depends on "Department ID" instead of "Employee ID."

**4. Boyce-Codd Normal Form (BCNF):**
- Every determinant determines a candidate key.
- A determinant is a set of attributes that uniquely identifies a row.- Example: A table with columns "Student ID," "Name," and "Major" is in BCNF because "Student ID" uniquely identifies each row.

**5. Fourth Normal Form (4NF):**
- Multivalued dependencies must be removed.
- A multivalued dependency occurs when a single value in one column corresponds to multiple values in another column.
- Example: A table with columns "Author ID," "Book ID," and "Chapters" may not be in 4NF if "Author ID" is multivalued with respect to "Book ID."

**6. Fifth Normal Form (5NF):**
- Join dependencies must be removed.
- A join dependency occurs when two or more tables must be joined to retrieve all relevant data.
- Example: A table with columns "Student ID," "Name," and "Course ID" may not be in 5NF if there are multiple courses with the same name.

**Significance of Normalization:**

* **Data Integrity:** Normalization helps ensure data accuracy and consistency.
* **Data Retrieval Efficiency:** Normalized databases allow for faster data retrieval as redundant data is eliminated.* **Data Modification Efficiency:** Updates and insertions are more efficient in normalized databases.
* **Database Scalability:** Normalization facilitates database growth and expansion by reducing data duplication.## Levels of Normalization

### Introduction

Normalization is a crucial process in database design that ensures data integrity and efficiency. It involves dividing a database into smaller tables to reduce redundancy and anomalies. Different levels of normalization exist, each with varying degrees of complexity and data integrity.

### Levels of Normalization

**First Normal Form (1NF)**

* Removes duplicate rows from a table.
* Ensures that each attribute is atomic (not divisible into smaller units).
* Syntax: PRIMARY KEY constraint for each table

```sql
CREATE TABLE Example (
  ID INT PRIMARY KEY,
  Name VARCHAR(50),
  Age INT
);
```

**Second Normal Form (2NF)**

* Meets all requirements of 1NF.
* Removes partial dependencies on the primary key.* Removes partial dependencies on the primary key.
* Attributes that do not fully depend on the primary key should be placed in separate tables.
* Syntax: FOREIGN KEY constraint to link tables

```sql
CREATE TABLE Example (
  ID INT PRIMARY KEY,
  Name VARCHAR(50)
);

CREATE TABLE ExampleDetails (
  ID INT PRIMARY KEY,
  ExampleID INT REFERENCES Example(ID),
  Age INT
);
```

**Third Normal Form (3NF)**

* Meets all requirements of 2NF.
* Removes transitive dependencies.
* Attributes that depend on other non-key attributes should be placed in separate tables.
* Syntax: Additional FOREIGN KEY constraints to enforce dependencies

```sql
CREATE TABLE Example (
  ID INT PRIMARY KEY,
  Name VARCHAR(50)
);

CREATE TABLE ExampleDetails (
  ID INT PRIMARY KEY,
  ExampleID INT REFERENCES Example(ID),
  Age INT
);

CREATE TABLE ExampleAddresses (
  ID INT PRIMARY KEY,
  ExampleDetailsID INT REFERENCES ExampleDetails(ID),
  Address VARCHAR(100)
);
```

### DenormalizationAddress VARCHAR(100)
);
```

### Denormalization

In certain cases, it may be necessary to denormalize a database, which involves combining data from multiple tables into a single table to improve performance at the cost of some data integrity.

### Conclusion

Normalization is an essential database design technique that ensures data quality and efficiency. Understanding the different levels of normalization helps optimize database design for specific requirements.**Markdown Notes on Denormalized Datasets**

**Introduction**

* A denormalized dataset is a data structure where all data is stored in a single file or table.
* This differs from normalized datasets, where data is stored in multiple tables, with each table representing a specific entity.

**Understanding the Denormalized Dataset**

* **Order Number:** Unique identifier for each sales order.
* **Quantity:** Number of items sold in the order.
* **Price:** Price of each item in the order.
* **Total Cost:** Total cost of the order.* **Total Cost:** Total cost of the order.

**Normalization Process**

To normalize the dataset, we need to separate the data into multiple tables based on entities:

1. **Orders Table:**
    * Order Number
    * Total Cost

2. **Order Items Table:**
    * Order Number
    * Quantity
    * Price

**Benefits of Normalization**

* **Data Integrity:** Prevents data inconsistency by ensuring that related data is stored together.
* **Data Redundancy:** Reduces data duplication, saving storage space and improving performance.
* **Data Consistency:** Enforces data integrity rules, ensuring that data remains consistent across tables.
* **Flexibility:** Makes it easier to add new columns or rows to the dataset as needed.

**Example Code**

```sql
-- Create denormalized table
CREATE TABLE SalesOrders (
  OrderNumber INT PRIMARY KEY,
  Quantity INT,
  Price DECIMAL(10,2),
  TotalCost DECIMAL(10,2)
);

-- Insert data into denormalized table
INSERT INTO SalesOrders (OrderNumber, Quantity, Price, TotalCost)
VALUESVALUES
  (1, 5, 10.00, 50.00),
  (2, 3, 15.00, 45.00),
  (3, 7, 8.00, 56.00);

-- Create normalized tables
CREATE TABLE Orders (
  OrderNumber INT PRIMARY KEY,
  TotalCost DECIMAL(10,2)
);

CREATE TABLE OrderItems (
  OrderNumber INT REFERENCES Orders(OrderNumber),
  Quantity INT,
  Price DECIMAL(10,2),
  PRIMARY KEY (OrderNumber, Quantity)
);

-- Insert data into normalized tables
INSERT INTO Orders (OrderNumber, TotalCost)
SELECT OrderNumber, TotalCost
FROM SalesOrders;

INSERT INTO OrderItems (OrderNumber, Quantity, Price)
SELECT OrderNumber, Quantity, Price
FROM SalesOrders;

-- Drop denormalized table
DROP TABLE SalesOrders;
```**Introduction to Order Management Data**

**Core Concepts:**

* Order: A transaction involving the purchase of goods or services.
* Customer: The individual or organization that places the order.
* Product: The item(s) being purchased.
* Sales Agent: The person responsible for facilitating the sale.

**Data Structure:**

**Order Information:****Data Structure:**

**Order Information:**

* **Order Date:** Date the order was placed.
* **Order Status:** Current status of the order (e.g., pending, shipped, completed).

**Product Information:**

* **Product Code:** Unique identifier for the product.
* **Product Name:** Name of the product.
* **Price:** Cost of the product.

**Customer Information:**

* **Customer Name:** Name of the customer company.
* **Phone Number:** Customer's phone number.
* **Address:** Customer's address.
* **City:** Customer's city.
* **Postal Code:** Customer's postal code.

**Sales Agent Information:**

* **Sales Agent:** Name of the sales agent.

**Additional Information:**

* **Deal Size:** Value of the order in monetary terms.

**Example Table:**

| Order Date | Order Status | Product Code | Product Name | Price | Customer Name | Phone Number | Address | City | Postal Code | Sales Agent | Deal Size |
|---|---|---|---|---|---|---|---|---|---|---|---||---|---|---|---|---|---|---|---|---|---|---|---|
| 2023-03-05 | Shipped | P1001 | iPhone 14 Pro | $1299 | Apple Corp. | 123-456-7890 | 1 Infinite Loop | Cupertino | 95014 | John Smith | $12990 |## Normalization in Database Design

### Understanding Normalization

Normalization is a process of structuring a database to reduce data redundancy and ensure data integrity. It involves organizing data into tables and defining relationships between them to minimize data duplication and anomalies.

### First Normal Form (1NF)

The first step in normalization is to ensure that the database satisfies the First Normal Form (1NF). 1NF has two rules:

- **Rule 1 (Single Value Rule):** Each column (attribute) in a table must contain a single, atomic value.
- **Rule 2 (Atomic Value Rule):** The value in each column must not be further divisible into smaller, meaningful units.

### Table Structure for 1NF

To achieve 1NF, you must ensure that:

- Each row in the table represents a unique entity.- Each row in the table represents a unique entity.
- Each column represents a specific attribute of the entity.
- Each cell contains a single, non-repeating value.

### Example

Let's consider a table with the following columns:

| Student ID | Name | Courses | Scores |
|---|---|---|---|
| 1001 | David | Math, Science | 90, 85 |

This table violates 1NF because the `Courses` and `Scores` columns contain multiple values for a single row (entity). To normalize it, we can create separate tables:

**Students Table:**

| Student ID | Name |
|---|---|
| 1001 | David |

**Courses Table:**

| Student ID | Course |
|---|---|
| 1001 | Math |
| 1001 | Science |

**Scores Table:**

| Student ID | Course | Score |
|---|---|---|
| 1001 | Math | 90 |
| 1001 | Science | 85 |**Understanding Data Normalization**

**Introduction**

Data normalization is a process of organizing data in a way that eliminates inconsistencies and redundancies. It helps ensure data accuracy, integrity, and efficiency.

**Rule 1: Atomic Values****Rule 1: Atomic Values**

* Each column should contain only one single value.
* This prevents data duplication and ensures accuracy.

**Example of Violation**

* A customer record with multiple product codes or names violates rule 1.
* This indicates that a single transaction involved multiple products, which should be represented in separate rows.

**Steps for Normalization**

1. **Identify Non-Atomic Columns:** Locate columns that contain multiple values (e.g., comma-separated values).
2. **Split Columns:** Create new columns for each unique value in the non-atomic columns.
3. **Create Relationships:** Establish relationships between the new columns to maintain data integrity.

**Benefits of Normalization**

* **Improved Data Accuracy:** Eliminates data duplication and inconsistencies, reducing errors.
* **Enhanced Data Integrity:** Ensures that data meets the defined rules and constraints.
* **Increased Data Efficiency:** Reduces storage requirements and improves performance.* **Enhanced Data Analysis:** Facilitates data analysis by organizing data in a logical and structured manner.**Understanding Database Normalization: A Beginner's Guide**

**Introduction**

Database normalization is a process that ensures that data in a database is organized in a logical and efficient manner. It aims to eliminate data redundancy, inconsistencies, and anomalies by structuring data into tables and columns.

**First Normal Form (1NF)**

1NF is the first level of database normalization. It requires that:

- Each table contains only one type of data (e.g., customer information, order information).
- Each column within a table represents a single attribute of that data type (e.g., customer name, order number).
- Each row in a table represents a unique instance of the data type (e.g., a specific customer, a specific order).

**Example of Violating 1NF**

In the given text, a single order statement contains details of two different items. This violates 1NF because:- The order information should be separated into two orders, as it represents two distinct purchases.
- The item details should be stored in a separate table, with each row representing a unique item.

**How to Fix the Violation**

To fix the violation, the data should be split into two orders and two items. The structure would then look like this:

| **Order Table** | | **Item Table** |
|---|---|---|
| Order ID | | Item ID |
| Customer ID | | Description |
| Order Date | | Quantity |

This structure satisfies 1NF because each table contains only one type of data, each column represents a single attribute, and each row represents a unique instance.

**Importance of Normalization**

Normalization is crucial for:

- **Data integrity**: Ensuring that data is accurate and consistent throughout the database.
- **Data efficiency**: Reducing data redundancy, minimizing storage space and improving performance.
- **Data flexibility**: Making it easier to update, add, or delete data without introducing errors.- **Application performance**: Improving the speed and efficiency of database operations.## Data Transformation: Splitting Multiple Values into Separate Records

### Concept

When working with data, it's common to encounter columns that contain multiple values separated by a delimiter (e.g., commas). To properly analyze and process this data, it's often necessary to split these values into individual records.

### Step-by-Step Procedure

**1. Copy and Paste Data**

Copy the column containing the multiple values and paste it into a new location.

**2. Remove Extra Values**

Remove all but one of the values from each row, retaining only the values you need.

**3. Adjust Quantities and Prices (if necessary)**

If the values represent quantities or prices, adjust them accordingly to reflect the individual records. For example, if a row contains "4, 780", you would split it into two rows: "4" and "780".

**4. Create New Rows for Products and Prices****4. Create New Rows for Products and Prices**

Create new rows for any additional product or price information associated with the values. For example, if the values were "Bus: $800, Truck: $900", you would create two rows: one for the Bus with a price of $800, and one for the Truck with a price of $900.

### Example

**Original Data:**

| Item | Quantity | Price |
|---|---|---|
| Bus, Truck | 4, 780 | 800, 900 |

**Split Data:**

| Item | Quantity | Price |
|---|---|---|
| Bus | 4 | 800 |
| Truck | 780 | 900 |**1. Understanding Data Normalization**

   - **Normalization:** A process of organizing data to reduce redundancy and inconsistencies.

**2. First Normal Form (1NF)**

   - **Definition:** A table where each column contains only a single value for each row.

   - **Example:** Splitting a column with multiple values (e.g., "Red, Blue, Green") into individual columns ("Color1", "Color2", "Color3").

**3. Second Normal Form (2NF)****3. Second Normal Form (2NF)**

   - **Definition:** A table where there is a unique identifier (key) that uniquely identifies each row.

   - **Requirement:** The key cannot be dependent on non-key attributes.

**4. Primary Key**

   - **Definition:** A unique identifier (or combination of attributes) that distinguishes each row in a table.

   - **Importance:** Facilitates efficient data retrieval and ensures data integrity.

**5. Rule for 2NF Compliance**

   - **Step 1:** Identify the primary key.
   - **Step 2:** Check that all non-key attributes are fully dependent on the primary key, meaning they cannot be uniquely identified without the primary key.

**6. Example of 2NF Violation**

   - **Table:** Students (StudentID, Name, Class)
   - **Violation:** Class is not fully dependent on StudentID, as multiple students can be in the same class.

**7. Modification for 2NF Compliance**

   - **Creation of a new table:** Classes (ClassID, ClassName)- **Creation of a new table:** Classes (ClassID, ClassName)
   - **Addition of Foreign Key:** ClassID in the Students table, referencing the ClassID in the Classes table.

**8. Importance of Normalization**

   - Reduces data redundancy, improving storage efficiency.
   - Minimizes data inconsistencies and errors.
   - Enhances data integrity and reliability.
   - Facilitates efficient data retrieval and analysis.## Identifying Uniqueness in Data

### Core Concept:

Data uniqueness refers to the property where each record in a dataset is distinct and cannot be duplicated. This is essential for maintaining the integrity and accuracy of data.

### Types of Uniqueness:

* **Unique Columns:** Columns that contain unique values for each record. Example: An order number column.
* **Composite Uniqueness:** When a combination of columns (composite key) uniquely identifies each record. Example: A combination of order number and product code.

### Example:

Consider a table with the following data:### Example:

Consider a table with the following data:

| Order Number | Product Code | Customer |
|---|---|---|
| 10101 | P1 | John |
| 10102 | P2 | Mary |
| 10103 | P3 | Bob |
| 10104 | P4 | Jane |
| 10105 | P5 | David |
| 10106 | P6 | John |
| 10106 | P7 | Mary |

### Rule 1: Unique Columns (Order Number)

Initially, the order number column appears to provide unique values for each record. However, the last two records share the same order number (10106). This violates the principle of unique columns.

### Rule 2: Composite Uniqueness (Order Number and Product Code)

Upon further analysis, we can see that each record has a unique combination of order number and product code. This means that even though the last two records have the same order number, they are still unique because they represent different products.

### Conclusion:### Conclusion:

To determine data uniqueness, consider both individual columns and their combinations. In this case, the combination of order number and product code provides composite uniqueness, satisfying rule 2.## Introduction to Database Normalization

### Normalization Levels

Database normalization is a process of organizing data in a relational database to reduce data redundancy and improve data integrity. It involves breaking down complex data structures into simpler ones, ensuring that each piece of data appears only once in the database.

### First Normal Form (1NF)

1NF requires that each row in a table represents a unique entity, and each column contains a single attribute of that entity. This means that:
- Each row should have a unique identifier (primary key)
- Each column should represent a specific characteristic or property of the entity

### Second Normal Form (2NF)### Second Normal Form (2NF)

2NF builds upon 1NF and requires that every non-key attribute (attribute that is not part of the primary key) in a table must be fully dependent on the primary key. In other words:
- Every non-key attribute must be dependent on the primary key alone, not on a subset of the primary key

### Rules for 2NF

There are three rules for 2NF:

1. The table must be in 1NF.
2. Each non-key attribute must be fully dependent on the primary key.
3. No non-key attribute can be transitively dependent on the primary key (i.e., indirectly dependent through another non-key attribute).

### Example

Consider a table called `Orders`:

| OrderID | CustomerID | ProductID | Quantity |
|---|---|---|---|
| 1 | 10 | 20 | 5 |
| 2 | 10 | 30 | 10 |
| 3 | 20 | 20 | 2 |

This table is not in 2NF because the `Quantity` attribute is dependent on both the `OrderID` and `ProductID`. To make it 2NF, we can split it into two tables:

`Orders`:
| OrderID | CustomerID |
|---|---|
| 1 | 10 |
| 2 | 10 |
| 3 | 20 ||---|---|
| 1 | 10 |
| 2 | 10 |
| 3 | 20 |

`OrderItems`:
| OrderID | ProductID | Quantity |
|---|---|---|
| 1 | 20 | 5 |
| 2 | 30 | 10 |
| 3 | 20 | 2 |**Understanding Database Normalization: Candidate Key**

**Introduction:**

Normalization is a technique used in database design to ensure data integrity and efficiency. One of the key concepts in normalization is the candidate key.

**Candidate Key:**

A candidate key is a set of column(s) that uniquely identifies each record in a table. It is a minimal set of columns that can be used to distinguish one record from another.

**Properties of a Candidate Key:**

* **Uniqueness:** Each unique combination of values in the candidate key identifies a different record.
* **Minimality:** The candidate key does not contain any unnecessary columns that do not contribute to uniqueness.

**Importance of Candidate Keys:**

Candidate keys are crucial for:

* Identifying records efficiently* Identifying records efficiently
* Maintaining data integrity by ensuring that records with identical values are not duplicated
* Establishing relationships between tables by linking them through foreign keys

**Example:**

Consider the following table:

| Order Number | Product Code | Quantity |
|---|---|---|
| 100 | P1 | 10 |
| 200 | P2 | 20 |
| 300 | P3 | 30 |

In this example, the combination of "Order Number" and "Product Code" uniquely identifies each record, making it the candidate key.

**Syntax:**

In SQL, you can define a candidate key using the `PRIMARY KEY` constraint:

```sql
CREATE TABLE orders (
  OrderNumber INTEGER NOT NULL,
  ProductCode INTEGER NOT NULL,
  Quantity INTEGER NOT NULL,
  PRIMARY KEY (OrderNumber, ProductCode)
);
```

This syntax ensures that the combination of "Order Number" and "Product Code" cannot contain duplicate values, enforcing the uniqueness constraint of the candidate key.## Candidate Keys

### Definition### Definition

A candidate key is a set of attributes that can uniquely identify each record in a table. A table can have multiple candidate keys.

### Characteristics

* **Unique:** The combination of values in a candidate key must be unique for each record.
* **Minimal:** A candidate key cannot contain any redundant attributes.

### Example

Consider the following table:

```
Order | Product | Quantity
------|---------|---------
1      | A       | 10
2      | B       | 20
3      | A       | 30
```

In this table, the combination of `Order` and `Product` is a candidate key because it uniquely identifies each record. This means that there is only one row for each unique combination of order and product.

### Primary Key

A primary key is a special type of candidate key that is chosen as the unique identifier for each record in a table. Only one primary key can be defined for a table.

### Non-Key Attributes### Non-Key Attributes

Non-key attributes are attributes that are not part of any candidate key. They provide additional information about the records in a table.

### Significance

Candidate keys play a crucial role in database design because they ensure the integrity and uniqueness of data. They are used to:

* Identify and retrieve specific records from a table
* Create relationships between tables
* Enforce referential integrity**Key Concepts of Second Normal Form (2NF)**

**1. Primary and Candidate Keys**

* **Primary Key:** A unique identifier that distinguishes each row in a table. It cannot contain null values.
* **Candidate Key:** A set of columns that collectively identify each row uniquely. There can be multiple candidate keys in a table.

**2. Non-Key Columns**

* Columns that are not part of the primary or candidate keys. They contain data related to the entities represented by the table.

**Rule 2 of 2NF: Non-Key Attributes Dependency****Rule 2 of 2NF: Non-Key Attributes Dependency**

* All non-key attributes must be fully dependent on the candidate key.
* **Full Dependency:** A non-key attribute is fully dependent on the candidate key if its value is uniquely determined by the value of the candidate key.
* **Partial Dependency:** If a non-key attribute is dependent on only a subset of the candidate key, it violates 2NF. In this case, the table should be split into multiple tables where each table contains only attributes that are fully dependent on a candidate key.

**Example:**

Consider a table with the following columns:

```
Order Number | Quantity | Item | Total Cost | Status
```

* **Candidate Key:** Order Number
* **Non-Key Columns:** Quantity, Item, Total Cost, Status

All non-key columns (Quantity, Item, Total Cost, Status) are fully dependent on the candidate key (Order Number). This means that for each unique order number, there is a unique set of values for these non-key columns.

**Example of Violation:****Example of Violation:**

Consider a table with the following columns:

```
Customer ID | Order Number | Product | Quantity
```

* **Candidate Key:** Customer ID, Order Number
* **Non-Key Column:** Product

The non-key column Product is only partially dependent on the candidate key. For a given customer and order number, there can be multiple different products ordered. Therefore, this table violates 2NF and should be split into two tables:

* **Table 1:** Customer ID, Order Number
* **Table 2:** Customer ID, Order Number, Product, Quantity## Normalization: Second Normal Form (2NF)

### Introduction

Normalization is a crucial concept in database design that helps ensure data integrity and efficiency. The Second Normal Form (2NF) is one of the levels of normalization that addresses partial dependencies.

### Candidate Key and Partial Dependencies

* **Candidate Key:** A set of attributes (columns) that uniquely identifies each row in a table.* **Partial Dependency:** A non-key column that depends on only a portion of the candidate key.

### Violating 2NF

A table violates 2NF when there are non-key columns that have partial dependencies on the candidate key. This means the non-key columns are dependent on a subset of the candidate key, rather than the entire key.

### Identifying Violating Columns

To identify violating columns:

1. Find the candidate key.
2. Check if any non-key columns depend on only a portion of the candidate key.

### Resolving 2NF Violations

To resolve 2NF violations, split the table into multiple tables based on the partial dependencies:

* Create a new table for each violating non-key column.
* The candidate key of the original table becomes the primary key of the new table.
* The violating non-key column becomes a foreign key in the new table, referencing the primary key of the original table.

### Example of Resolving 2NF Violation

Consider the following table:Consider the following table:

| Order Number | Quantity | Item Price | Product Code | Product Name | Product Price |
|---|---|---|---|---|---|

This table violates 2NF because:

* `Quantity`, `Item Price`, and `Cost` are dependent on `Order Number` only.
* `Product Name` and `Product Price` are dependent on `Product Code` only.

To resolve the violation:

* Split the table into two new tables:

    **Orders Table:**

    | Order Number | Quantity | Item Price | Cost |
    |---|---|---|---|

    **Products Table:**

    | Product Code | Product Name | Product Price |
    |---|---|---|

### Conclusion

Enforcing 2NF ensures that non-key columns are fully dependent on the entire candidate key, improving data integrity and reducing redundancy.## Understanding Database Normalization: Second Normal Form (2NF)

### Introduction### Introduction

Database normalization is a process of organizing data in a way that eliminates data redundancy and ensures data integrity. Second Normal Form (2NF) is a specific rule that helps ensure data is stored efficiently and accurately.

### Key Concepts

* **Candidate Key:** A set of attributes that uniquely identifies each row in a table.
* **Dependency:** The relationship between attributes where the value of one attribute determines the value of another.
* **Partial Dependency:** When a non-key attribute is dependent on only a portion of the candidate key.

### 2NF Rule

A table is in 2NF if:

* It is in 1NF (all values are atomic and not divisible).
* Every non-key attribute is fully dependent on the entire candidate key, not just a portion of it.

### Identifying Non-2NF Tables

To identify tables that violate 2NF, look for non-key attributes that are only partially dependent on the candidate key. For example, consider the following table:| ProductCode | Motorcycle | Price | CustomerName | Address | PhoneNumber |
|---|---|---|---|---|---|

In this table, the product name and price are partially dependent on the ProductCode, which is a candidate key. This violates 2NF because the product name and price could change without the ProductCode changing.

Similarly, the customer information (CustomerName, Address, PhoneNumber) is not dependent on any part of the candidate key (ProductCode). This also violates 2NF.

### Splitting Tables

To correct 2NF violations, we need to split the table into multiple tables based on the dependencies:

* **Product Table:**
```
| ProductCode | Motorcycle | Price |
```

* **Customer Table:**
```
| CustomerName | Address | PhoneNumber |
```

### Example

Consider the following data:

| OrderID | ProductCode | Motorcycle | Price | CustomerName | Address | PhoneNumber |
|---|---|---|---|---|---|---|
| 1 | A | Yamaha | 500 | John | 10 Main St | 555-1212 |
| 2 | B | Harley | 800 | Mary | 15 Elm St | 555-2323 || 2 | B | Harley | 800 | Mary | 15 Elm St | 555-2323 |
| 3 | A | Ducati | 600 | John | 10 Main St | 555-1212 |

By splitting the table into two tables, we can ensure that each non-key attribute is fully dependent on the candidate key:

**Product Table:**
```
| ProductCode | Motorcycle | Price |
|---|---|---|
| A | Yamaha | 500 |
| B | Harley | 800 |
| C | Ducati | 600 |
```

**Customer Table:**
```
| CustomerName | Address | PhoneNumber |
|---|---|---|
| John | 10 Main St | 555-1212 |
| Mary | 15 Elm St | 555-2323 |
```

### Benefits of 2NF

* Reduces data redundancy
* Improves data integrity
* Makes data easier to update and maintain
* Enhances query performance**Database Table Separation**

**Introduction:**
Database table separation is a crucial concept in database design that ensures data integrity and efficient retrieval. It involves organizing data into multiple tables based on logical entities.

**Benefits of Table Separation:****Benefits of Table Separation:**

- **Data Integrity:** Separate tables prevent data redundancy and inconsistencies. Each piece of data is stored only once, eliminating potential errors from duplication.
- **Efficient Retrieval:** Tables organized by specific entities allow for faster and more targeted data retrieval. Queries can be focused on specific tables, reducing the amount of data that needs to be scanned.
- **Maintainability:** Separating tables simplifies database maintenance. Changes or additions to one table do not affect other tables, making it easier to manage and update the database.

**Steps for Table Separation:**

1. **Identify Logical Entities:** Determine the different entities (e.g., customers, products, orders) that constitute the system.
2. **Create Separate Tables:** Create a separate table for each entity, including only the relevant data for that entity.3. **Establish Relationships:** Determine the relationships between the entities (e.g., customers place orders, products are purchased by customers) and establish foreign key constraints to link them.
4. **Normalize Data:** Normalize the tables by removing redundant data and breaking them down into smaller, more specific tables.

**Example:**

In the provided text, the following table separation has been applied:

- Orders Table: Contains order information.
- Products Table: Contains product information.
- Customers Table: Contains customer information.

By separating these tables, the database ensures data integrity by preventing duplicate customer or product records. It also allows for efficient retrieval of specific data and simplified maintenance of the database.

**Code Syntax (SQL):**

```sql
-- Create the Orders table
CREATE TABLE Orders (
  Order_ID INT PRIMARY KEY,
  Customer_ID INT,
  Product_ID INT,
  Quantity INT,
  FOREIGN KEY (Customer_ID) REFERENCES Customers(Customer_ID),FOREIGN KEY (Customer_ID) REFERENCES Customers(Customer_ID),
  FOREIGN KEY (Product_ID) REFERENCES Products(Product_ID)
);

-- Create the Products table
CREATE TABLE Products (
  Product_ID INT PRIMARY KEY,
  Name VARCHAR(255),
  Price DECIMAL(10, 2)
);

-- Create the Customers table
CREATE TABLE Customers (
  Customer_ID INT PRIMARY KEY,
  Name VARCHAR(255),
  Address VARCHAR(255)
);
```**Normal Forms in Database Design**

**1. First Normal Form (1NF)**

* Ensures that each record in a table contains only one entity.
* No repeating groups or multi-valued attributes.
* Each column represents a single attribute of the entity.

**2. Second Normal Form (2NF)**

* Requires a table to be in 1NF and every non-key attribute must be fully dependent on the primary key.
* Eliminates partial dependencies between non-key attributes and key attributes.

**3. Third Normal Form (3NF)**

* Requires a table to be in 2NF and every non-key attribute must be directly dependent on the primary key.* Eliminates transitive dependencies, where a non-key attribute is dependent on another non-key attribute.

**Creating Normalized Tables**

**Step 1: Identify Entities and Attributes**

* Determine the different types of entities in your data (e.g., orders, products, customers).
* Identify the attributes associated with each entity (e.g., order ID, product name, customer address).

**Step 2: Split Tables into 1NF**

* Divide tables into smaller tables to remove repeating groups.
* Each table should contain only one entity and its attributes.

**Step 3: Assign Primary Keys**

* Designate a unique identifier (primary key) for each table.
* The primary key should be a field that uniquely identifies each record in the table.

**Step 4: Establish Foreign Keys**

* Create foreign keys in tables to establish relationships between them.
* A foreign key in one table references the primary key of another table.

**Example:**

**Orders Table (1NF)**
```
| Order ID | Customer ID | Product ID | Quantity |```
| Order ID | Customer ID | Product ID | Quantity |
|---|---|---|---|
| 1 | 10 | 20 | 5 |
| 2 | 11 | 21 | 3 |
```

**Products Table (1NF)**
```
| Product ID | Product Name | Price |
|---|---|---|
| 20 | Widget A | $10 |
| 21 | Widget B | $15 |
```

**Customers Table (1NF)**
```
| Customer ID | Customer Name | Email |
|---|---|---|
| 10 | John Doe | john@example.com |
| 11 | Jane Smith | jane@example.com |
```**Understanding Primary Keys**

**What is a Primary Key?**

A primary key is a unique identifier assigned to each row in a database table. It ensures that no two rows have the same data, making it easier to find and retrieve specific records.

**Creating a Primary Key**

When creating a primary key, consider the following:

* **Uniqueness:** Each primary key value must be unique within the table.
* **Irreversibility:** The primary key should not be changed or updated over time.
* **Suitability:** The primary key should be appropriate for the data it identifies.

**Steps to Create a Primary Key****Steps to Create a Primary Key**

1. **Identify a Unique Column:** Choose a column that contains unique values for each row, such as an order number or customer ID.
2. **Add a New Column for the Primary Key:** If a unique column does not exist, add a new column to the table.
3. **Assign Unique Values:** Populate the new column with unique values, such as sequential numbers or UUIDs (Universally Unique Identifiers).
4. **Set Primary Key Constraint:** Define the new column as the primary key using a constraint. This prevents duplicate values from being inserted.

**Example**

In the given text, a new primary key column named "order_id" is added to the "orders" table. The following SQL syntax can be used:

```
ALTER TABLE orders ADD COLUMN order_id INT NOT NULL AUTO_INCREMENT;
ALTER TABLE orders ADD PRIMARY KEY (order_id);
```

This creates a unique, sequential primary key for the "orders" table.**Notes on Identifying a Primary Key**

**1. Definition:****1. Definition:**

- A primary key is a unique identifier for each row in a database table.
- It ensures that every row can be uniquely identified and distinguished from all other rows.

**2. Identifying a Primary Key:**

- **Natural Key:** A unique attribute or combination of attributes that naturally identifies each row (e.g., product code in the example).
- **Surrogate Key:** An artificial, auto-generated value used as a primary key (e.g., ID column in many tables).

**3. Considerations:**

- The primary key should be unique and non-null (cannot be empty).
- It should be chosen carefully to ensure uniqueness and efficiency.
- If duplicate records exist, they should be removed to maintain data integrity.

**4. Example:**

- In the text provided, the product code for each product in the "product stable" can be used as the primary key.
- Duplicate records for buses and trucks are removed to ensure uniqueness.
- The product code column is then defined as the primary key column.

**5. Syntax and Example:****5. Syntax and Example:**

```sql
-- Create a table with a primary key
CREATE TABLE product_stable (
  product_code VARCHAR(255) PRIMARY KEY,
  product_name VARCHAR(255),
  ...
);

-- Insert data with unique product codes
INSERT INTO product_stable (product_code, product_name)
VALUES ('PROD001', 'Product 1'),
       ('PROD002', 'Product 2'),
       ('PROD003', 'Product 3');

-- Select data based on the primary key
SELECT * FROM product_stable
WHERE product_code = 'PROD001';
```**Primary Key in Database Tables**

**Concept:**

* A primary key is a unique identifier for each row in a database table.
* It ensures that every row has a distinct identity and can be uniquely retrieved.

**Guidelines for Choosing a Primary Key:**

* **Uniqueness:** The values in the primary key column must be different for every row.
* **Non-Null:** The primary key column cannot contain null values (empty or missing values).
* **Immutability:** The primary key value should not change once it is assigned to a row.

**Example:****Example:**

In the provided text, a primary key is added to the "customer" table.

**Code:**

```sql
ALTER TABLE customer
ADD COLUMN customer_id INT NOT NULL AUTO_INCREMENT,
ADD PRIMARY KEY (customer_id);
```

* `customer_id` is the new primary key column.
* `INT` specifies that it is an integer data type.
* `NOT NULL` ensures that it cannot contain null values.
* `AUTO_INCREMENT` automatically generates a unique value for each new row inserted.

**Benefits of Using a Primary Key:**

* Efficient data retrieval: Primary keys allow for faster data retrieval by quickly identifying the specific row needed.
* Data integrity: Enforces uniqueness and prevents duplicate rows, ensuring the accuracy and consistency of data.
* Data relationships: Facilitates the establishment of relationships between tables by linking rows based on their primary keys.

**Removing Duplicate Records:**

* The `REMOVE DUPLICATES` command in the example text identifies and removes duplicate rows.* This helps to eliminate redundant data and create a more accurate representation of the real-world entities being represented in the table.**Primary Keys and Database Normalization**

**Core Concepts:**

* **Primary Key:** A unique identifier associated with each row in a table, ensuring uniqueness and ease of data retrieval.
* **Database Normalization:** A process of organizing data into tables to eliminate data redundancy and anomalies.

**Steps to Normalize a Database:**

**Rule 3: Eliminate Redundant Data**

**Two Approaches to Satisfying Rule 3:**

**Approach 1: Adding a Foreign Key Column**

* Add a column to the "Orders" table that references a primary key in the "Products" table, establishing a relationship between the two tables.
* Syntax:
```
ALTER TABLE Orders ADD COLUMN product_id INT NOT NULL;
ALTER TABLE Orders ADD FOREIGN KEY (product_id) REFERENCES Products(product_id);
``````
* Example: Each row in the "Orders" table now includes a product ID, which references a unique product in the "Products" table.

**Approach 2: Creating a Separate "Order Items" Table**

* Create a separate table called "Order Items" with two columns: order_id (foreign key to "Orders") and product_id (foreign key to "Products").
* Syntax:
```
CREATE TABLE Order_Items (
  order_id INT NOT NULL,
  product_id INT NOT NULL,
  FOREIGN KEY (order_id) REFERENCES Orders(order_id),
  FOREIGN KEY (product_id) REFERENCES Products(product_id)
);
```
* Example: Each row in the "Order Items" table represents a specific product item within an order.

**Benefits of Multiple Normalization Approaches:**

* Flexibility in data organization based on project requirements.
* No strict rules on how to normalize a database.
* Choice of approach depends on factors such as company guidelines and performance considerations.**Understanding Database Normalization**

**Introduction****Introduction**
Database normalization is a process that involves structuring a database to minimize data redundancy and improve data integrity. One of the important rules of normalization is the Second Normal Form (2NF).

**2NF: Elimination of Partial Dependencies**
2NF states that every non-key attribute (column) in a table must be fully dependent on the primary key and not just part of it. In other words, each column must depend directly on the primary key, not on any subset of it.

**Example: Identifying a Partial Dependency**
Consider the following table:

| OrderNumber | ProductCode | CustomerID |
|-------------|--------------|------------|
| 1           | Buses        | 100        |
| 2           | Trucks       | 100        |

In this table, the primary key is `OrderNumber`. However, the column `CustomerID` is partially dependent on the primary key, as it is repeating for the same customer for different orders.

**Normalization to 2NF****Normalization to 2NF**
To address the partial dependency, we can create a new table called `Relationships` with the following columns:

| OrderNumber | ProductCode | CustomerID |
|-------------|--------------|------------|
| 1           | Buses        | 100        |
| 2           | Trucks       | 100        |

By creating this new table, we have eliminated the partial dependency, as `CustomerID` is now fully dependent on the primary key of the `Relationships` table (which includes both `OrderNumber` and `ProductCode`).

**Benefits of 2NF**
- Improved data integrity: Ensures that changes to the primary key will cascade appropriately to related columns.
- Reduced data redundancy: Eliminates duplicate data, such as customer information that is repeated for multiple orders.
- Enhanced data retrieval efficiency: Allows for faster and more efficient retrieval of data by directly accessing the primary key.**Database Normalization: Second Normal Form (2NF)****Goal:** Eliminate partial dependencies on non-key attributes.

**Steps to Achieve 2NF:**

* **Identify the primary key (PK)** of each table.
* For each non-key attribute (NKA), determine the attributes on which it is dependent.
* If a NKA is fully dependent on a subset of the PK, move that NKA to a new table with its own PK.

**Example:**

**Original Table:** Customers, Products, Orders

**Relationships:**
* Products: PK ProductID
* Customers: PK CustomerID
* Orders: PK OrderID, FK ProductID, FK CustomerID

**Partial Dependency:**
* Product Name depends on ProductID only.
* Customer Name depends on CustomerID only.

**Normalized Tables:**

**Products Table:**
* PK: ProductID
* Attributes: Product Name, Price

**Customers Table:**
* PK: CustomerID
* Attributes: Customer Name, Email

**Orders Table:**
* PK: OrderID
* Attributes: ProductID, CustomerID, Quantity

**Relationship Table:**
* PK: ID
* Attributes: ProductID, CustomerID, OrderID

**Benefits of 2NF:****Benefits of 2NF:**

* Ensures data integrity by eliminating duplicate data.
* Improves performance by reducing the number of table joins required.
* Facilitates easier data updates and insertions.

**Note:**
* A database can be in 2NF without being in 1NF.
* The process of normalization should be iterative, aiming for higher normal forms to further optimize the database.## Third Normal Form (3NF) in Database Normalization

### Introduction

Third Normal Form (3NF) is a set of rules used in database design to ensure data integrity and reduce data redundancy. It builds upon the principles of Second Normal Form (2NF).

### Key Concepts

- **Transitive Dependency:** A column C depends transitively on another column B if C depends on B and B depends on a primary key.
- **3NF Rule 1:** A relation R is in 3NF if it is in 2NF.
- **3NF Rule 2:** There should be no transitive dependencies on non-key columns.

### How to Enforce 3NF### How to Enforce 3NF

To convert a dataset from 2NF to 3NF, split columns that create transitive dependencies into separate tables.

### Example

Consider the following table:

| StudentID | Course | Grade |
|---|---|---|
| 1 | Math | A |
| 2 | Physics | B |
| 3 | Math | C |

In this table, the column **Grade** depends on **Course**, which in turn depends on the primary key **StudentID**. This creates a transitive dependency on **Grade** to the primary key.

To remove the transitive dependency, split the table into two tables:

| StudentID | Course |
|---|---|
| 1 | Math |
| 2 | Physics |
| 3 | Math |

| Course | Grade |
|---|---|
| Math | A |
| Math | C |
| Physics | B |

Now, **Grade** only depends on **Course**, which is a primary key, satisfying 3NF.

### Benefits of 3NF

- Reduces data redundancy
- Improves data integrity and consistency
- Simplifies queries and data manipulation
- Enhances database performance**Functional Dependency and Transitivity**

**Key Terms:****Key Terms:**

* **Functional Dependency:** When the value of one attribute (A) uniquely determines the value of another attribute (B) in a table.
* **Transitivity:** If A is functionally dependent on B and B is functionally dependent on C, then A is functionally dependent on C.

**Explanation:**

Consider a dataset with three columns:

* **a**: Customer Name
* **b**: Order Number
* **c**: Sales Contact Name

**Transitivity in Action:**

* **a** is functionally dependent on **b** because knowing the customer name allows you to determine the corresponding order.
* **b** is functionally dependent on **c** because knowing the order number reveals the sales contact.

Based on transitivity, we can conclude that:

* **a** is functionally dependent on **c**. This means that knowing the customer name directly provides information about the sales contact.

**Simplified Explanation:****Simplified Explanation:**

Imagine a list of orders where each customer has a unique order. If you know the customer's name (**a**), you can find the order number (**b**). Similarly, if you know the order number (**b**), you can find the sales contact (**c**). Therefore, knowing the customer's name (**a**) also gives you the sales contact (**c**).**Entity Relationship Modeling (ERM) and Data Normalization**

**Core Concepts:**

* **Entity Relationship Model (ERM):** A blueprint that depicts the relationships between entities (e.g., customers, orders) in a database.
* **Normalization:** A process of organizing data into tables to reduce data redundancy and maintain data integrity.
* **Transitive Dependency:** When a column in a table depends on another column that, in turn, depends on a third column.

**Normalization Process:**

**Second Normal Form (2NF):**

1. Split the customer information into a separate table (**CustomerTable**).2. Identify the transitive dependency in the **OrdersTable** (salesperson's information depends on customer's information).
3. Remove the columns causing the dependency (salesperson's name) from the **OrdersTable**.

**Example:**

**CustomerTable:**

| CustomerID | CustomerName |
|---|---|
| 1 | John Doe |
| 2 | Jane Smith |

**OrdersTable:**

| OrderID | CustomerID | SalespersonID |
|---|---|---|
| 100 | 1 | NULL |
| 101 | 2 | NULL |

**SalespersonTable:**

| SalespersonID | SalespersonName |
|---|---|
| 1 | Bob Jones |
| 2 | Mary Smith |

**Benefits of Normalization:**

* Reduces data duplication and errors.
* Improves data integrity by enforcing referential constraints.
* Enhances data retrieval and update efficiency.**Teaching Notes on Database Design for Beginners**

**Understanding Duplicates and Primary Keys**

**What is a duplicate?**

A duplicate occurs when multiple rows in a table contain the same data. For example, in an employee table, two employees might have the same ID number.**Why remove duplicates?**

Duplicates can clutter up your database and make it difficult to manage. For example, if you have two employees with the same ID number, it can be hard to tell which employee is which.

**Primary keys**

A primary key is a unique identifier for each row in a table. It ensures that no two rows have the same data.

**Creating a primary key**

To create a primary key, follow these steps:

1. Identify a column that uniquely identifies each row. For example, in an employee table, the employee ID would be a good primary key.
2. Add the PRIMARY KEY constraint to the column. In SQL, you would use the following syntax:

```sql
ALTER TABLE employee ADD PRIMARY KEY (employee_id);
```

**Example**

In the provided text, the employee ID is used as the primary key for the employee table. This ensures that there are no duplicate employees in the table.

**Moving Columns**

**Why move columns?**

Sometimes, you may want to move columns to improve the readability or organization of your database.**How to move columns**

To move a column, follow these steps:

1. Use the ALTER TABLE statement.
2. Specify the name of the table you want to modify.
3. Use the ADD COLUMN clause to add the column to its new location.
4. Use the DROP COLUMN clause to remove the column from its old location.

**Example**

In the provided text, the deal size column is moved to the left to make it more visible. This improves the readability of the orders table.**Normalization in Database Design**

**Introduction**

Normalization is a process of organizing data in a database to reduce redundancy and improve data integrity.

**Third Normal Form (3NF)**

3NF is the highest level of normalization that ensures that all columns in a table are dependent on the primary key only.

**Relationship Table**

A relationship table is used to establish links between tables that have a many-to-many relationship.

**Creating a Relationship Table**

To create a relationship table:

1. Identify the primary keys of the related tables.1. Identify the primary keys of the related tables.
2. Create a new table with two columns, each containing one of the primary keys.
3. Populate the relationship table with the combinations of primary keys that represent the relationships.

**Example**

**Employee Table**

| Employee ID | Name |
|---|---|
| 1 | John |
| 2 | Mary |
| 3 | Bob |

**Order Table**

| Order ID | Employee ID | Product ID |
|---|---|---|
| 1 | 1 | A |
| 2 | 2 | B |
| 3 | 3 | C |

**Relationship Table**

| Employee ID | Order ID |
|---|---|
| 1 | 1 |
| 1 | 2 |
| 2 | 3 |

**Explanation**

The relationship table links the Employee table and the Order table by their primary key columns. This establishes the many-to-many relationship between employees and orders, as each employee can place multiple orders and each order can be placed by multiple employees.## Understanding Foreign Keys in Database Normalization

### Introduction### Introduction
Foreign keys are a crucial concept in database normalization. They enforce referential integrity and prevent data inconsistencies in related tables.

### Anatomy of a Foreign Key
A foreign key is a column in a child table that references a column in a parent table.

**Syntax**:
```
ALTER TABLE child_table ADD FOREIGN KEY (foreign_key_column) REFERENCES parent_table (referenced_column)
```

**Example**:
In the given text, the `orders_id` column in the `relationship` table is a foreign key that references the `id` column in the `orders` table. This establishes a master-child relationship between the two tables.

### Benefits of Foreign Keys
* **Referential Integrity**: Foreign keys ensure that data in the child table is consistent with the parent table.
* **Data Integrity**: They prevent data loss when records are deleted from the parent table.
* **Data Validation**: Foreign keys act as data validators, ensuring that only valid values are entered in the child table.

### Creating Foreign Keys### Creating Foreign Keys
In the second normal form, foreign keys are created by identifying the primary key of the parent table and using it to reference the appropriate column in the child table.

**Example**:
In the given text, the `order_id` column (primary key) in the `orders` table is referenced by the `orders_id` column (foreign key) in the `relationship` table.

### Conclusion
Foreign keys provide a robust mechanism for maintaining data consistency and integrity in relational databases. By creating foreign keys, we can ensure that data in related tables is valid and accurate.### Understanding Data Normalization: Foreign Keys and Relationships

**Normalization:** A technique to organize data into tables such that each table contains a specific set of related data and each row is unique.

**Foreign Keys:** Fields in a table that reference a primary key in another table, establishing a relationship between the tables.

**Example:****Example:**

Create a foreign key called `order_id` in the `order_details` table that references the `order_id` primary key in the `orders` table. This establishes a link between orders and their details.

### Levels of Normalization

**First Normal Form (1NF):**
- No duplicate rows
- Each column contains atomic data (cannot be broken down further)

**Second Normal Form (2NF):**
- In 1NF
- No partial dependencies on the primary key
- Example: In the `order_details` table, each row is dependent on the `order_id` primary key for all its columns

**Third Normal Form (3NF):**
- In 2NF
- No transitive dependencies
- Example: In the `customers` table, the `customer_id` primary key is not dependent on any other column, so there are no transitive dependencies

### Insertion Anomaly

**Insertion Anomaly:**
- Occurs when it's impossible to add new data to a table without violating data integrity.

**Example:****Example:**
- In a table where `product_name` and `product_code` are combined into a single field, it would be impossible to add a new product with the same name but a different code**Understanding Denormalization in Databases**

**Definition:**
Denormalization refers to the practice of storing duplicate data in multiple tables to improve query performance. Unlike normalized databases, which prioritize data integrity, denormalized databases sacrifice data coherence for efficiency.

**Rationale:**
Consider a customer table containing information about both customers and their orders. If customers make multiple purchases, their information (e.g., name, address) must be repeated for each order. This duplication can slow down queries as the database must join multiple tables to retrieve customer-specific data.

**Example:**

| CustomerID | Name | Address | OrderID | Product | Price | Date |
|---|---|---|---|---|---|---|
| 1 | Land of Toys | 123 Main St | 100 | Toy A | $10 | 2023-01-01 || 1 | Land of Toys | 123 Main St | 101 | Toy B | $20 | 2023-01-10 |
| 1 | Land of Toys | 123 Main St | 102 | Toy C | $30 | 2023-02-01 |

**Advantages:**

* **Improved Query Performance:** By storing customer information in the order table, queries only need to access a single table, significantly reducing query time.

**Disadvantages:**

* **Data Redundancy:** Duplicate data increases storage space requirements and can lead to data inconsistencies.
* **Data Integrity Compromised:** Denormalization violates the principle of data normalization, potentially resulting in data anomalies.

**Appropriate Use Cases:**

Denormalization can be beneficial in situations where:

* Queries frequently retrieve data from multiple related tables.
* Data integrity is less critical than query performance.
* The denormalized data does not easily change.**Markdown Notes on Database Normalization**

**Introduction****Introduction**
- Database normalization refers to the process of organizing data into a structured format to avoid data redundancy and anomalies.

**Denormalization**
- Denormalization means storing data in a non-normalized form, where some data may be repeated to improve performance.
- This approach can result in data redundancy, which can lead to insertion anomalies.

**Normalization**
- Normalization involves breaking down data into smaller, independent tables based on specific rules (normal forms).
- The goal is to eliminate data redundancy and ensure data integrity.

**Third Normal Form (3NF)**
- **Definition:** A database is in 3NF if it meets the following conditions:
  - It is in 2NF.
  - Every non-key attribute is non-transitively dependent on the primary key.

**Data Redundancy in Denormalization vs. Normalization**
- **Denormalized Data:** Some data may be repeated in multiple tables.
  - Inserting a new row can result in duplication of data.- Inserting a new row can result in duplication of data.
- **Normalized Data:** Data is distributed across multiple tables to eliminate redundancy.
  - Inserting a new row only requires adding data to a single table.

**Benefits of Normalization**
- Reduced data redundancy
- Increased data integrity
- Improved data consistency
- Enhanced data flexibility and scalability

**Example**
Consider the customer information and orders in a database:

**Denormalized Data:**
```
CREATE TABLE Customers_Orders (
  Customer_ID INT PRIMARY KEY,
  Customer_Name VARCHAR(100),
  Order_Date DATE,
  Order_ID INT,
  Product_Name VARCHAR(100),
  Quantity INT
);
```

**Normalized Data (3NF):**
```
CREATE TABLE Customers (
  Customer_ID INT PRIMARY KEY,
  Customer_Name VARCHAR(100)
);

CREATE TABLE Orders (
  Order_ID INT PRIMARY KEY,
  Customer_ID INT REFERENCES Customers(Customer_ID),
  Order_Date DATE
);

CREATE TABLE Products (
  Product_ID INT PRIMARY KEY,
  Product_Name VARCHAR(100)
);

CREATE TABLE Order_Details (Product_Name VARCHAR(100)
);

CREATE TABLE Order_Details (
  Order_ID INT REFERENCES Orders(Order_ID),
  Product_ID INT REFERENCES Products(Product_ID),
  Quantity INT
);
```

In the normalized database, each table represents a specific entity (Customers, Orders, Products, Order_Details) and contains only the data related to that entity. This eliminates data redundancy and ensures that any changes to customer information or orders are reflected in a single place, maintaining data integrity.**Insertion Anomaly in Database Normalization**

**Problem Statement:**
When data is duplicated in multiple tables of a database, updating or inserting data in one table may require changes in other tables, leading to data inconsistency and errors. This is known as insertion anomaly.

**Normalized Database Structure:**
To eliminate insertion anomaly, data should be normalized into separate tables. Each table represents a specific entity or aspect of the data.

**Example of Insertion Anomaly:**

**Denormalized Table:****Example of Insertion Anomaly:**

**Denormalized Table:**

| Order ID | Customer ID | Product Name | Product Price |
|---|---|---|---|
| 1 | 1001 | iPhone | 1000 |
| 2 | 1002 | MacBook | 1500 |

**Problem:** If a new product is introduced, such as a cruise ship, the entire table needs to be updated to include the product's information.

**Normalized Table Structure:**

| **Customer Table** | **Product Table** | **Order Table** |
|---|---|---|
| Customer ID | Name | Address | | Product ID | Name | Price | | Order ID | Customer ID | Product ID | Quantity |

**Benefits of Normalization:**

* Eliminates data redundancy
* Ensures data consistency
* Simplifies data updates and insertions
* Improves database efficiency

**Code Example for Inserting Data into Normalized Tables:**

**Inserting New Product:**

```sql
INSERT INTO Product (Name, Price)
VALUES ('Cruise Ship', 5000);
```

**Inserting New Order:**

```sql
INSERT INTO Order (Customer ID, Product ID, Quantity)```sql
INSERT INTO Order (Customer ID, Product ID, Quantity)
VALUES (1001, (SELECT Product ID FROM Product WHERE Name = 'Cruise Ship'), 1);
```

**Additional Notes:**

* Normalization level affects database performance and flexibility.
* Denormalization may be appropriate in certain scenarios for improved query performance.
* Data modeling techniques, such as entity-relationship diagrams, help design efficient and normalized databases.## Avoiding Insertion Anomalies in Database Normalization

### Introduction
Database normalization aims to eliminate data redundancy and ensure data integrity. One issue that can arise during data insertion is the presence of insertion anomalies, where missing or incomplete data violates the integrity of the database.

### Problem in a Denormalized Database### Problem in a Denormalized Database
In a denormalized database, all information is stored in a single table. When a new product is added that has not been purchased yet, several fields (such as customer information) will have null values. This violates data integrity and creates missing data.

### Solution in a Normalized Database
In a normalized database, data is separated into multiple tables based on logical relationships. When adding a new product, only the necessary information (such as name and description) is entered into the product table. Other related information, such as order and customer details, are stored in separate tables and linked as needed.

### Step-by-Step Explanation
1. **Create separate tables:** Organize data into logical entities, such as a table for products, orders, and customers.
2. **Define relationships:** Establish relationships between tables using primary and foreign keys to link related records.3. **Insert product information:** Add a new product to the product table, including only the essential details.
4. **Link to other tables:** When an order is placed or a customer is registered, create records in the respective tables and link them to the product table using the foreign key.

### Example

**Denormalized Table:**

| Product ID | Product Name | Order ID | Customer ID |
|---|---|---|---|
| P001 | Widget X | NULL | NULL |

**Normalized Tables:**

**Product Table:**

| Product ID | Product Name |
|---|---|
| P001 | Widget X |

**Order Table:**

| Order ID | Product ID | Customer ID |
|---|---|---|
| O001 | P001 | C001 |

**Customer Table:**

| Customer ID | Name | Address |
|---|---|---|
| C001 | John Doe | 123 Main St. |

### Benefits of Normalization
- **Eliminates missing data:** Data is only stored where it is logically required, reducing null values and ensuring data integrity.
- **Enhances data consistency:** Data updates are performed only in the relevant table, preventing inconsistencies.- **Improves query efficiency:** Normalization simplifies data retrieval by separating data into logical tables, reducing the need for complex queries.**Topic: Database Normalization Anomalies**

**Core Concepts:**

* **Normalization:** A process of organizing data in a database to reduce data redundancy and inconsistencies.
* **Third Normal Form (3NF):** A level of data normalization where each table only contains data related to its primary key.
* **Insertion Anomaly:** An anomaly that occurs when inserting new data into a denormalized database, causing changes to unrelated data.
* **Deletion Anomaly:** An anomaly that occurs when deleting data from a denormalized database, causing loss of related data.

**Explanation:**

**Third Normal Form (3NF) and Insertion Anomaly:**

* In a 3NF database, each table is designed around a specific entity (e.g., products, customers, orders). This prevents insertion anomalies.* In a denormalized database, multiple tables may contain duplicate data. Inserting new data into one table can require changes to other tables, violating the principle of data independence.
* For example, in the given dataset, adding a new product only requires adding a record to the "products" table, maintaining referential integrity without affecting other tables.

**Deletion Anomaly:**

* In a denormalized database, data can be distributed across multiple tables. Deleting data from one table can unintentionally delete related data from other tables.
* For example, if the order number 10103 were deleted from the given denormalized database, the order details related to that order would also be lost.

**Example Code (SQL):**

**Denormalized Table:**

```sql
CREATE TABLE Orders (
  order_id INT PRIMARY KEY,
  product_id INT,
  product_name VARCHAR(50),
  customer_id INT,
  customer_name VARCHAR(50)
);

-- Insert a new order
INSERT INTO Orders (order_id, product_id, product_name, customer_id, customer_name)VALUES (10103, 101, 'Product X', 201, 'Customer A');
```

**3NF Table Structure:**

```sql
-- Products table
CREATE TABLE Products (
  product_id INT PRIMARY KEY,
  product_name VARCHAR(50)
);

-- Orders table
CREATE TABLE Orders (
  order_id INT PRIMARY KEY,
  product_id INT,
  customer_id INT,
  FOREIGN KEY (product_id) REFERENCES Products(product_id),
  FOREIGN KEY (customer_id) REFERENCES Customers(customer_id)
);

-- Insert a new order
INSERT INTO Orders (order_id, product_id, customer_id)
VALUES (10103, 101, 201);
```

**Key Takeaways:**

* Normalizing a database eliminates insertion and deletion anomalies, ensuring data integrity and consistency.
* 3NF is a common level of normalization that strikes a balance between data efficiency and flexibility.
* Understanding normalization anomalies is essential for designing effective and reliable databases.## Data Integrity Considerations in Denormalized Datasets

### Concept: Denormalization### Concept: Denormalization

- Denormalization is a data optimization technique where redundant data is introduced to improve query performance.
- Denormalized datasets have faster queries, but may have data integrity issues.

### Data Integrity Concerns

When removing records from a denormalized dataset, consider the following data integrity risks:

- **Loss of Order Information:** Deleting an order record removes order details, such as order date and shipping address.
- **Loss of Product Information:** Orders may contain unique product information that is not present in other records. Deleting the order can result in product data loss.
- **Loss of Customer Information:** Customers may only be present in a single order record. Deleting the order may result in customer data loss.

### Best Practice: Selective Removal

To maintain data integrity, follow these best practices when removing records from denormalized datasets:- **Identify Critical Information:** Determine which information is essential to retain (e.g., customer, product).
- **Remove Redundant Data:** Only remove data that is available in multiple records.

### Example

Consider the following record in a denormalized dataset:

```
ID | OrderID | ProductID | CustomerID | ProductName
1   | 10       | 15         | 20        | Classic Cards
```

- **Critical Information:** CustomerID (customer information)
- **Redundant Information:** OrderID (order information), ProductID (product information)

If the order with ID 10 is removed, the following information would be lost:

- Order details (OrderID)
- Product information (ProductID, ProductName), since Classic Cards is only mentioned in this record

Therefore, it would be unwise to remove this record as it contains critical customer information.**Understanding Database Anomalies**

**Deletion Anomaly:**

* Occurs when deleting a record from a denormalized table results in the loss of related data in other tables.**Normalized Table vs. Denormalized Table:**

* **Normalized Table:** Tables are split into smaller tables based on data dependencies, reducing redundancy and anomalies.
* **Denormalized Table:** Tables contain redundant data to improve performance, but this can lead to anomalies.

**Example of Deletion Anomaly in a Denormalized Table:**

* You have a table with three columns: "Product," "Customer," and "Orders."
* When you delete an order, the corresponding entries in the "Product" and "Customer" tables are also deleted.
* This can result in loss of data, such as the product's sales history or the customer's order information.

**Example of Deletion Anomaly Avoidance in a Normalized Table:**

* You have separate "Product," "Customer," and "Orders" tables.
* Deleting an order only deletes the corresponding entry in the "Orders" table, leaving the "Product" and "Customer" data intact.

**Updation Anomaly:**

* Occurs when updating a record in a denormalized table results in inconsistent data in other tables.**Example of Updation Anomaly in a Denormalized Table:**

* You have a denormalized table with columns "Product," "Price," and "Description."
* When you update the price of a product, you need to manually update the price in all the related tables.
* This can lead to inconsistencies, such as having different prices for the same product in different tables.

**Example of Updation Anomaly Avoidance in a Normalized Table:**

* You have separate "Product" and "Price" tables.
* Updating the price of a product only updates the corresponding entry in the "Price" table, ensuring consistency across the database.## Understanding Update Anomaly in Database Systems

### Core Concept

Update anomaly refers to the issue that occurs when a database update involves modifying multiple records to reflect a single change in underlying data. This can lead to data inconsistencies and operational inefficiencies.

### Causes of Update Anomaly### Causes of Update Anomaly

* **Duplication of Data:** When the same data is stored in multiple tables or records, updating one instance may require updating others to ensure data integrity.
* **Scattered Data:** When related data is distributed across multiple tables, updating one part of the data may require updating several other tables.

### Consequences of Update Anomaly

* **Data Inconsistencies:** If updates are not properly coordinated, different records may contain conflicting data, resulting in inaccurate information.
* **Inefficiency:** Updating multiple records unnecessarily can slow down database performance and waste resources.

### Solving Update Anomaly

**Normalization:**

* Refactor database design to eliminate data redundancy and ensure that each piece of information is stored only once.
* Divide tables into more specific and focused entities, reducing the need for multiple updates.

**Data Integrity Constraints:****Data Integrity Constraints:**

* Define primary keys, foreign keys, and other constraints to enforce data relationships and prevent inconsistent updates.
* Ensure that updates are made only to the appropriate tables and records.

**Centralized Updates:**

* Create a single table or point of control where all related data is updated.
* Avoid direct updates to individual records, instead use a centralized mechanism to handle updates.

**Example:**

```sql
-- Original Design with Update Anomaly
CREATE TABLE Customers (
  customer_id INT,
  purchase_id INT,
  motorcycle_id INT,
  motorcycle_price INT,
  PRIMARY KEY (customer_id)
);

-- Scattered Data
CREATE TABLE Motorcycles (
  motorcycle_id INT,
  motorcycle_price INT,
  PRIMARY KEY (motorcycle_id)
);

-- Update Anomaly Example
UPDATE Motorcycles SET motorcycle_price = 250 WHERE motorcycle_id = 1;

-- This update requires updating all records in the Customers table where motorcycle_id = 1
UPDATE Customers SET motorcycle_price = 250 WHERE motorcycle_id = 1;```

```sql
-- Normalized Design to Solve Update Anomaly
CREATE TABLE Customers (
  customer_id INT,
  PRIMARY KEY (customer_id)
);

CREATE TABLE Purchases (
  purchase_id INT,
  customer_id INT,
  motorcycle_id INT,
  purchase_date DATE,
  PRIMARY KEY (purchase_id)
  FOREIGN KEY (customer_id) REFERENCES Customers(customer_id),
  FOREIGN KEY (motorcycle_id) REFERENCES Motorcycles(motorcycle_id)
);

CREATE TABLE Motorcycles (
  motorcycle_id INT,
  motorcycle_price INT,
  PRIMARY KEY (motorcycle_id)
);

-- Centralized Update
UPDATE Motorcycles SET motorcycle_price = 250 WHERE motorcycle_id = 1;

-- Only the Motorcycles table is updated, eliminating the need for redundant updates in the Purchases or Customers tables.
```**Normalization in Databases**

**Concept:**

Normalization is a process of organizing data in a database to reduce data redundancy and improve data integrity. It involves dividing data into multiple tables based on their relationships and dependencies.

**Advantages of a Normalized Database:****Advantages of a Normalized Database:**

* **Reduces data redundancy:** Each piece of data is stored only once, avoiding duplication.
* **Improves data integrity:** Relationships between data are enforced through foreign key constraints, reducing the risk of data inconsistencies.
* **Facilitates data updates:** Updating a normalized database is more efficient as only the affected record needs to be changed, unlike in a denormalized database where multiple records may require update.

**Example:**

Consider a table `orders` containing the following data:

| Order ID | Product ID | Price |
|---|---|---|
| 1 | 1 | 10 |
| 2 | 1 | 10 |
| 3 | 2 | 20 |

**Denormalized Dataset:**

In a denormalized dataset, the `products` table would be merged with the `orders` table, resulting in:

| Order ID | Product ID | Price | Product Name |
|---|---|---|---|
| 1 | 1 | 10 | Product A |
| 2 | 1 | 10 | Product A |
| 3 | 2 | 20 | Product B |

**Normalized Dataset:**| 3 | 2 | 20 | Product B |

**Normalized Dataset:**

In a normalized dataset, there would be separate tables for `orders` and `products`:

`orders` table:

| Order ID | Product ID | Price |
|---|---|---|
| 1 | 1 | 10 |
| 2 | 1 | 10 |
| 3 | 2 | 20 |

`products` table:

| Product ID | Product Name |
|---|---|
| 1 | Product A |
| 2 | Product B |

**Advantages of Using a Normalized Database for Updates:**

In the denormalized dataset example, if the price of Product A needs to be changed, all three records must be updated. In a normalized dataset, only the corresponding record in the `products` table needs to be updated, making it much more efficient.