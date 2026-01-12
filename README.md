# E-Commerce-Analysis---UK
### Sales Analysis Project (Python + Seaborn)
#### Overview
This project performs end-to-end sales data cleaning, feature engineering, and exploratory data analysis (EDA) on a retail transactions dataset. The goal is to identify real sales transactions, analyze time-based sales patterns, and present insights using Seaborn visualizations (including faceted plots).

#### Data Source
The dataset used in this project is publicly available on Kaggle and is not included in this repository due to file size limitations.

    Dataset link:
    https://www.kaggle.com/datasets/atharvaarya25/e-commerce-analysis-uk/data


#### Dataset

The dataset contains retail transaction records with the following columns:

- InvoiceNo, StockCode, Description

- Quantity, UnitPrice

- InvoiceDate

- CustomerID

- Country

#### Tools & Libraries

- Python

- Pandas, NumPy

- Seaborn, Matplotlib

#### Data Cleaning (Business Rules)

To ensure the analysis reflects genuine customer sales, the following business-driven rules were applied:

- **Duplicate transactions** were removed to prevent double-counting revenue.
- **Returns and cancellations** were excluded by keeping only transactions with a positive quantity (`Quantity > 0`).
- **Non-sales system records** such as free items and accounting adjustments were removed by retaining only transactions with a positive unit price (`UnitPrice > 0`).
- Records with missing product descriptions and customer IDs were automatically eliminated, as these were consistently associated with zero-priced system entries.
- The dataset index was reset after filtering to maintain a clean and continuous structure.

#### Feature Engineering

From InvoiceDate, the project extracts time-based features to support trend analysis:

- year

- MonthName

- DayName

- hour

- Part of the Day (Categorization)

Using pd.cut, hours are grouped into readable time periods:

    Night (0–6)

    Morning (6–12)

    Afternoon (12–18)

    Evening (18–24)

Revenue Column

A sales/revenue column is created:

    sales = Quantity * UnitPrice

### Analysis Performed
#### Time-Based Sales Insights

- Monthly sales (Which month is highest/lowest?)

- Day-of-week sales (Which weekday is busiest?)

- Time-of-day sales (Morning vs afternoon vs evening)

#### Business Deep Dives

- Sales by Country

- Top Products by revenue (Top 10 and lowest 10)

- Sales trend across time (Monthly trend by year)

- Day vs Time-of-day matrix (Pivot + heatmap)

- Customer spending distribution (customer segmentation concept included)

#### Visualizations

The following charts show insights from the data:

- Sales by Month
  
  <img width="551" height="263" alt="totalSalesByMonth" src="https://github.com/user-attachments/assets/b52d0288-87c6-4f8f-b14b-95ab2db658be" />


- Sales by Day of Week
  
  <img width="359" height="225" alt="TotalSalesByDaysOfAWeek" src="https://github.com/user-attachments/assets/f5c636d8-88e7-4b51-a943-bf2667c8daac" />


- Sales by Part of the Day
  
  <img width="345" height="233" alt="TotalSalesByTimeOfADay" src="https://github.com/user-attachments/assets/daf3eb34-7c55-4daf-8e64-dfbf1e2ce545" />

- Top 10 Products by Revenue
  
    <img width="584" height="326" alt="Top10Products" src="https://github.com/user-attachments/assets/137a5dd5-afa7-411a-9279-5640940f27c5" />
    
- 10 Lowest Selling Products
  
   <img width="536" height="315" alt="LowestSelling10Items" src="https://github.com/user-attachments/assets/0f893a2c-ab02-4759-9262-3094ab308178" />


- Top 5 Countries by Sales Revenue
  
  <img width="470" height="300" alt="SalesByCountry" src="https://github.com/user-attachments/assets/633382e7-3490-43de-b33d-23d4f74d7428" />

- Monthly Sales Trend by Year
  
  <img width="630" height="356" alt="MonthlySalesTrendByYear" src="https://github.com/user-attachments/assets/a13b5328-f65f-4afe-bb26-6375254bd23a" />

- Sales by Day of Week and Part of Day
  
  <img width="449" height="278" alt="SalesHeatmapDayVsPartOfTheDay" src="https://github.com/user-attachments/assets/f4f96444-bd57-45b6-bd90-61fc22998e75" />


- Customer Segment Distribution
  
  <img width="527" height="263" alt="CustomerRevenueDistributionBySegment" src="https://github.com/user-attachments/assets/24519fdd-0bf5-4815-8230-4c7fbebcb984" />


#### Key Findings & Business Insights
#### Seasonal Sales Patterns

Sales show strong seasonality, with November generating the highest revenue, likely driven by pre-holiday and festive demand.

February records the lowest sales, indicating a post-holiday slowdown and reduced customer activity.

- Business value:
This insight can help businesses plan inventory, promotions, and staffing around peak and off-peak months.

#### Weekly Sales Behavior

Thursdays consistently generate the highest sales, suggesting strong mid-week purchasing behavior.

Sundays show the lowest revenue, indicating reduced shopping activity toward the end of the week.

- Business value:
Marketing campaigns and product launches may perform better when scheduled mid-week rather than on weekends.

#### Time-of-Day Purchasing Trends

The Afternoon period produces the highest revenue, followed closely by Morning hours.

Night-time sales are 0, showing no customers are active during late hours.

- Business value:
Businesses can optimize operational hours, customer support availability, and digital promotions to align with peak purchasing times.

#### Product Sales Distribution

Sales are unevenly distributed across products, with number of items generating very high revenue, while many products contribute relatively low sales.

The dataset clearly shows the presence of both highest-selling items and lowest-selling items, indicating variation in product demand.

#### Geographic Sales Distribution

The United Kingdom dominates total sales, while several international markets show moderate but consistent demand.

- Business value:
There is potential for market expansion strategies in high-performing international regions.

#### Data Quality Insight

Missing product descriptions, zero unit prices, and missing customer IDs consistently occur together, confirming they represent system or adjustment records rather than real sales.

Removing these records improved revenue accuracy without affecting genuine transactions.

- Business value:
Ensures reliable financial insights and prevents revenue overestimation.

#### How to Run

Clone/download this repository

Install dependencies:

pip install pandas numpy seaborn matplotlib


