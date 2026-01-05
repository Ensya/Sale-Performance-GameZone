# Sale Performance - Exploratory Data Analysis

## Project Background
GameZone  -  a fictional company founded in 2018 is selling new and refurbished gaming products all around the world, and they are mostly sell their products through their online website, mobile app and variety of marketing channels.

The goal of this project was to extract actionable insights on sales performance, customer trends, regional growth, and product performance using interactive dashboards and data modeling.
The analysis supports business decisions in marketing, inventory, and regional strategy.

The Excel file with multiple sheets ( raw and cleaned ones) for this analysis can be found [[here](https://github.com/Ensya/Sale-Performance-GameZone/gamezone-orders-data.xlsx)]




## Data Structure & Initial Checks

The companies main database structure as seen below consists of 2 tables: Orders and Region, with a total row count of 21864 records. A description of each table with multiple columns is as follows:
- **Orders :**
  - USER_ID: Each order have an unique id.
  - ORDER_ID: Unique order id. However some duplicates found in this dataset within unique user id. 
  - PURCHASE_TS: Purchasing timestamp from customers. 
  - SHIP_TS: Shipping timestamp
  - PRODUCT_NAME: Product sold within the order
  - PRODUCT_ID: Id of product
  - USD_PRICE: Revenue
  - PURCHASE_PLATFORM: Order was made through website or mobile app.
  - MARKETING_CHANNEL: The channel used for selling (affiliate, directly,email, social media, unknown channel)
  - ACCOUNT_CREATION_METHOD: Account can be made through multiple method (Desktop,mobile, tablet, tv,unknown method). Some missing information found in both of the marketing channel and account creation method, which show that there are a correlation of missing value between these columns, however, the magnitude 
  - COUNTRY_CODE: Code of country, and I can now where's it come from (region).

- **Region:**
  - COUNTRY_CODE: Code of country of customers
  - REGION: Region that the order belongs.
    
**Data Model Design:**

`orders_cleaned` (fact table)

`region_cleaned` (region dimension)

`Date` (date dimension)

Star schema with relationships on `COUNTRY_CODE` and `PURCHASE_TS`

### 🔗 Data Model Diagram

 <img width="562" height="536" alt="Ảnh màn hình 2026-01-04 lúc 15 43 34" src="https://github.com/user-attachments/assets/77564179-dd42-4eb7-95a1-ac7addaa1f59" />

*This visual illustrates the data relationships between `orders_cleaned`, `region_cleaned`, and the `Date` table.*

---
## Exploratory Data Analysis (EDA)
  
  Gathering all the requirements is the antidote to getting lost in exploratory data analysis, and to get very intentional about what the delverable should be.
 
  Finding the metrics and questions to anwers through data exploring are vary from department to department (Finance, Marketing) but there might me some frame to identify those metrics and questions: Overall Trends, Growth Rates, Performance Measurement, KPI Reporting. 
 
  In this project, SCAN framework are being used for answering an sample question '_**How did sales look over the COVID years?**_' from the stakeholders (it could be marketing, product managers or finance managers).

### SCAN Framework

 _How did total revenue dollars across all products perform during 2019 - 2022? Some initial analysis to help product, marketing, and finance managers understand high-level trends_ 

**1. Stakeholder goal**

_(What decision is this analysis supporting? What KPIs matter?)_

- no direct decision being made(yet) - focus on high-level trends and patterns. Most important KPI is USD price (revenue)

**2. Columns and coverage**
_(What data do we have available, and how can I use it?)_

- We'll use ```USD_PRICE```, ```PRODUCT_NAME``` and the purchase time columns

**3. Aggregates and anomalies**

Look at total USD price across months, products, and averages. Identify minimums, maximums, and any outliers._(The high level metrics, outliers,and unexpected patterns)_
<img width="1287" height="566" alt="Ảnh màn hình 2026-01-03 lúc 01 39 28" src="https://github.com/user-attachments/assets/8f1afc10-1524-46f5-be26-c24ef5385a2b" /> 
- Metrics and Dimension relevant to each teams
  - Finance Team:
    - Total sales across 2019-2022 is around ($6.1million), ranging in montly sales from $80k to $500k
    - Top performing product is gaming monitor(almost $2M total sales), worst performing os gaming headset with $800. (might be missing data and would need to check with the finance team.
    - All products has a significant spike in sales 2020 onwards, following the general trend in total sales. This indicates a macro or company-wide impact (mostly likely due to COVID)

  - Marketing/Product Team:
    - Worst performing category is headsets, which are responsible for less than 2% of sales
    - Dec 2020 saw a large spike in sales - seems like fall and winter month, which might indicates impact factors comes from promotions or holiday season
    - Almost all product exhibited a spike in Dec 2020 - look into campaigns and promotions at this time 
      
**4. Notable segments** ~

_(Slice by category, time,or other key dimension to surface early insights)_

To prevent analysis paralysis from the beginning is to identify the core questions and ways to solve it. By using North Stars Metrics, North Stars Dimensions and North Stars Team Goals

_Note: This is a porfolio project so I'm going to just focus on the USD price or total revenue as I don't have a lot of clarity from our stakeholder_

- Metrics: USD Price, Total Revenue, Order Count, AOV ( Average Order Vavlue)
- Dimensions: Region, Marketing Channel, Product, Time
- Team Goals:
  - Marketing Team: To attract more customers or get them to buy more
  - Finance Team: Where is the revenue or loss coming from?
  - Product Team: What features or product lines are popular?

## Insights Deep Dive  
### High Level Sales 
- Sales surged to record highs in late 2020 and then sharply declined in February 2021, nearing pre-COVID levels
- Sales more than doubled in the early 2020, with all-time highs in September and December in 2020
### Product insights: 
- Along the products aspect, Gaming monitor, Nintendo Switch, and Xbox are the main ddrivers of the dip - all three exhibit the same plateuing behaviour in 2021 and 2022. 
### Region Insights: 
- For Xbox, the drops is mostly contained to the NA region and direct traffic - may indicate a shift in trends or competitiors there
- The sales mix by channel is directly taking up from 70% to 80% of total revenue (roughly around 25%). Direct is the main driver of all sales. All other channels pale in comparison.
## Recommendations 
### Finance Team 
- Investigate the main drivers of the dip in sales in the years following COVID. As the metric showed without any dimentional insight and, for the contextual insights, during the covid year there was a huge spike in sales, which confirms our understanding that when people are spending more time at home, which leads to higher willingness to spend on gaming products.
### Product Team 
- Low hanging fruit recommendation is to consider discountinuing the headsets because it only make up less than 2% of overall revenue.
### Marketing Team
- Push more promotions and marketing strategies towards North American sales fro gaming monitor and playstation, which have more traction than other top 2 products
- Double down on Winter sales by pushing promotions for top 3 products in October/November
- Checking with marketing team about attriobution to marketing channel if it is correct. As dirrect seemsoversized. Focus marketing startegy on email channel, which shows potential up tick, in order to shift away from reliance on Direct traffic. 
# Dashboard

An interactive Tableau dashboard used to report and explore sales trends can be found here [[link](https://public.tableau.com/views/GameZoneSalesDashboard_17674577239320/SalesDashboard?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)].

<img width="2778" height="2718" alt="Sales Dashboard" src="https://github.com/user-attachments/assets/afb460f1-8d07-49a9-b002-a49086297e47" />


</p>







