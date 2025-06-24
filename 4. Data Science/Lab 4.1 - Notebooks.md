## 🎯 Objective
Explore the use of Notebooks in Fabric to run Spark-based transformations.

## ✅ Prerequisites
- Existing Lakehouse with data loaded

## 📝 Step 1: Create a Notebook
1. Click New → Notebook
2. Select PySpark runtime
3. Add data items -> exisitng items
4. Select your lakehouse

## 🧪 Step 2: Load Data from Lakehouse
1. df = spark.read.table("{YOUR LAKEHOUSE NAME}.sales_data")
2. df.show()
    - display(df)
3. df = df.withColumnRenamed('product', 'ProductName')
## 🧹 Step 3: Transform the Data
1. df_filtered = df.filter(df["region"] == "Midwest")
2. df_filtered = df_filtered.withColumnRenamed('product', 'ProductName')
3. df_filtered = df_filtered.groupBy("ProductName").sum("sales")
4. df_ordered =  df_filtered.orderBy(df_filtered["sum(sales)"].desc())
5. display(df_ordered)

## 📘 Key Concepts
- Notebook: Interactive environment for Spark, Python, and SQL
- DataFrame: Core abstraction for data in Spark
