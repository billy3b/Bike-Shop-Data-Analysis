# Toman Bike Shop Data Analysis Project
## Overview
This project focuses on analyzing the key performance metrics of Toman Bike Share to facilitate informed decision-making. The analysis is conducted using SQL queries and visualized through a Power BI dashboard.

![image](https://github.com/billy3b/Bike-Shop-Data-Analysis/assets/108816279/5dba9a15-ac4e-43ca-8de4-55bf302b7e6d)



## Dashboard Features
- Hourly Revenue Analysis: Visual representation of revenue generated hourly.
- Profit and Revenue Trends: Trends in profit and revenue over time.
- Seasonal Revenue: Analysis of revenue trends across different seasons.
- Rider Demographics: Insights into the demographics of riders.

## Data
The dataset includes information such as season, month, year, weekday, temperature, humidity, Price, COGS and rider type etc. There are three datasets appended for analysis, comprising 11 columns and 34,758 rows.

## Data Analysis Workflow
 1. Create a Database: Set up a database to store the datasets.
 2. Develop SQL Queries: Construct SQL queries to extract relevant insights.
 3. Connect Power BI to DB: Establish connection between Power BI and the database.
 4. Build a Dashboard in Power BI: Design and create a dashboard to visualize the analysis.
 5. Answer the Analysis Questions: Address business questions using the insights derived from the data.

## Tools Used
- SQL Server Management Studio
- Power BI

## SQL Query Used
```
with cte as (
	select * from bike_share_yr_0
	union 
	select * from bike_share_yr_1 
)
select 
dteday,season,a.yr,weekday,hr, rider_type,riders,price,COGS, 
riders*price as revenue, riders*price - COGS*riders as profit
from cte a 
left join cost_table b
on a.yr=b.yr
```

## Business Questions Answered
1. Rider Demographic: Identified 1 million Casual Riders and 3 million Registered Riders.
2. Sales Variation by Day: Highlighted sales patterns, with peak hours during weekdays (7 AM to 9 AM and 5 PM to 7 PM) and weekends (10 AM to 6 PM).
3. Total Revenue and Profit: Total Revenue amounted to 15 million, with a Total Profit of 10.45 million.

## Recommendations
Conservative Increase: Suggested a conservative increase in pricing (10-15%) to test market response without risking significant customer loss.

## How to Use
To replicate the analysis:

- Set up a database using SQL Server Management Studio.
- Execute the provided SQL query to retrieve relevant data.
- Connect Power BI to the database and import the dataset.
- Design and create visualizations in Power BI dashboard.
