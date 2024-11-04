# LITA-Capstone-Project-2
Customer Segmentation for a Subscription Service
### Table of Content
- Introduction [Introduction](#introduction)
- Project Overview [Project Overview](#project_overview)
- Dataset [Dataset](#dataset)

- Project Overview [Project Overview](#project-overview)
- Data Description [Data Description](#data-description)
- Data Cleaning [Data Cleaning](#data-cleaning)
- Tool Used:
  - Excel Analysis [Excel Analysis](#excel-analysis)
  - MySQL Analysis [MySQL Analysis](#mysql_analysis)
  - Power BI Analysis [Power BI Analysis](#power_bi_analysis)

- Insights and Findings 
-Conclusion 




- ###Project Overview

This project analyzes customer data for a subscription service to identify segments and trends. The goal is to understand customer behavior, track subscription types, and identify key trends in cancellations and renewals.




- Methodology
  - Data analysis using Microsoft Excel,MySQL,and Power BI.
  - Data visualizations and insights.

 ### Data Description 
 - Data Source: Public Sales dataset
 - Customer subscription data (anonymous)
- 4 regions: East, South, West, North
- 3 subscription types: Basic, Premium, Standard![Customer subscription Dashboard - Power BI]


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





Key Findings

Revenue Analysis

- Total Revenue: $68M
- Average Subscription Duration: 365.35 days

Regional Analysis

| Region | Revenue | Percentage |
| --- | --- | --- |
| East | $17M | 25.11% |
| South | $17M | 25.02% |
| West | $17M | 24.97% |
| North | $17M | 24.9% |

Subscription Type Analysis

| Subscription Type | Revenue | Percentage |
| --- | --- | --- |
| Basic | $34M | 50.01% |
| Premium | $17M | 25.02% |
| Standard | $17M | 24.97% |

*Tools Used*

- Excel
- SQL Server
- Power BI





Insights
*Revenue Analysis*

- The total revenue stands at $68M, indicating a substantial customer base.
- The average subscription duration is 365.35 days, suggesting a relatively long-term commitment from customers.

Regional Analysis

- The revenue distribution across regions is relatively even, with East, South, West, and North contributing 25.11%, 25.02%, 24.97%, and 24.9% respectively.
- This suggests a consistent market presence across all regions.

Subscription Type Analysis

- The Basic subscription type generates the highest revenue ($34M, 50.01%), followed by Premium ($17M, 25.02%) and Standard ($17M, 24.97%).
- This indicates a strong demand for the Basic subscription type.

Customer Retention

- Total subscription renewals (18,612) outnumber cancellations (15,175), indicating a positive customer retention rate.

*Findings*

1. *Regional parity*: Revenue distribution is relatively even across regions, indicating consistent market presence.
2. *Basic subscription dominance*: Basic subscription type generates the highest revenue, suggesting strong demand.
3. *Positive customer retention*: Subscription renewals outnumber cancellations, indicating a loyal customer base.

*Recommendations*

1. *Targeted marketing*: Focus on promoting Basic subscription type in regions with high demand.
2. *Regional optimization*: Analyze regional trends to optimize marketing strategies and improve revenue growth.
3. *Customer retention strategies*: Develop programs to maintain customer loyalty and reduce cancellations.
4. *Premium and Standard subscription enhancement*: Consider enhancing features or pricing to increase adoption rates.

*Future Work*

1. Predictive modeling for customer churn
2. Clustering analysis for customer segmentation
3. Geospatial analysis for regional trends

Data Dictionary



Files

- `customer_data.csv`: customer subscription data
- `power_bi_dashboard.pbix`: Power BI dashboard
- `sql_queries.sql`: SQL queries used for analysis







- Power BI Dashboard
![Customer Subscription Pivot](https://github.com/user-attachments/assets/4a817064-92bb-46b6-af94-fade1d13e8d9)


![Customer subscription Dashboard - Power BI](https://github.com/user-attachments/assets/2b6d5941-2082-4bd8-930a-89c2f0eecd1e)
![Excel Customer Subscription Chart](https://github.com/user-attachments/assets/47a3063f-97d5-42d7-a7f9-6cd4958b7d6f)
