## 🎯 Objective
Explore the use of Notebooks in Fabric to run Spark-based transformations.

## ✅ Prerequisites
- Existing Lakehouse with data loaded

## 📝 Step 1: Create a Notebook
1. Click New → Notebook
2. Name it Lakehouse_Analysis
3. Select Spark runtime

## 🧪 Step 2: Load Data from Lakehouse
1. df = spark.read.table("Sales_Lakehouse.sales_data")
2. df.show()

## 🧹 Step 3: Transform the Data
1. df_filtered = df.filter(df["region"] == "Midwest")
2. df_filtered.groupBy("product").sum("sales").show()

## 📘 Key Concepts
- Notebook: Interactive environment for Spark, Python, and SQL
- DataFrame: Core abstraction for data in Spark
