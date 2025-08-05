# 🛒 Olist E-Commerce Power BI Dashboard

This project presents an interactive Power BI dashboard built using the [Olist Brazilian E-Commerce Public Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) from Kaggle. It showcases key metrics related to customer behavior, orders, delivery, payments, and sales performance.

---

## 📊 Project Overview

The dashboard is organized into **7 distinct report pages**, each focusing on a specific aspect of the e-commerce business. It is designed for both strategic insights and exploratory analysis.

---

## 🔖 Pages and Key Insights

### 1. Overview
- **KPI Cards:** Total Revenue, Total Orders, Total Customers, Avg Payment per Order
- **Pie Chart" & **Column chart:** Payment Method Breakdown
- **Line Chart:** Revenue Trend by Month
- **Bar Chart:** Top 5 Product Categories by Revenue

### 2. Sales Performance
- **KPI Card:** Total Products Sold
- **Bar Charts:** Revenue by Product Category, Revenue by Seller
- **Treemap:** Top-selling Products by Revenue
- **Line Chart:** Revenue Trend Over Time

### 3. Customer Analysis
- **KPI Cards:** Total Customers, Avg Revenue per Customer
- **Map:** Customers by City (with sentiment coloring)
- **Bar/Donut Charts:** Customers by Region/State

### 4. Delivery & Operations
- **KPI Cards:** Avg Delivery Time (Days),AVg Freight cost, Total Late Deliveries
- **Bar Charts:** Avg Delivery Time by Region, Late Deliveries by Region
- **Column Chart:** Top 5 Region by AVg Freight Cost
- **Table:** Orders: On-Time vs. Estimated Delivery Overview


### 5. Reviews & Satisfaction
- **KPI Card:** Average Review Score
- **Bar Charts:** Review Score Distribution
- **Map:** Customer Review Sentiment by Region
- **Donut Chart:** 
- **Scatter Plot:** Delivery Time vs Review Score

### 6. Payment Analysis
- **KPI Cards:** Total Payment, AVg Payment per Order, Max Payment per Order
- **Donut Chart** & **Column Chart:** Total Payment and AVg Payment by Type
- **Bar Chart:** Payment by Region and Year
- **Line Chart:** Payment over Time

### 7. Filters / Controls
A slicer panel to control filters across pages:
- **Slicers include:** Date, Product Category, State/City, Seller, Payment Type

---

## 🧮 DAX Measures Used

A number of DAX measures were used to drive the KPIs and visuals across the report. Below are some key examples:

-- Total Revenue
`Total Revenue = SUM('Order Items'[payment_value])`

-- Avg Delivery Time (Days)
`Avg Delivery Time (Days) = 
    AVERAGEX(orders, DATEDIFF(orders[order_purchase_date], orders[order_delivered_date], DAY))`

-- Review Sentiment Classification
`Review_Sentiment = 
    SWITCH(
        TRUE(),
        'order_reviews'[review_score] >= 4, "Positive",
        'order_reviews'[review_score] = 3, "Neutral",
        'order_reviews'[review_score] < 3, "Negative",
        "Unknown"
    )`

-- Total Product Sold
`Total Product Sold = COUNTROWS(order_items)`


---

## 🔗 Data Model Relationships

- **Star Schema** with a central `Orders` table.
- Bridging relationships via `Order Items` to connect `Products` and `Sellers`.
- Custom **Date Table** created using `CALENDAR()` and marked as official date table.

---

## 🎨 Design and UI Features

- **Slicer Syncing**: Implemented for consistent filters across pages (via Sync Pane → checked both "eye" and "sync" icons).
- **Icons** and KPI Cards for maximum readability.
- **Custom Color Scheme**: Uniform revenue color (green) across visuals.
- **Navigation**: Text box hyperlinks to switch between report tabs.

---

## 📌 Tools & Technologies

- Power BI Desktop
- DAX (Data Analysis Expressions)
- Power Query (for cleaning and transforming)
- Relationship modeling & Date Intelligence

---

## 📈 Business Value

This dashboard allows stakeholders to:
- Identify top-performing products and sellers
- Monitor delivery performance and delays
- Analyze customer satisfaction across regions
- Understand payment trends and revenue contributions
- Track sales growth trends month-over-month

---

## 📬 Contact

**Nayeem Ibn Ali**  
📧 [YourEmail@example.com]  
🔗 [LinkedIn Profile] | [GitHub Repository]

---



