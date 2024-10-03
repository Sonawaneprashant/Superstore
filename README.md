# Superstore-Dashboard


## Introduction

The Superstore Dashboard is an interactive business intelligence solution built using Power BI to analyze and visualize sales performance, profitability, and customer segmentation within a retail environment. The dataset, sourced from a fictional superstore, includes detailed transactional data such as sales, profit, quantity, discounts, and customer demographics across various regions and product categories.

The goal of this project is to provide valuable insights into the store's operations by tracking key performance indicators (KPIs) such as total sales, profit margins, and regional performance. The dashboard empowers decision-makers to optimize inventory, target specific customer segments, and improve profitability by understanding sales patterns and the impact of discounts on revenue.

The project demonstrates advanced Power BI functionalities such as data modeling, creating relationships between tables, and using DAX (Data Analysis Expressions) to perform complex calculations. Additionally, this dashboard allows users to drill down into specific metrics like top-performing products and regions, offering a deeper understanding of business performance.

### Objective

The primary objective of this dashboard is to analyze sales performance, customer segmentation, and profitability across different regions and product categories. By leveraging the Superstore dataset, the goal is to provide business insights that can drive decision-making, such as optimizing inventory, identifying top-performing products, and understanding customer behavior patterns.

Specific Goals:
* Sales Analysis: Track total sales across various regions, product categories, and customer segments.
* Profitability: Analyze the profit margin to identify high-performing products and regions.
* Customer Segmentation: Understand how different customer segments contribute to the overall business.
* Discount Impact: Assess how discounts affect sales and profit margins.

### Data Source

Data downlodad from online

The data for this report includes Store sales data, and operational KPIs collected throughout the year. Data was cleaned and processed before being visualized in the dashboard.

### Tool used

  * Excel : Data cleaning, and manipulation
  * Power Query : Data clanining, creating Fact and Dimdnsion tables
  * Data modeling : created Star Schema
  * Power BI : Visualizations, Drill through
  * Power BI Service : Dashboard sharing

### DAX 
* Adjusted Price(Value) = [Average Price]*(1+([Adjusted Profit Value Value]))
* Adjusted Profit = [Adjusted Revenue]-[Total Cost]
* Adjusted Revenue = SUMX(Main,Main[Quantity]*[Adjusted Price(Value)])
* Average Days to Ship = AVERAGEX
(Main,DATEDIFF(Main[Order Date],Main[Ship Date],DAY))
* Average Days to Ship = AVERAGEX
(Main,DATEDIFF(Main[Order Date],Main[Ship Date],DAY))
* Average Discount % = AVERAGEX(Main,Main[Discount]*100)
* Average Price = DIVIDE([Total Revenue],[Total Quantity],0)
* Prev Month Revenue = CALCULATE([Total Revenue],DATEADD('Calendar'[Date],-1,MONTH))
* Previous Month Total Order = CALCULATE([Total Order],PREVIOUSMONTH('Calendar'[Date]))
* Profit Margin = DIVIDE([Total Profit],[Total Revenue],0)
* Revenue Target = [Prev Month Revenue]*1.1
* Sales Growth = DIVIDE ( 
    [Total Revenue]
        -CALCULATE ( [Total Revenue], SAMEPERIODLASTYEAR ( 'Calendar'[Date] ) ),
    CALCULATE ( [Total Revenue], SAMEPERIODLASTYEAR ( 'Calendar'[Date] ) ),0)
* Target % = [Total Revenue]/1000000
* Target Diff = 1- [Target %]
* Target Sales = [Total Revenue]*1.10
* Total Cost = [Total Revenue]-[Total Profit]
* Total Discount = SUM(Main[Discount])
* Total Mtd = TOTALMTD([Total Revenue],'Calendar'[Date]) 
* Total Order = DISTINCTCOUNT(Main[Order ID])
* Total Profit = SUM(Main[Profit])
* Total Qtd = TOTALQTD([Total Revenue],'Calendar'[Date])
* Total Quantity = SUM(Main[Quantity])
* Total Revenue = //CALCULATE(SUM(Main[Sales]))
             SUM(Main[Sales])
* Total Ytd = TOTALYTD([Total Revenue],'Calendar'[Date]) 
* Adjusted Profit Value = GENERATESERIES(-1, 1, 0.05)
* Adjusted Profit Value Value = SELECTEDVALUE('Adjusted Profit Value'[Adjusted Profit Value])


### Key Metrics

The dashboard focuses on several key metrics to provide a clear picture of business performance:

* Calendar: Table for contineous date 
* Total Sales: Overall revenue generated from all sales.
* Total Profit: Net profit after costs are subtracted from sales.
* Profit Margin: The percentage of profit from total sales.
* Total Quantity Sold: The total number of units sold.
* Sales by Region: Breakdown of sales performance across * different geographic regions.
* Top Performing Products: Products that generate the highest sales and profit.
* Discount Impact: Evaluation of how discounts affect overall profitability.

### Visualizations (using pivot Table)

* Card
* Slicer
* Funnel
* Donut chart
* Line chart
* Stacked bar chart
* Matrix
* Gauge
* Area chart

 # Dashboard (Power BI)

 ![Superstore_Dashboard](https://github.com/user-attachments/assets/32738dd3-e492-4af9-b9aa-463203935ee5)

* 2nd Page, Product Details (Drill through)
![Superstore_Product Details](https://github.com/user-attachments/assets/9a981082-a296-47dd-a843-d848d97cfbf8)

# Data modeling (Star Schema)
![Star schema](https://github.com/user-attachments/assets/f18a9890-8a6e-463b-8731-557634dd45a2)


# Key Insights

The Superstore Dashboard provides valuable insights, including:

* Regional Sales and Profitability: The West region generates the highest sales, while the South region shows the best profit margins.
* Top Performing Products: Technology-related products, especially Office Machines, drive the most sales and profits.
* Impact of Discounts on Profit: Discounts over 20% significantly reduce profit margins, particularly in the Furniture and Office Supplies categories.
* Customer Segmentation Insights: The Consumer segment drives the most orders, while the Home Office segment yields higher average order values.
* Seasonal Trends: Sales peak during the holiday season, suggesting a need for inventory and marketing optimization during these times.
* Underperforming Categories: Categories like Office Supplies and sub-categories like Tables underperform in profitability despite moderate sales.

# Conclusion and Future Improvement

The Superstore Dashboard delivers actionable insights to help decision-makers optimize product inventory, improve regional sales strategies, and refine discount policies. By using the dashboard, business leaders can make data-driven decisions that enhance profitability, improve customer targeting, and drive overall business growth.
