# Sale Performance - Exploratory Data Analysis

## Project Background
GameZone  -  a fictional company founded in 2018 is selling new and refurbished gaming producrs all around the world, and they are mostly sell their products through their online website, mobile app and variety of marketing channels. With more than 20k records. 

This project will show how can I solve real business problems. 
 

The Excel file with multiple sheets ( raw and cleaned ones) for this analysis can be found [[here](https://github.com/Ensya/Sale-Performance-GameZone/gamezone-orders-data.xlsx)]

An interactive Tableau dashboard used to report and explore sales trends can be found here [link].



## Data Structure & Initial Checks

The companies main database structure as seen below consists of 2 tables: Orders and Region, with a total row count of 21864 records. A description of each table is as follows:
- **Orders :**
  - ORDER_ID
  - 
- **Region:**



## Exploratory Data Analysis (EDA)
  
  Gathering all the requirements is the antidote to getting lost in exploratory data analysis, and to get very intentional about what the delverable should be.
 
  Finding the metrics and questions to anwers through data exploring are vary from department to department (Finance, Marketing) but there might me some frame to identify those metrics and questions: Overall Trends, Growth Rates, Performance Measurement, KPI Reporting. 
 
  In this project, SCAN framework are being used for answering an sample question '_**How did sales look over the COVID years?**_' from the stakeholders (it could be marketing, product managers or finance managers).

### SCAN Framework

 _How did total revenue dollars across all products perform during 2019 - 2022? Conduct some initial analysis to help product, marketing, and finance managers understand high-level trends_ 

**1. Stakeholder goal**

_(What decision is this analysis supporting? What KPIs matter?)_

- no direct decision being made(yet) - focus on high-level trends and patterns. Most important KPI is USD price (revenue)

**2. Columns and coverage**
_(What data do we have available, and how can I use it?)_

- We'll use ```USD_PRICE```, ```PRODUCT_NAME``` and the purchase time columns

**3. Aggregates and anomalies**

_(The high level metrics, outliers,and unexpected patterns)_

- Look at total USD price across months, products, and averages. Identify minimums, maximums, and any outliers.

**4. Notable segments**

_(Slice by category, time,or other key dimension to surface early insights)_

- 
