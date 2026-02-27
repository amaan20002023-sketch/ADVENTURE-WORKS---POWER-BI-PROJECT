# ADVENTURE-WORKS---POWER-BI-PROJECT
# AdventureWorks Sales & Returns Analysis – Power BI Project

[![Power BI](https://img.shields.io/badge/Tool-Power%20BI-blue)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/Language-DAX-purple)](https://learn.microsoft.com/en-us/dax/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This Power BI project analyzes the classic **AdventureWorks** sample dataset (bicycle manufacturer) focusing on **sales performance**, **returns**, **product categories**, and **customer behavior** from 2015–2017.

The dashboard emphasizes **Category-level** and **Product-level** insights with heavy use of **DAX measures**, relationships, time intelligence, and conditional formatting — perfect for practicing intermediate-to-advanced Power BI skills.

## Project Highlights

- Built **entirely in Power BI Desktop** (no external tools used for analysis)
- Star schema data model with proper relationships (Sales ↔ Products ↔ Categories ↔ Subcategories ↔ Calendar ↔ Customers ↔ Territories ↔ Returns)
- 20+ custom **DAX measures** for revenue, returns, bulk orders, weekend analysis, high-ticket orders, etc.
- Interactive dashboards with slicers, drill-through, tooltips, and conditional formatting
- Focus on **Category Analysis** and **Product Analysis** (as shown in your reference image)

## Key Analysis Areas & DAX Tasks Implemented

### Category Analysis
1. Total Revenue at category level  
   `Total Revenue = SUMX(Sales, Sales[OrderQuantity] * RELATED(Products[ProductPrice]))`

2. Total Quantity Sold at category level

3. Return Rate at category level  
   `Return Rate = DIVIDE([Total Qty Returned], [Total Qty Sold], 0)`

4. Identify category/subcategory/product with highest return rate

5. Total Qty Returned + Total Qty Sold per category

6. Number of **bulk orders** per category (orders where any product qty > 1)  
   `Bulk Orders = CALCULATE(COUNTROWS(Sales), Sales[OrderQuantity] > 1)`

7. % of bulk orders per category

8. High-ticket orders at category level (orders with price > overall average price)

9. Orders placed on **weekend** vs **weekday** at category level  
   (Using `WEEKDAY()` + `CALCULATE` filter modifiers)

10. Total high-ticket orders at category level

### Product Analysis
- Top products by revenue / quantity / return rate
- Drill-down from category → subcategory → product
- Return quantity vs sold quantity comparison
- Bulk & high-value product identification

### Other KPIs Created
- Total Orders, Total Quantity Sold, Total Returned Quantity
- Profit Margin, Return %, MoM/YoY growth (using time intelligence)
- Average Order Value, Average Selling Price

## Dashboard Pages
- **Home / Overview** – KPIs, revenue trend, top categories, return alerts
- **Category Analysis** – Detailed category breakdown, bulk orders, weekend vs weekday, high-ticket orders
- **Product Analysis** – Product hierarchy drill-down, return leaders, top performers
- **Customer Insights** – (Optional extension) Income, occupation, home ownership segmentation
- **Returns Deep Dive** – High-return products/subcategories, territory comparison

## Data Sources (All Loaded in Power BI)
- AdventureWorks_Sales_2015/2016/2017.csv
- AdventureWorks_Returns.csv
- AdventureWorks_Products.csv
- AdventureWorks_Product_Categories.csv
- AdventureWorks_Product_Subcategories.csv
- AdventureWorks_Calendar.csv
- AdventureWorks_Territories.csv
- CUSTOMERS.xlsx

→ Combined, cleaned, and related entirely inside **Power Query** and **Model** view.

## How to Use This Project

1. Clone the repository
   ```bash
  https://github.com/amaan20002023-sketch/ADVENTURE-WORKS---POWER-BI-PROJECT/blob/main/README.md
  Learning Takeaways

Advanced DAX: CALCULATE, DIVIDE, RELATED, FILTER, SUMX, time-intelligence functions
Handling weekend/weekday logic with WEEKDAY()
Bulk order & high-ticket filtering
Return rate calculation and ranking highest-return items
Effective star-schema modeling
Conditional formatting, drill-through pages, dynamic titles

Screenshots
Future Enhancements (Ideas)

Add What-If parameters for target return rate
Drill-through to individual product detail page
Add territory map visual
Create executive summary with cards & sparklines

About the Author
MOHDAMMAD AMAAN
Delhi, India
Aspiring Data Analyst / Power BI Developer
Feel free to fork, star ⭐, or open issues if you find bugs or want to suggest improvements!
Happy analyzing! 🚴‍♂️📊
