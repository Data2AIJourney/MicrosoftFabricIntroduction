## 🎯 Objective
Use Data Factory in Fabric to build pipelines that ingest and transform data into your Lakehouse.

## ✅ Prerequisites
- Lakehouse created from the previous lab
- Sample file: product_data.csv

## 🧰 Step 1: Create a Data Pipeline
1. From your Fabric workspace, click New → Data pipeline
2. Name it Product_Pipeline and click Create

## 🔗 Step 2: Add a Data Source
1. Inside the pipeline canvas, click + Pipeline activity → Copy Data
2. Set the source:
  - Choose more connections, slect view more
  - Source type: Azure files
  - Connection: Blob Account
  - File Path: Navigate to the product_data.csv file
  - File Format: DelimitedText
3. Set the destination:
  - Destination type: Lakehouse
  - Target Lakehouse: Sales_Lakehouse (as created in lab1)
  - Root Folder: Tables
  - Table: type product_data
  - Table Action: Overwrite

## ▶️ Step 3: Trigger the Pipeline
1. Click Validate to ensure no errors
2. Click Run to execute the pipeline
3. Monitor progress under the Monitor tab or at the bottom of the pipeline screen in output
4. Navigate to the lakehouse to view your table
5. Create a query to join the slaes and the product data

## 🔄 Step 4: Automate with a Schedule (Optional)
1. Go to Triggers tab
2. Create a new trigger:
  - Type: Schedule
  - Frequency: e.g., Daily
  - Time: 1:00 AM
3. Attach the trigger to the pipeline

## 📘 Key Concepts
- Pipeline: A workflow of data transformation and movement steps
- Copy Activity: Transfers data from source to destination
- Monitoring: View logs and status of runs from the Monitor tab

## 🧠 Tips
- Break complex pipelines into modular activities
- Use naming conventions for easier management
