# Pizza-Sales-Analysis

**🍕 Pizza Sales Analysis Power BI Dashboard** <br><br>
**📌 Project Overview** <br><br>
This project delivers a comprehensive Pizza Sales Analysis Dashboard built using Power BI, SQL, and Excel. The primary objective is to transform raw pizza order data into actionable business insights. By analyzing order volume, revenue metrics, category preferences, and peak sales periods, this dashboard empowers decision-makers to optimize menu offerings, refine promotional strategies, and improve overall operational efficiency.<br>

**🛠️ Data Architecture & Pipeline** <br><br>
![Dashboard Preview](https://github.com/azhar54321/Pizza-Sales-Analysis/blob/main/Untitled.png)

**🚀 Key Features & Functional Requirements**<br><br>
**1. Key Performance Indicators (KPIs)**<br>
**-Total Pizza Revenue:** Overall income generated from pizza sales over a specified time period.

**-Average Order Value (AOV):** Average amount spent per pizza order.

**-Total Pizzas Sold:** Cumulative count of individual pizzas sold.

**-Total Orders Placed:** Total volume of distinct pizza orders processed.

**-Average Pizzas Per Order:** Average quantity of pizzas purchased per order transaction.<br><br>

**2. Trend & Operational Insights**<br>
**-Daily Trend for Total Orders:** Bar chart tracking peak ordering days to optimize store staffing and prep inventory.<br>

**-Monthly Trend for Total Orders:** Line chart highlighting seasonality and sales fluctuations across months.<br>

**-Sales by Pizza Category:** Breakdown of sales percentage across categories (e.g., Classic, Supreme, Chicken, Veggie).<br>

**-Sales by Pizza Size:** Revenue distribution based on pizza sizes (e.g., Regular, Medium, Large, XL, XXL).<br><br>


**3. Menu Performance & Ranking**<br>
**-Top 5 Best-Selling Pizzas:** Ranked by Revenue, Total Quantity Sold, and Total Orders.<br>

**-Bottom 5 Worst-Selling Pizzas:** Identified by lowest sales volume and revenue to assist with menu engineering and item retirement.<br><br>


**🛢️ SQL Queries Used for Data Verification**<br>
Below are sample SQL queries utilized to validate the Power BI metrics against the raw database: <br><br>

**-- 1. Total Pizza Revenue**
SELECT SUM(total_price) AS Total_Revenue 
FROM pizza_sales;

**-- 2. Average Order Value**
SELECT SUM(total_price) / COUNT(DISTINCT order_id) AS Avg_Order_Value 
FROM pizza_sales;

**-- 3. Total Pizzas Sold**
SELECT SUM(quantity) AS Total_Pizzas_Sold 
FROM pizza_sales;

**-- 4. Total Orders**
SELECT COUNT(DISTINCT order_id) AS Total_Orders 
FROM pizza_sales;

**-- 5. Top 5 Best-Selling Pizzas by Revenue**
SELECT TOP 5 pizza_name, SUM(total_price) AS Total_Revenue
FROM pizza_sales
GROUP BY pizza_name
ORDER BY Total_Revenue DESC;

**-- 6. Bottom 5 Worst-Selling Pizzas by Quantity**
SELECT TOP 5 pizza_name, SUM(quantity) AS Total_Quantity
FROM pizza_sales
GROUP BY pizza_name
ORDER BY Total_Quantity ASC; <br><br>


**📊 DAX Calculations Used**<br>
Here are key DAX formulas created within Power BI for interactive visualization:<br>

// Total Revenue
Total Revenue = SUM(pizza_sales[total_price])

// Total Pizzas Sold
Total Pizzas Sold = SUM(pizza_sales[quantity])

// Total Orders
Total Orders = DISTINCTCOUNT(pizza_sales[order_id])

// Average Order Value
Average Order Value = [Total Revenue] / [Total Orders]

// Average Pizzas Per Order
Avg Pizzas Per Order = [Total Pizzas Sold] / [Total Orders] <br><br>


**💻 Tech Stack**<br>
Business Intelligence: Power BI (Power Query, DAX, Data Modeling)

Database & Querying: SQL (SQL Server / MySQL)

Data Prep & Source: Microsoft Excel / CSV

Documentation: Markdown <br><br>



### 6.	Screenshots / Demos
Show what the dashboard looks like.
Example: ![Dashboard Preview](https://github.com/azhar54321/Pizza-Sales-Analysis/blob/main/Page%201.png) <br><br>
         ![Dashboard Preview](https://github.com/azhar54321/Pizza-Sales-Analysis/blob/main/Page%202.png)


