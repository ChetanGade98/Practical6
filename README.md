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







