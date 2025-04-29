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

4) EmployeeDetails Table with Constraints
a) Create Department and EmployeeDetails tables with constraints:
sql
Copy
Edit
-- First, create Department table
CREATE TABLE Department (
    DepartmentID INT PRIMARY KEY,
    DepartmentName VARCHAR(100)
);

-- Sample department data
INSERT INTO Department VALUES 
(1, 'HR'),
(2, 'Finance'),
(3, 'Engineering');

-- Now create EmployeeDetails table
CREATE TABLE EmployeeDetails (
    EmployeeID INT PRIMARY KEY,
    EmployeeName VARCHAR(100),
    DepartmentID INT,
    Salary DECIMAL(10,2),
    FOREIGN KEY (DepartmentID) REFERENCES Department(DepartmentID)
);
b) Insert a valid employee, then attempt invalid foreign key:
sql
Copy
Edit
-- Valid insert
INSERT INTO EmployeeDetails VALUES 
(101, 'Ravi Kumar', 1, 55000.00);

-- Invalid insert: DepartmentID = 99 does not exist (will cause error)
INSERT INTO EmployeeDetails VALUES 
(102, 'Sunita Rao', 99, 48000.00);
c) Attempt to insert duplicate EmployeeID:
sql
Copy
Edit
-- Duplicate primary key (will result in error)
INSERT INTO EmployeeDetails VALUES 
(101, 'Ajay Mehta', 2, 60000.00);
d) Modify Salary column to add UNIQUE constraint and test it:
sql
Copy
Edit
-- Add UNIQUE constraint
ALTER TABLE EmployeeDetails
ADD CONSTRAINT unique_salary UNIQUE (Salary);

-- Insert with same salary as existing employee (will cause error if duplicate)
INSERT INTO EmployeeDetails VALUES 
(103, 'Nisha Singh', 3, 55000.00);
e) Delete employee and ensure referential integrity:
sql
Copy
Edit
DELETE FROM EmployeeDetails WHERE EmployeeID = 101;

-- Verify deletion
SELECT * FROM EmployeeDetails;
Technology Insight:
Tool: PostgreSQL

Key Features:

Advanced open-source RDBMS with strong SQL compliance

Supports complex queries, window functions, and CTEs

Built-in support for JSON, GIS (PostGIS), and full-text search

Extensive constraint system (check, unique, foreign key, exclusion)

ACID compliant and supports MVCC (multi-version concurrency control)

Industry Use: Used in financial services, e-commerce, government, and analytics-heavy environments due to its reliability, data integrity, and performance.

Q5

5) Create an Employee Table with Various Columns
a) Create the Employee table:
sql
Copy
Edit
CREATE TABLE Employee (
    EmployeeID INT PRIMARY KEY,
    Name VARCHAR(100) NOT NULL,
    Salary DECIMAL(10,2),
    JoiningDate DATE,
    ActiveStatus BOOLEAN
);
b) Insert five sample employee records:
sql
Copy
Edit
INSERT INTO Employee VALUES 
(1, 'Amit Sharma', 60000.00, '2022-12-15', TRUE),
(2, 'Neha Gupta', 50000.00, '2023-03-10', TRUE),
(3, 'Rajeev Bansal', 45000.00, '2024-01-05', FALSE),
(4, 'Pooja Mehta', 70000.00, '2021-11-01', TRUE),
(5, 'Rohit Kumar', 55000.00, '2023-07-20', TRUE);
c) Find employees who joined before January 1, 2023:
sql
Copy
Edit
SELECT * FROM Employee
WHERE JoiningDate < '2023-01-01';
d) Update Amit Sharma’s salary by 10% and show updated record:
sql
Copy
Edit
UPDATE Employee 
SET Salary = Salary * 1.10
WHERE Name = 'Amit Sharma';

SELECT * FROM Employee
WHERE Name = 'Amit Sharma';
e) Retrieve all active employees:
sql
Copy
Edit
SELECT * FROM Employee
WHERE ActiveStatus = TRUE;
Technology Insight:
Tool: Amazon RDS (Relational Database Service)

Key Features:

Fully managed service for SQL databases (MySQL, PostgreSQL, SQL Server, Oracle, etc.)

Automated backups, patching, and failover

Scalability with read replicas

Integrated monitoring and security features (IAM, VPC)

Multi-AZ deployments for high availability

Industry Use: Popular in cloud-native applications and SaaS platforms for reducing DBA overhead while ensuring high availability, security, and performance of relational databases.


Q6

