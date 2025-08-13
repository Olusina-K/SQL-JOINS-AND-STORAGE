#  Sales & Product Database (SQL)

This repository contains SQL scripts for creating and managing a simple **Sales & Product** database in Microsoft SQL Server.  
It includes table creation, sample data insertion, and SQL queries for basic reporting and stored procedures.

---

##  Project Structure

- **`SQL LOGIC.sql`** – Main SQL script containing:
  - Database table creation
  - Sample data insertion
  - Queries for reporting
  - Stored procedures

---

##  Features

1. **Create Tables**
   - `PRODUCT` – Stores product details like name, category, and price.
   - `SALESS` – Stores sales transactions linked to products.

2. **Insert Sample Data**
   - Preloaded products (Laptop, Smartphone, etc.)
   - Sample sales records with quantities and prices.

3. **SQL Queries**
   - Get total sales amount for each product.
   - Display sales on a specific date (`2024-01-02`).
   - Join product details with sales records.
   
4. **Stored Procedures**
   - Insert two rows into the `PRODUCT` table in one execution.
   - Retrieve booking details by customer ID (if extended).

---

##  Requirements

- **Microsoft SQL Server** (2017 or later recommended)
- **SQL Server Management Studio (SSMS)**

---

##  How to Run

1. Open **SQL Server Management Studio (SSMS)**.
2. Create or select a database where you want to run the script.
3. Open `SQL LOGIC.sql` and execute the script in SSMS.
4. Run the provided queries to test the database.

---

##  Example Queries

1. Get Total Sales by Product
```sql
SELECT P.PRODUCT_NAME, SUM(S.TOTAL_PRICE) AS TOTAL_SALES
FROM SALESS S
JOIN PRODUCT P ON S.PRODUCT_ID = P.PRODUCT_ID
GROUP BY P.PRODUCT_NAME;

2. Sales on 2024-01-02
SELECT * FROM SALESS
WHERE SALE_DATE = '2024-01-02';

3. Join Products & Sales
SELECT P.PRODUCT_NAME, S.QUANTITY_SOLD, S.SALE_DATE
FROM SALESS S
JOIN PRODUCT P ON S.PRODUCT_ID = P.PRODUCT_ID;
