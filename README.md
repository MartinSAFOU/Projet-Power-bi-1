# 📊 Global Superstore Sales Performance Dashboard | Power BI

## Project Overview

This project consists of designing an interactive Business Intelligence dashboard in Power BI using the Global Superstore dataset.

The objective is to transform raw transactional data into a decision-support tool that enables stakeholders to monitor sales performance, identify growth opportunities, and evaluate regional and product profitability.

The dashboard is structured around two analytical pages:

- Executive Overview
- Sales & Performance Analysis

---

## Business Problem

The company needs a real-time reporting solution to monitor commercial performance and support strategic decision-making.

Key questions addressed:

- Are sales growing compared to previous years?
- Which regions generate the highest revenue?
- Which products contribute the most to sales?
- How do discounts impact performance?
- What are the main sales trends over time?

---

## Project Objectives

- Monitor key business KPIs
- Analyze sales trends and seasonality
- Compare performance Year-over-Year (YoY)
- Identify top-performing products and regions
- Support data-driven decision making

---

# Tools & Technologies

- Power BI Desktop
- Power Query
- DAX
- Data Modeling
- CSV Dataset

---

# Data Preparation

Data preparation was performed using Power Query.

### Main transformations

- Data type validation
- Date formatting
- Removal of duplicates
- Null value verification
- Creation of analytical columns:
  - Delivery Duration
  - Year
  - Month
  - Month Number
- Data standardization

---

# Data Model

A Star Schema was implemented to optimize performance and ensure scalability.

## Fact Table

### Fact_Sales

Contains transactional sales information:

- Order ID
- Sales
- Quantity
- Discount
- Shipping Cost
- Customer ID
- Product ID
- Geographic Key

---

## Dimension Tables

### Dim_Date

- Date
- Year
- Quarter
- Month
- Month Number

### Dim_Product

- Product Name
- Category
- Sub-Category

### Dim_Customer

- Customer Name
- Segment

### Dim_Geography

- Country
- Region
- State
- City
- Market

### Dim_Shipping

- Ship Mode
- Order Priority

---

# DAX Measures

Key measures created:

```DAX
Total Sales =
SUM(Fact_Sales[Sales])
```

```DAX
Total Orders =
DISTINCTCOUNT(Fact_Sales[Order ID])
```

```DAX
Average Order Value =
DIVIDE(
    [Total Sales],
    [Total Orders]
)
```

```DAX
Sales N-1 =
CALCULATE(
    [Total Sales],
    SAMEPERIODLASTYEAR(Dim_Date[Date])
)
```

```DAX
Sales Growth % =
DIVIDE(
    [Total Sales] - [Sales N-1],
    [Sales N-1]
)
```

```DAX
Average Discount =
AVERAGE(Fact_Sales[Discount])
```

---

# Dashboard Structure

## Page 1 — Executive Overview

### Purpose

Provide a high-level view of business performance for management and decision-makers.

### KPIs

- Total Sales
- Total Orders
- Average Order Value
- Sales Growth %
- Average Discount

### Visualizations

#### Sales Trend Analysis

Line chart showing sales evolution over time.

**Business Value**
- Detect seasonality
- Identify growth periods
- Monitor performance trends

---

#### Sales vs Previous Year

Combined Column & Line Chart

- Sales (Current Year)
- Sales Growth %

**Business Value**
- Measure YoY performance
- Track growth dynamics

---

#### Sales by Customer Segment

Donut Chart

**Business Value**
- Understand customer contribution
- Identify the most valuable customer segments

---

#### Geographic Sales Analysis

Map Visualization

**Business Value**
- Compare regional performance
- Identify strategic markets

---

## Key Insights Generated

- Overall business growth trend
- Regional revenue concentration
- Customer segment contribution
- Sales performance evolution

---

# Page 2 — Sales & Performance Analysis

### Purpose

Provide detailed operational insights to support tactical decisions.

---

### Top 10 Products

Bar Chart

**Business Value**
- Identify best-selling products
- Support inventory planning
- Highlight revenue drivers

---

### Discount Impact Analysis

Scatter Plot

Measures:
- Sales
- Discount

**Business Value**
- Evaluate pricing strategy
- Identify excessive discounting

---

### Regional Performance Analysis

Treemap

Measures:
- Sales

**Business Value**
- Compare market performance
- Prioritize growth opportunities

---

### Shipping Performance

Column Chart

Measures:
- Average Delivery Duration

**Business Value**
- Monitor operational efficiency
- Improve customer experience

---

### Detailed Sales Table

Includes:

- Product
- Category
- Region
- Sales
- Quantity
- Discount

Features:

- Sorting
- Filtering
- Drill-down analysis

---

# 💡 Business Insights

The dashboard enables stakeholders to:

### Sales Monitoring

Track business performance through key KPIs.

### Regional Analysis

Identify high-performing and underperforming regions.

### Product Performance

Determine revenue-generating products.

### Growth Tracking

Compare current results with previous periods.

### Pricing Evaluation

Assess the impact of discounts on sales performance.

🚀 Key Skills Demonstrated

### Business Intelligence

- KPI Design
- Executive Reporting
- Dashboard Development

### Data Analytics

- Trend Analysis
- Sales Performance Analysis
- Business Insights Generation

### Data Modeling

- Star Schema Design
- Fact & Dimension Modeling

### Power BI

- Power Query
- DAX
- Interactive Visualizations
- Drill-down Analysis

---

# 📂 Repository Structure

```text
📁 data
    └── Global_Superstore.csv

📁 screenshots
    ├── page1.png
    └── page2.png

📁 pbix
    └── Sales_Performance_Dashboard.pbix

README.md
```

---

# Author

Data Analyst Portfolio Project

Built with Power BI to demonstrate end-to-end Business Intelligence capabilities, from data preparation and modeling to dashboard design and business storytelling.