6) Sales Table with Aggregate Functions
a) Create Sales table:
sql
Copy
Edit
CREATE TABLE Sales (
    SaleID INT PRIMARY KEY,
    ProductID INT,
    ProductName VARCHAR(100),
    Quantity INT,
    Discount DECIMAL(5,2),
    SaleAmount DECIMAL(10,2),
    SaleDate DATE
);
Insert sample data:
sql
Copy
Edit
INSERT INTO Sales VALUES
(1, 201, 'Laptop', 2, 5.00, 140000.00, '2025-02-05'),
(2, 202, 'Mouse', 5, 2.00, 2500.00, '2025-02-10'),
(3, 203, 'Keyboard', 3, 1.50, 3600.00, '2025-02-15'),
(4, 204, 'Monitor', 1, 10.00, 15000.00, '2025-01-20'),
(5, 201, 'Laptop', 1, 5.00, 70000.00, '2025-02-25'),
(6, 205, 'Webcam', 2, 3.00, 6000.00, '2025-02-12'),
(7, 202, 'Mouse', 4, 2.00, 2000.00, '2025-03-01');
a) Total sales in February 2025:
sql
Copy
Edit
SELECT SUM(SaleAmount) AS TotalSalesFeb2025
FROM Sales
WHERE MONTH(SaleDate) = 2 AND YEAR(SaleDate) = 2025;
b) Average billing amount:
sql
Copy
Edit
SELECT AVG(SaleAmount) AS AverageBilling
FROM Sales;
c) Minimum quantity sold in any transaction:
sql
Copy
Edit
SELECT MIN(Quantity) AS MinQuantity
FROM Sales;
d) Maximum discount applied:
sql
Copy
Edit
SELECT MAX(Discount) AS MaxDiscount
FROM Sales;
e) Count of 'Laptop' transactions:
sql
Copy
Edit
SELECT COUNT(*) AS LaptopSalesCount
FROM Sales
WHERE ProductName = 'Laptop';
Technology Insight:
Tool: Google BigQuery

Key Features:

Serverless, highly scalable data warehouse optimized for analytics

Supports standard SQL, real-time analytics, and federated queries across data lakes

Integrates with Google Cloud Storage, Looker Studio, and ML tools

Pay-per-query pricing model

Partitioning, clustering, and automatic optimization for performance

Industry Use: BigQuery is used for large-scale data analytics, marketing intelligence, fraud detection, and business intelligence due to its speed and ability to analyze petabyte-scale data in seconds.


Q7

7) Employees Table with Constraints
a) Create the Employees table with constraints:
sql
Copy
Edit
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    Name VARCHAR(100) NOT NULL,
    Email VARCHAR(100) UNIQUE,
    Salary DECIMAL(10,2) CHECK (Salary > 10000),
    Status VARCHAR(20) DEFAULT 'Active'
);
b) Try inserting a record without Name (NOT NULL violation):
sql
Copy
Edit
-- This will fail due to NOT NULL constraint
INSERT INTO Employees (EmployeeID, Email, Salary)
VALUES (1, 'test@example.com', 15000.00);
c) Insert a record without specifying Status (check DEFAULT):
sql
Copy
Edit
INSERT INTO Employees (EmployeeID, Name, Email, Salary)
VALUES (2, 'Nitin Verma', 'nitin@example.com', 20000.00);

-- Check the default value applied
SELECT * FROM Employees WHERE EmployeeID = 2;
d) Insert a record with Salary < 10000 (CHECK constraint):
sql
Copy
Edit
-- This will fail due to CHECK constraint
INSERT INTO Employees (EmployeeID, Name, Email, Salary)
VALUES (3, 'Simran Kaur', 'simran@example.com', 8000.00);
e) Insert two records with same Email ID (UNIQUE violation):
sql
Copy
Edit
-- First insert (valid)
INSERT INTO Employees (EmployeeID, Name, Email, Salary)
VALUES (4, 'Rahul Joshi', 'rahul@example.com', 30000.00);

-- Second insert with same email (will cause UNIQUE constraint violation)
INSERT INTO Employees (EmployeeID, Name, Email, Salary)
VALUES (5, 'Anjali Rao', 'rahul@example.com', 32000.00);
Technology Insight:
Tool: Oracle Database 23c

Key Features:

Enhanced JSON support with JSON Relational Duality

SQL-based graph queries, AI vector search

Advanced security (Data Redaction, Transparent Data Encryption)

Multitenant architecture and automatic indexing

Designed for hybrid cloud and on-premises deployments

