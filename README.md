# ECommerce-Sales-Power-BI

🛒 E-Commerce Sales Analysis – Power BI
📌 Project Overview

This project focuses on building an end-to-end Power BI solution for an e-commerce business.
The objective is to transform raw transactional data, model it correctly for analytics, and finally build business-ready dashboards to analyze sales, customers, products, orders, discounts, and profitability.

The project is executed in three structured modules:

Data Transformation (Power Query)

Data Modeling & Measure Creation (DAX)

Visualization & Business Analysis

🎯 Business Objectives

Categorize discounts and analyze their impact on sales

Build a clean fact table for analysis

Create industry-standard KPIs (AOV, AIPO, ARPC, Profit Margin)

Analyze customer segments, product performance, and order profitability

Deliver executive-ready dashboards

🛠️ Tools & Technologies

Power BI Desktop

Power Query (Data Transformation)

DAX (Measures & KPIs)

GitHub (Version control & documentation)

🔄 Module 1: Data Transformation (Power Query)
📄 Table: Sales
➕ Conditional Column – Discount Category

Column Name: Discount Category

Discount = 0%        → No Discount
Discount ≤ 10%       → Low
Discount ≤ 25%       → Medium
Else                 → High

🔗 Table Merging (Final Fact Table)

All merges use Left Join to preserve sales data:

Sales ⟶ Products

Join Key: Product ID

Expanded columns excluding Product ID

Result ⟶ Customers

Join Key: Customer ID

Expanded columns excluding Customer ID

➕ Calculated Columns
🧮 Product Amount
Product Amount = Quantity × Product List Price

💰 Sales Amount
Sales Amount = Product Amount − (Discount × Product Amount)


✔ Dataset finalized using Close & Apply

🧩 Module 2: Data Modeling & Measures
📌 Fact Table

Sales

🔗 Relationships
Many-to-One

Sales ↔ Products (Product ID)

Sales ↔ Customers (Customer ID)

Sales ↔ Dates (Order Date → Date)

🔑 Unique Entity Creation

Column Name: Order_Line_ID

Order_Line_ID = [Order ID] & "-" & [Product ID]

📐 Core Measures (DAX)
Total Sales = SUM(Sales[Sales Amount])

Total Quantity Sold = SUM(Sales[Quantity])

Total Orders = DISTINCTCOUNT(Sales[Order ID])

AOV =
DIVIDE([Total Sales], [Total Orders])

AIPO =
DIVIDE([Total Quantity Sold], [Total Orders])

Total Customers =
DISTINCTCOUNT(Customers[Customer ID])

ARPC =
DIVIDE([Total Sales], [Total Customers])

📊 Module 3: Advanced Measures
Total Sales All =
CALCULATE([Total Sales], ALL(Products))

Total Quantity Sold All =
CALCULATE([Total Quantity Sold], ALL(Products))

Total Orders All =
CALCULATE([Total Orders], ALL(Products))

AOV All =
CALCULATE([AOV], ALL(Products))

AIPO All =
CALCULATE([AIPO], ALL(Products))

Total Customers All =
CALCULATE([Total Customers], ALL(Customers))

ARPC All =
CALCULATE([ARPC], ALL(Customers))

Total Discount Given =
CALCULATE(
    SUMX(Sales, Sales[Discount] * Sales[Product Amount]),
    ALL(Products)
)

📊 Dashboard Pages
📄 Page 1 – KPIs

Title: ECommerce Performance – Key Performance Indicators

KPI Cards

Total Sales / Total Sales All

Total Quantity Sold / Total Quantity Sold All

Total Orders / Total Orders All

AOV / AOV All

AIPO / AIPO All

Total Customers / Total Customers All

ARPC / ARPC All

Slicers

Product Category

Product Sub-Category

Table

Sub-Category

Total Orders

Total Sales

Line Chart

X-Axis: Date Hierarchy (Year → Quarter → Month)

Y-Axis: Total Sales

Secondary Axis: Total Quantity Sold

📄 Page 2 – Customer & Product

Title: ECommerce Performance – Customer & Product Segment

Charts

Stacked Bar Chart

Total Sales by Customer Segment & Region

Stacked Bar Chart

Total Sales by Product Category & Region

Card (New)

Total Customers

Total Orders

Total Sales
(by Customer Segment)

Card (New)

Total Customers

Total Orders

Total Sales
(by Product Category)

📄 Page 3 – Order & Profit Analysis

Title: ECommerce Performance – Order & Profit Analysis

Additional Measures
Total Profit =
[Total Sales] - SUMX(Sales, Sales[Discount] * Sales[Product Amount])

Profit Margin =
DIVIDE([Total Profit], [Total Sales])

Average Discount =
AVERAGE(Sales[Discount])

Delivery Time =
DATEDIFF(Sales[Order Date], Sales[Delivery Date], DAY)

Average Delivery Time =
AVERAGE(Sales[Delivery Time])

Visuals

Card: Total Profit, Profit Margin

Gauge: Average Discount

Matrix: Discount × Product Category → Total Orders

Donut Chart: Orders by Ship Mode

Gauge: Average Delivery Time

🚀 Key Business Insights Enabled

Discount impact on revenue and profitability

Customer and product contribution to sales

Order efficiency and delivery performance

Regional and category-level performance analysis

📁 Project Files

📊 Ecommerce_Sales_Charts.pbix – Power BI dashboard

📄 README.md – Project documentation

🧠 Skills Demonstrated

Power Query Transformations

Data Modeling & Relationships

DAX KPI Design

E-Commerce Metrics (AOV, AIPO, ARPC)

Business Dashboard Design

Analytical Storytelling
