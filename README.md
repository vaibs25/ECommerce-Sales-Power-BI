# -ECommerce-Sales-Power-BI

Problem Description
For this module, you will now use the measures and modelled data to create visuals. If required, you’ll be creating more measures.


Requirements for visuals on PowerBI :

Open the Ecommerce_Sales PowerBI file.

Add additional measures

Name - Total Sales All

Name - Total Quantity Sold All

Name - Total Orders All

Name - AOV All

Name - AIPO All

Name - Total Customers All

Name - ARPC All

Name - Total Discount Given

Create Card & Visuals for KPIs page

Create Charts for Customer & Product page

Create Charts for Order & Profit Analysis page

Save and upload the Power BI file with the completed data visuals.

✅ Steps for PowerBI file submission
Checklist
Step & Task Description


In the same file as submitted for previous module : Creating Measures

Home table - Sales
Create Measures

Name - Total Sales All

Name - Total Quantity Sold All

Name - Total Orders All

Name - AOV All

Name - AIPO All

Name - Total Customers All

Name - ARPC All

Name - Total Discount Given

DAX → CALCULATE(SUMX(Sales, Sales[Discount] * Sales[Product Amount]), ALL(Products))
Create Card type visuals

Total Sales All

Total Quantity Sold All

Total Orders All

AOV All

AIPO All

Total Customers All

ARPC All

Total Sales

Total Quantity Sold

Total Orders

AOV

AIPO

Total Customers

ARPC

Add Slicer

Style - Vertical List

Field

Product Category

Product Sub-Category

Create Chart

Type - Table

Columns

Sub-Category

Total Orders

Total Sales

Create Chart

Type - Line

X-Axis - Date Hierarchy (Year, Quarter, Month)

Y-Axis - Total Sales

Secondary Y-Axis - Total Quantities Sold

Page 1 Rename Page → "KPIs"

Add text on top of page

"ECommerce Performance - Key Performance Indicators"
Add borders to all visuals

Align the KPIs and filter cleanly on the page

Create New Page → "Customer & Product"

Add text on top of page

"ECommerce Performance - Customer & Product Segment"
Create Chart

Type - Stacked bar chart

X-Axis - Total Sales

Y-Axis - Customers Segment

Legend - Region

Title - Total Sales by Regional Customers

Create Chart

Type - Stacked bar chart

X-Axis - Total Sales

Y-Axis - Product Category

Legend - Region

Title - Total Sales by Regional Products

Create Chart

Type - Card (New)

Data

Total Customers

Total Orders

Total Sales

Categories - Customers Segment

Create Chart

Type - Card (New)

Data

Total Customers

Total Orders

Total Sales

Categories - Products Category

Add borders to all visuals

Align the Charts cleanly on the page
Create New Page → "Order & Profit Analysis"

Add text on top of page

"ECommerce Performance - Order & Profit Analysis"
Create New measures : Home table - Sales

Name - Total Profit

DAX → [Total Sales] - SUMX(Sales, Sales[Discount]* Sales[Product Amount])
Name - Profit Margin

DAX → [Total Profit] / [Total Sales]
Name - Average Discount

DAX → AVERAGE(Sales[Discount])
Name - Delivery Time

Difference between Delivery Date and Order Date

Change Type - Whole Number

Name - Average Delivery Time

Home table - Sales

DAX → AVERAGE(Sales[Delivery Time])

Create Card type visuals

Total Profit

Profit Margin

Create Gauge type visuals

Value - Average Discount

Minimum value - Min of Discount

Maximum value - Max of Discount

Create Matrix visual

Rows - Discount (Sorted Desc)

Columns - Product [Category]

Values - Total orders

Create Chart

Type - Donut Chart

Legend - Ship Mode

Values - Total orders

Title - Distribution of orders by shipping method

Create Gauge type visuals

Value - Average Delivery Time

Minimum value - Min of Delivery Time

Maximum value - Max of Delivery Time

Add borders to all visuals

Align the Charts cleanly on the page
Save and Submit:

✅ Steps for PowerBI file submission
Expected Output

Page 1 - KPIs

image


Page 2 - Customer & Product

image


Page 3 - Order & Profit Analysis
