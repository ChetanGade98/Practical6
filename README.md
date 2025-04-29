Practical 6  

1) Sales Table and Aggregate Functions
a) Create table:
sql
Copy
Edit
CREATE TABLE Sales (
    SaleID INT PRIMARY KEY,
    ProductID INT,
    Quantity INT,
    SaleAmount DECIMAL(10,2),
    SaleDate DATE
);
b) Insert sample data:
sql
Copy
Edit
INSERT INTO Sales VALUES 
(1, 101, 2, 200.00, '2025-02-01'),
(2, 102, 1, 150.00, '2025-02-02'),
(3, 103, 5, 500.00, '2025-02-03'),
(4, 101, 3, 300.00, '2025-03-01'),
(5, 104, 2, 250.00, '2025-03-05'),
(6, 105, 1, 100.00, '2025-01-15'),
(7, 106, 4, 400.00, '2025-02-10'),
(8, 107, 2, 220.00, '2025-03-12'),
(9, 102, 3, 450.00, '2025-01-20'),
(10, 108, 1, 120.00, '2025-02-20');
c) Total revenue:
sql
Copy
Edit
SELECT SUM(SaleAmount) AS TotalRevenue FROM Sales;
d) Product with highest sale amount:
sql
Copy
Edit
SELECT * FROM Sales WHERE SaleAmount = (SELECT MAX(SaleAmount) FROM Sales);
e) Average sale amount:
sql
Copy
Edit
SELECT AVG(SaleAmount) AS AvgSaleAmount FROM Sales;
Technology Insight:
Tool: Snowflake

Key Features:

Cloud-native and serverless data warehouse

Auto-scaling, auto-suspend features for efficient cost usage

Supports structured and semi-structured data (JSON, Avro, Parquet)

Zero-copy cloning for rapid environment setup

Time travel and fail-safe features for data recovery

Industry Use: Used for real-time analytics, big data warehousing, and ELT pipelines due to performance, scalability, and ease of integration with BI tools like Tableau and Power BI.


Q2)
2) Use DDL and DML Commands
a) Create Products table:
sql
Copy
Edit
CREATE TABLE Products (
    ProductID INT PRIMARY KEY,
    ProductName VARCHAR(100),
    Price DECIMAL(10,2),
    StockQuantity INT
);
b) Insert five product records & display:
sql
Copy
Edit
INSERT INTO Products VALUES 
(1, 'Laptop', 75000.00, 10),
(2, 'Mouse', 500.00, 100),
(3, 'Keyboard', 1200.00, 50),
(4, 'Monitor', 15000.00, 25),
(5, 'Printer', 9000.00, 15);

SELECT * FROM Products;
c) Update price of ProductID = 3 and check:
sql
Copy
Edit
UPDATE Products SET Price = 1300.00 WHERE ProductID = 3;

SELECT * FROM Products WHERE ProductID = 3;
d) Delete a product and verify:
sql
Copy
Edit
DELETE FROM Products WHERE ProductID = 5;

SELECT * FROM Products;
e) Alter table to add Discount column with default value:
sql
Copy
Edit
ALTER TABLE Products ADD Discount DECIMAL(4,2) DEFAULT 5.00;

-- Check result
SELECT * FROM Products;
Technology Insight:
Tool: Microsoft Azure SQL Database

Key Features:

Fully managed cloud-based relational database

Auto-patching, high availability (99.99% uptime SLA)

AI-powered performance tuning

Built-in threat detection and security controls

Seamless integration with Azure services (e.g., Power BI, Data Factory)

Industry Use: Used for scalable web and enterprise applications, real-time analytics, and multi-tenant SaaS platforms due to its robustness, elasticity, and security.

Q3  

3) Customer Table with Integrity Constraints
a) Create Customers table with constraints:
sql
Copy
Edit
CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY,
    Name VARCHAR(100),
    Email VARCHAR(100) UNIQUE,
    Age INT CHECK (Age > 18),
    Country VARCHAR(50) DEFAULT 'India'
);
b) Insert valid customer (without specifying Country):
sql
Copy
Edit
INSERT INTO Customers (CustomerID, Name, Email, Age) 
VALUES (1, 'Raj Verma', 'raj.verma@example.com', 28);

-- Verify default country
SELECT * FROM Customers WHERE CustomerID = 1;
c) Attempt to insert customer with age 16 (CHECK constraint violation):
sql
Copy
Edit
-- This will result in an error
INSERT INTO Customers (CustomerID, Name, Email, Age)
VALUES (2, 'Ankit Sharma', 'ankit.sharma@example.com', 16);
d) Try inserting two customers with same Email ID (UNIQUE constraint violation):
sql
Copy
Edit
-- First insert (valid)
INSERT INTO Customers (CustomerID, Name, Email, Age)
VALUES (3, 'Meena Jain', 'meena.jain@example.com', 30);

-- Duplicate email (will result in error)
INSERT INTO Customers (CustomerID, Name, Email, Age)
VALUES (4, 'Asha Rani', 'meena.jain@example.com', 35);
e) Retrieve customers older than 25 and not from 'India':
sql
Copy
Edit
SELECT * FROM Customers 
WHERE Age > 25 AND Country <> 'India';
Technology Insight:
Tool: MongoDB (with schema validation using Mongoose or native JSON Schema)

Key Features:

NoSQL document database, stores data in JSON-like BSON format

Highly scalable, supports sharding and replication

Allows flexible schema, but schema validation is supported

Aggregation pipeline for advanced analytics

Powerful indexing and geospatial query capabilities

Industry Use: Widely used for modern web applications, content management systems, IoT platforms, and real-time analytics where flexible and dynamic data models are needed.

Q4