Industry Use: Oracle is favored in enterprise environments for high-performance transaction processing, complex security requirements, and robust data integrity management.

Q8

8) DDL and DML Commands – Library / Books Table
a) Create a Library database and Books table:
sql
Copy
Edit
-- In some systems, databases are created at a higher level:
-- CREATE DATABASE Library;

-- Use the database (varies by RDBMS)
-- USE Library;

CREATE TABLE Books (
    BookID INT PRIMARY KEY,
    Title VARCHAR(200),
    Author VARCHAR(100),
    Genre VARCHAR(50),
    Price DECIMAL(10,2)
);
b) Insert five sample records and verify:
sql
Copy
Edit
INSERT INTO Books VALUES
(1, 'Clean Code', 'Robert C. Martin', 'Programming', 550.00),
(2, 'Deep Work', 'Cal Newport', 'Productivity', 400.00),
(3, 'Sapiens', 'Yuval Noah Harari', 'History', 600.00),
(4, 'The Pragmatic Programmer', 'Andrew Hunt', 'Programming', 500.00),
(5, 'AI Superpowers', 'Kai-Fu Lee', 'Technology', 450.00);

-- Display all records
SELECT * FROM Books;
c) Add PublicationYear column using ALTER TABLE:
sql
Copy
Edit
ALTER TABLE Books
ADD PublicationYear INT;

-- Optional: Update sample data
UPDATE Books SET PublicationYear = 2008 WHERE BookID = 1;
UPDATE Books SET PublicationYear = 2016 WHERE BookID = 2;
UPDATE Books SET PublicationYear = 2011 WHERE BookID = 3;
UPDATE Books SET PublicationYear = 1999 WHERE BookID = 4;
UPDATE Books SET PublicationYear = 2018 WHERE BookID = 5;
d) Update price of all books published before 2020 by 10%:
sql
Copy
Edit
UPDATE Books
SET Price = Price * 1.10
WHERE PublicationYear < 2020;
e) Delete books where genre is ‘Outdated Technology’ and validate:
sql
Copy
Edit
-- First, insert a sample book in that genre for testing
INSERT INTO Books VALUES (6, 'COBOL Programming', 'Jane Doe', 'Outdated Technology', 300.00, 1980);

-- Now delete
DELETE FROM Books
WHERE Genre = 'Outdated Technology';

-- Validate deletion
SELECT * FROM Books;
Technology Insight:
Tool: CockroachDB

Key Features:

Distributed SQL database designed for high availability and resilience

Strong consistency with support for ACID transactions

Scales horizontally with automatic replication and fault tolerance

PostgreSQL-compatible SQL interface

Ideal for global applications due to geo-partitioning support

Industry Use: Used in fintech, SaaS, and global apps where uptime, data consistency, and scalability are critical, often replacing legacy RDBMS with cloud-native architecture.

Q9

9) DDL and DML Commands (Books Table)
a) Create Books table:
sql
Copy
Edit
CREATE TABLE Books (
    BookID INT PRIMARY KEY,
    Title VARCHAR(200),
    Author VARCHAR(100),
    Price DECIMAL(10,2),
    StockAvailable INT
);
b) Insert 5 book records:
sql
Copy
Edit
INSERT INTO Books VALUES
(1, 'Atomic Habits', 'James Clear', 450.00, 10),
(2, 'Zero to One', 'Peter Thiel', 500.00, 5),
(3, 'The Lean Startup', 'Eric Ries', 600.00, 0),
(4, 'Digital Minimalism', 'Cal Newport', 350.00, 7),
(5, 'Start With Why', 'Simon Sinek', 400.00, 0);
c) Modify table to add a new column Genre:
sql
Copy
Edit
ALTER TABLE Books
ADD Genre VARCHAR(100);
d) Increase the price of all books by ₹50:
sql
Copy
Edit
UPDATE Books
SET Price = Price + 50;
e) Delete all records where StockAvailable is 0:
sql
Copy
Edit
DELETE FROM Books
WHERE StockAvailable = 0;

-- Verify remaining records
SELECT * FROM Books;
Technology Insight:
Tool: Firebase Realtime Database

Key Features:

NoSQL cloud database that syncs data in real-time across all clients

Designed for mobile and web apps with offline capabilities

JSON-based, highly responsive with event-driven updates

Integrates easily with Firebase Authentication and Firebase Cloud Functions

Minimal setup for rapid prototyping and deployment

Industry Use: Commonly used in mobile applications, chat systems, real-time collaboration tools, and MVPs due to its ease of integration and live-sync capabilities.

Q10



