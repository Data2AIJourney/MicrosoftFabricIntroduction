## 🎯 Objective
Create and explore a dedicated SQL Data Warehouse in Fabric to store and query structured data.

## ✅ Prerequisites
- Fabric workspace access
- Sample data: orders.csv

## 🏗️ Step 1: Create a Warehouse
1. From your workspace, click New → Warehouse
2. Name it Orders_Warehouse
3. Click Create

## 📤 Step 2: Load Data
1. Open the lakehouse and load the orders data as a table
2. Open the new warehouse and click New SQL query
3. Use the Select INTO statement to load data:
    - Select * into dbo.orders from Sales_Lakehouse_JM.dbo.orders

## 🔍 Step 3: Query the Warehouse
1. Run a query like:
    - SELECT COUNT(*) FROM dbo.orders;

 ## 📘 Key Concepts
- Warehouse: A dedicated SQL analytics database
- T-SQL: Full support for transactional queries and views

