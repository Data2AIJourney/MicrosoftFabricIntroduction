#  IN PROGRESS
## 🎯 Objective

Connect to Fabric data and leverage natural language to ask questions about the data.

## ✅ Prerequisites

Lakehouse, Warehouse, semantic model or data stored in Fabric

## 🔌 Step 1: ICreate the agent

1. Login into Fabric
2. Create New Item -> Data Agent
3. Name the agent -> Create

## 🔗 Step 2: Connecting the agent to data
1. Add a data source to your agent
    - Choose the NYC Taxi lakehouse, the SFtechDW_Sample warehouse, and the WWImporter_%5 sematic model
2. Select a set of tables from the lakehouse and warehouse to be able to answer queestions below
3. Ask some of the follwoing questions
    - How many taxi rides were there in 2019
    - What was the average distance for a taxi ride in the year of 2021
    - What was the total amount processed for trips for the years 2010 to 2015
    - Who was the top customer in sales
    - 

## Fine tuing the agent to get better results

1. Add the follwoing context to your agent
    - The NYC Taxi Lakehouse is wher eyou cna find information in relation to taxi rides and trips. This will help make sure you are getting things related to specifc fares and all reatled data to the fares

    The WWImporter_560 is a semantic model for the worldwide importers company. In here you will find things realted to sales, customers, and products related to those sales. This is in the form of facts and dimenions and key fields should eb used to join between tbales

    The SFTech_DWSample is a data warehous esample of data that is related to a private car service. While it is similar to taxi this is not related and should focus on trips and medallions which ar considered the private town car people would take for their trip.
2. Add the follwoing query examples to your agent
    - Finding the top customers for sales
    
    Select top 1 cust.Customer, sum(sales.UnitPrice)*sum(sales.Quantity) as TotalRevenue from 
dbo.dimension_customer cust
inner JOIN
dbo.fact_sale sales 
on cust.CustomerKey = sales.CustomerKey
group by cust.Customer
order by TotalRevenue

    - FInding trips by year
    
    Select *  FROM [dbo].[Trip] T
JOIN [dbo].[Date] D ON T.DateID = D.DateID
WHERE D.Year BETWEEN '2010' AND '2015';
    - Number of taxi rides for a given year

    SELECT COUNT(*) AS TotalRides
FROM [year_2019].[green_tripdata_2019];

    - Medallions Trips

    SELECT MedallionCode, count(DateID) totaltrips
FROM [SFtech_DWSample].[dbo].[Medallion] med
inner join dbo.Trip trip 
on med.MedallionID = trip.MedallionID
group by MedallionCode

3. Retest questions, also try the follwoing
