## 🎯 Objective
Learn how to set up and explore a Lakehouse in Microsoft Fabric, load data, and understand the integration with OneLake.

## ✅ Prerequisites
- Microsoft Fabric enabled workspace
- Contributor or higher role in the workspace
- Sample dataset from /resources/sample-data/ (e.g., sales_data.csv)

## 🧱 Step 1: Create a Lakehouse
1. Go to your Fabric workspace
2. Click on New → Lakehouse
3. Give it a name (e.g., Sales_Lakehouse)
4. Click Create

## 📁 Step 2: Load Data into the Lakehouse
1. Open your newly created Lakehouse
2. Under the Files tab, click Upload
3. Upload sales_data.csv from the resources folder
4. After upload completes,exit and click on files
  - Explore the file by clicking on th efile you have loaded to see what is in it
5. Right-click on the file and choose Load to Tables
6. Follow the prompt to create a new table (e.g., sales_data)

## 🔍 Step 3: Explore the Data
1. In the upper right, change from lakehouse to SQL Analytics Endpoint
2. Expand the lakehouse, expand schemas, find your table
3. Select the sales_data table
4. Right clikc on the table, select New SQL query, Select top 100
Optional
1. Right click on my Queries, Select new SQL query
2. Run a simple query:
  - SELECT TOP 100 * FROM sales_data where product = 'Widget C' ;

## 📘 Key Concepts
- OneLake: A unified data lake that stores all Fabric data assets
- Delta Tables: Tables in Lakehouse are Delta format compatible for ACID transactions
- SQL Analytics Endpoint: Allows querying Lakehouse tables with T-SQL

## 🧠 Tips
- Use folders in the Files tab to organize data
- You can also connect to this Lakehouse using Notebooks (see next module)
