# LITA-Capstone-Project-2
Customer Segmentation for a Subscription Service
### Table of Content
- Project Overview [Project Overview](#project-overview)
- Data Description [Data Description](#data-description)
- Data Cleaning [Data Cleaning](#data-cleaning)
- Tool Used
  - Excel Analysis [Excel Analysis](#excel-analysis)
  - MySQL Analysis [MySQL Analysis](#mysql-analysis)
  - Power BI Analysis [Power BI Analysis](#power-bi-analysis)
- Visualizations [Visualizations](#visualizations)
- Key Insights and Recommendations [Key Insights and Recommendations](#key-insights-and-recommendations) 
-Conclusion 




- ###Project Overview
  This project analyzes customer data to identify segments, trends, and insights for a subscription-based service. The goal is to understand customer behaviour, track subscription types, and uncover patterns in cancellations and renewals.


- Methodology
  - Data analysis using Microsoft Excel,MySQL,and Power BI.
  - Data visualizations and insights.

 ### Data Description 
 - Data Source: LITA Capstone
 - Data Period: January 2022 - August 2024
 - 4 regions: East, South, West, North
 - 3 subscription types: Basic, Premium, Standard

- Variables:
 1. CustomerID (Unique identifier for each Subscription 
 2. CustomerName (Unique identifier for each customer)
 3. Region. (Geographic region)
 4. Subscription Type 
 5. Subscription Start
 6. Subscription End
 7. Canceled 
 8. Revenue 

- Notes: This dataset represents Customer's subscription service.
- Data Format: xlsx

  ### Data Cleaning 
 - Data Import: Imported Customer's subscription service data into my Microsoft Excel
 - Data Inspection: Reviewed data for duplicates records 
 - Data Transformation: converted data format to YYYY/MM/DD

### Tool Used
- Microsoft Excel for data cleaning and transformation 
- MySQL for analysis 
- Power BI for modeling and visualization

### Excel Analysis
 
![Customer Subscription Pivot](https://github.com/user-attachments/assets/4a817064-92bb-46b6-af94-fade1d13e8d9)


Key Findings

Revenue Analysis

- Total Revenue: 68M
- Average Subscription Duration: 365.35 days

**Regional Analysis**

| Region | Revenue | Percentage |
| --- | --- | --- |
| East | 17M | 25.11% |
| South | 17M | 25.02% |
| West | 17M | 24.97% |
| North | 17M | 24.9% |

**Subscription Type Analysis**

| Subscription Type | Revenue | Percentage |
| --- | --- | --- |
| Basic | 34M | 50.01% |
| Premium | 17M | 25.02% |
| Standard | 17M | 24.97% |
![Excel Customer Subscription Chart](https://github.com/user-attachments/assets/47a3063f-97d5-42d7-a7f9-6cd4958b7d6f)


### MySQL Analysis
1. Total Number of customers from each Region

```sql
SELECT Region, COUNT(DISTINCT CustomerID) AS Total_Customers
FROM `lita captstone customerdata`
GROUP BY Region;
```

2. Most Popular Subscription type by the number of customers
   
```sql
SELECT SubscriptionType, COUNT(DISTINCT CustomerID) AS Population_Subscription
FROM `lita captstone customerdata`
GROUP BY SubscriptionType
ORDER BY COUNT(DISTINCT CustomerID) DESC 
LIMIT 1;
```

3. Customers who canceled their subscription within 6 months

```sql
SELECT CustomerID, SubscriptionStart, SubscriptionEnd, DATEDIFF(SubscriptionEnd, SubscriptionStart) 
AS Subscription_Duration 
FROM `lita captstone customerdata`
WHERE Canceled = TRUE
AND (
(SubscriptionStart = '2022-01-31' AND SubscriptionEnd <= '2023-07-31')
OR
(SubscriptionStart = '2023-01-31' AND SubscriptionEnd <= '2023-07-31')
);
```

4. Average Subscription duration for all Customers
```sql
SELECT AVG(DATEDIFF(SubscriptionEnd, SubscriptionStart)) AS Average_Subscription_Duration
FROM `lita captstone customerdata`
```
5. Customers with subscriptions longer than 12 months 

```sql
SELECT CustomerID, CustomerName, SubscriptionStart, SubscriptionEnd, DATEDIFF(SubscriptionEnd, SubscriptionStart) 
AS Subscription_Duration 
FROM `lita captstone customerdata`
WHERE DATEDIFF(SubscriptionEnd, SubscriptionStart) > 365;
```

6. Total Revenue by Subscription Type
   
```sql
SELECT SubscriptionType, SUM(Revenue) AS Total_Revenue
FROM `lita captstone customerdata`
GROUP BY SubscriptionType
ORDER BY Total_Revenue DESC;
```


GROUP BY SubscriptionType
7. Top 3 Regions by Subscription Cancellation 

```sql
SELECT Region, COUNT(CustomerID) AS Cancellation_Count
FROM `lita captstone customerdata`
WHERE Canceled = TRUE
GROUP BY Region
ORDER BY Cancellation_Count DESC
LIMIT 3
```

7. Total Number of Active and Canceled Subscriptions 

```sql
SELECT SUM(CASE WHEN Canceled = 'FALSE' OR Canceled = 0 THEN 1 ELSE 0 END) AS Active_Subscriptions,
SUM(CASE WHEN Canceled = 1 THEN 1 ELSE 0 END) AS Canceled_Subscriptions
FROM `lita captstone customerdata`; 
```

- Power BI Dashboard

![Customer subscription Dashboard - Power BI](https://github.com/user-attachments/assets/2b6d5941-2082-4bd8-930a-89c2f0eecd1e)

Insights
*Revenue Analysis*

- The total revenue stands at $68M, indicating a substantial customer base.
- The average subscription duration is 365.35 days, suggesting a relatively long-term commitment from customers.

*Regional Analysis*

- The revenue distribution across regions is relatively even, with East, South, West, and North contributing 25.11%, 25.02%, 24.97%, and 24.9% respectively.
- This suggests a consistent market presence across all regions.

*Subscription Type Analysis*

- The Basic subscription type generates the highest revenue ($34M, 50.01%), followed by Premium ($17M, 25.02%) and Standard ($17M, 24.97%).
- This indicates a strong demand for the Basic subscription type.

*Customer Retention*

- Total subscription renewals (18,612) outnumber cancellations (15,175), indicating a positive customer retention rate.

*Findings*

1. **Regional parity**: Revenue distribution is relatively even across regions, indicating consistent market presence.
2. **Basic subscription dominance**: Basic subscription type generates the highest revenue, suggesting strong demand.
3. **Positive customer retention**: Subscription renewals outnumber cancellations, indicating a loyal customer base.

*Recommendations*

1. *Targeted marketing*: Focus on promoting Basic subscription type in regions with high demand.
2. *Regional optimization*: Analyze regional trends to optimize marketing strategies and improve revenue growth.
3. *Customer retention strategies*: Develop programs to maintain customer loyalty and reduce cancellations.
4. *Premium and Standard subscription enhancement*: Consider enhancing features or pricing to increase adoption rates.




Files

- `customer_data.csv`: customer subscription data
- `power_bi_dashboard.pbix`: Power BI dashboard
- `sql_queries.sql`: SQL queries used for analysis







