# Portfolio-Gonzalo-Rodriguez-Spuch

# Sales Performance & Product Profitability Analysis

**Data Analytics Portfolio Project | Power BI**

## Table of Contents

- [1. Project Overview](#1-project-overview)
- [2. Project Goals](#2-project-goals)
- [3. Dataset Structure](#3-dataset-structure)
- [4. Executive Summary](#4-executive-summary)
- [5. Dashboard Analysis](#5-dashboard-analysis)
  - [a. Sales Performance](#a-sales-performance)
  - [b. Product Profitability](#b-product-profitability)
- [6. Key Performance Indicators](#6-key-performance-indicators)
- [7. Business Questions](#7-business-questions)
- [8. Technical Details](#8-technical-details)
- [9. Caveats and Assumptions](#9-caveats-and-assumptions)

---

## 1. Project Overview

Understanding sales performance and product profitability is essential for making informed business decisions. However, sales data becomes significantly more valuable when it is transformed into meaningful indicators that reveal revenue trends, product performance, cost structures, and differences across markets.

This project uses Power BI to develop an interactive sales analytics solution focused on two complementary areas: overall sales performance and product profitability.

The analysis combines sales transactions with product, customer, reseller, date, and sales territory information to explore business performance from multiple perspectives.

The project includes data preparation, data modeling, DAX measures, and interactive visualizations designed to support data-driven decision-making.

The resulting dashboard is organized into two main sections:

- **Sales Performance:** An overview of revenue trends, geographic performance, product categories, and sales volume.
- **Product Profitability:** An analysis of sales, product costs, gross profit, and the products contributing most to revenue.

This project demonstrates how business intelligence tools can transform transactional data into a structured analytical solution that helps identify patterns, evaluate performance, and generate actionable business insights.

---

## 2. Project Goals

The project was designed around three main objectives.

### 1. Sales Performance Analysis

- Track total sales and sales trends over time.
- Compare sales performance across countries and territories.
- Evaluate sales distribution across product categories.
- Explore how performance changes across fiscal years.

### 2. Product Profitability Analysis

- Compare total sales against product costs.
- Calculate gross profit using sales and product cost data.
- Identify product categories with higher gross profit.
- Highlight products that contribute most to revenue.
- Explore the relationship between sales and costs.

### 3. Business Intelligence and Data Visualization

- Build an analytical data model connecting sales transactions with relevant business dimensions.
- Create reusable DAX measures for key performance indicators.
- Develop interactive dashboards that allow users to explore the data through filters and visual interactions.
- Present business information in a clear and accessible format to support decision-making.

---

## 3. Dataset Structure

The project uses a relational sales dataset organized into seven tables. These tables contain transactional information and descriptive attributes that allow sales performance to be analyzed by time, geography, product, customer, and reseller.

### Table: `Sales_data`

The main fact table containing sales transaction data.

Key fields include:

- `SalesOrderLineKey`: Identifier for each sales order line.
- `ResellerKey`: Identifier linking a transaction to a reseller.
- `CustomerKey`: Identifier linking a transaction to a customer.
- `ProductKey`: Identifier linking a transaction to a product.
- `OrderDateKey`: Key used to connect sales transactions to the date dimension.
- `SalesTerritoryKey`: Identifier linking transactions to a sales territory.
- `Order Quantity`: Number of units sold.
- `Unit Price`: Selling price per unit.
- `Extended Amount`: Extended sales amount.
- `Unit Price Discount Pct`: Discount percentage applied to the unit price.
- `Product Standard Cost`: Standard cost per product.
- `Total Product Cost`: Total product cost associated with the sales line.
- `Sales Amount`: Sales amount used to calculate total revenue.

This table provides the numerical measures required for sales, volume, cost, and profitability analysis.

### Table: `Sales Order_data`

Contains additional information about sales orders and sales channels.

Key fields include:

- `SalesOrderLineKey`: Key linking the table to the sales fact table.
- `Channel`: Sales channel.
- `Sales Order`: Sales order identifier.
- `Sales Order Line`: Sales order line identifier.

This table provides additional context for analyzing sales transactions.

### Table: `Date_data`

Provides the time attributes required for temporal analysis.

Key fields include:

- `DateKey`
- `Date`
- `Fiscal Year`
- `Fiscal Quarter`
- `Month`
- `Full Date`
- `MonthKey`

The date dimension enables monthly trend analysis and comparisons across fiscal periods.

### Table: `Product_data`

Contains descriptive information about the products being sold.

Key fields include:

- `ProductKey`
- `SKU`
- `Product`
- `Standard Cost`
- `Color`
- `List Price`
- `Model`
- `Subcategory`
- `Category`

This table supports product-level and category-level performance analysis.

### Table: `Customer_data`

Contains customer attributes for analyzing sales by customer and geographic location.

Key fields include:

- `CustomerKey`
- `Customer ID`
- `Customer`
- `City`
- `State-Province`
- `Country-Region`
- `Postal Code`

### Table: `Reseller_data`

Contains reseller information that can be used to analyze sales across business partners.

Key fields include:

- `ResellerKey`
- `Reseller ID`
- `Business Type`
- `Reseller`
- `City`
- `State-Province`
- `Country-Region`
- `Postal Code`

### Table: `Sales Territory_data`

Contains geographic attributes associated with sales territories.

Key fields include:

- `SalesTerritoryKey`
- `Region`
- `Country`
- `Group`

This dimension allows users to compare sales performance across geographic markets.

### Data Model

The data model connects the sales fact table to the relevant descriptive tables through key fields.

The main analytical dimensions are:

- Date
- Product
- Customer
- Reseller
- Sales Territory

This structure supports analysis across multiple business dimensions while maintaining a central source for transactional metrics.

---

## 4. Executive Summary

This project develops an interactive Power BI dashboard to evaluate sales performance and product profitability.

The analysis focuses on revenue, sales volume, product costs, and gross profit, providing an overview of business performance across time periods, geographic markets, and product categories.

The dashboard includes two complementary analytical views:

- **Sales Performance:** Tracks revenue trends over time and compares performance across countries, territories, and product categories.
- **Product Profitability:** Evaluates sales against product costs, calculates gross profit, and identifies products contributing most to revenue.

The project also incorporates interactive fiscal-year filtering, allowing users to explore changes in performance across different periods.

Rather than focusing exclusively on total revenue, the analysis combines sales and cost metrics to provide a broader understanding of business performance.

The dashboard is intended to support exploratory analysis and demonstrate how structured data modeling, DAX calculations, and visualization can be combined to answer practical business questions.

---

## 5. Dashboard Analysis

### a. Sales Performance

The Sales Performance dashboard provides an overview of the company's sales activity.

Its purpose is to identify revenue trends, compare geographic markets, and understand how sales are distributed across product categories.

#### Core Visualizations

**1. Sales KPIs**

The dashboard displays key indicators, including:

- Total Sales
- Gross Profit
- Units Sold
- Total Costs

These indicators provide a high-level overview of sales performance and product economics.

**2. Monthly Sales Trend**

A line chart displays total sales over time.

This visualization helps identify changes in revenue, recurring patterns, and periods of higher or lower sales activity.

**3. Sales by Country or Territory**

A bar chart compares total sales across geographic markets.

This view helps identify the countries or territories contributing most to overall revenue.

**4. Sales by Product Category**

A column chart compares revenue across product categories.

This visualization provides an overview of the distribution of sales across different product groups.

**5. Fiscal Year Filter**

An interactive fiscal-year filter allows users to explore performance within selected periods.

The filter makes it possible to compare results and examine how revenue and other KPIs change over time.

### b. Product Profitability

The Product Profitability dashboard focuses on the relationship between revenue and product costs.

While revenue indicates the amount generated by sales, comparing it with product costs provides additional context for evaluating financial performance.

#### Core Visualizations

**1. Financial KPIs**

The dashboard displays:

- Total Sales
- Total Product Costs
- Gross Profit

These indicators provide a consolidated view of revenue, direct product costs, and gross profit.

**2. Gross Profit by Product Category**

A bar chart compares gross profit across product categories.

This visualization helps identify which categories contribute most to gross profit and which generate comparatively lower results.

**3. Top 10 Products by Sales**

A bar chart highlights the ten products with the highest sales.

This view helps identify products that contribute significantly to revenue and may deserve closer commercial attention.

**4. Sales vs. Costs**

A scatter chart explores the relationship between sales and product costs.

This visualization can help identify products or categories with different revenue and cost profiles.

The results should be interpreted alongside gross profit, since high sales alone do not necessarily imply high profitability.

---

## 6. Key Performance Indicators

The dashboard uses DAX measures to calculate the main business indicators.

| KPI | Definition | Business Purpose |
|---|---|---|
| Total Sales | Sum of `Sales Amount` | Measures total revenue recorded in the dataset. |
| Total Costs | Sum of `Total Product Cost` | Measures the total product costs associated with sales. |
| Gross Profit | Total Sales minus Total Costs | Evaluates sales performance after product costs. |
| Units Sold | Sum of `Order Quantity` | Measures sales volume. |
| Average Unit Price | Average of `Unit Price` | Provides an overview of recorded unit prices. |
| Average Discount | Average of `Unit Price Discount Pct` | Measures the average recorded discount percentage. |

### DAX Measures

The main calculations implemented in Power BI are:

**Total Sales**

```dax
Total Sales = SUM('Sales_data'[Sales Amount])
```

**Total Costs**

```dax
Total Costs = SUM('Sales_data'[Total Product Cost])
```

**Gross Profit**

```dax
Gross Profit = [Total Sales] - [Total Costs]
```

**Units Sold**

```dax
Units Sold = SUM('Sales_data'[Order Quantity])
```

**Average Unit Price**

```dax
Average Unit Price = AVERAGE('Sales_data'[Unit Price])
```

**Average Discount**

```dax
Average Discount = AVERAGE('Sales_data'[Unit Price Discount Pct])
```

These measures provide a reusable foundation for the dashboard calculations and respond to the filters applied in the report, subject to the data model relationships.

---

## 7. Business Questions

The dashboard is designed to help explore the following questions:

### Sales Performance

- How do sales evolve over time?
- Which countries or sales territories generate the highest revenue?
- Which product categories contribute most to total sales?
- How does performance change across fiscal years?
- How many units are sold, and how does sales volume vary?

### Product Profitability

- Which product categories generate the highest gross profit?
- Which products contribute most to total sales?
- How do product costs compare with sales revenue?
- Are high-revenue products also generating high gross profit?
- How do sales and profitability indicators change when different periods are selected?

These questions provide a starting point for identifying trends and potential areas for further investigation.

---

## 8. Technical Details

### Tools and Technologies

- **Power BI Desktop:** Dashboard development, data modeling, and visualization.
- **Power Query:** Data preparation and transformation.
- **DAX (Data Analysis Expressions):** Calculation of sales, costs, gross profit, sales volume, and average indicators.
- **Relational Data Modeling:** Integration of sales transactions with date, product, customer, reseller, and territory dimensions.
- **GitHub:** Project documentation and portfolio presentation.

### Workflow

The project follows a structured business intelligence workflow:

1. **Data Import:** Imported the source tables into Power BI.
2. **Data Preparation:** Reviewed the tables, column names, data types, and data quality in Power Query.
3. **Data Modeling:** Established relationships between the sales data and descriptive dimensions.
4. **Measure Development:** Created DAX measures for the main business KPIs.
5. **Dashboard Development:** Built two report pages focused on sales performance and product profitability.
6. **Validation:** Reviewed the displayed metrics, visual interactions, and filtering behavior.
7. **Documentation:** Prepared project documentation to explain the data structure, analytical objectives, and calculations.

---

## 9. Caveats and Assumptions

- The analysis is based on the structure and contents of the source dataset. Results should be interpreted within that context.
- Total Sales represents the sum of the `Sales Amount` field in the sales table.
- Total Costs represents the sum of `Total Product Cost`.
- Gross Profit is calculated as Total Sales minus Total Costs. It is a simplified gross profit measure and does not include operating expenses, taxes, financing costs, or other indirect expenses.
- Average Unit Price is calculated as the arithmetic average of recorded unit prices. It is not a weighted average based on units sold.
- Average Discount is calculated as the arithmetic average of recorded discount percentages.
- The results depend on the correctness of the source data, relationships, data types, and filter behavior in Power BI.
- No causal conclusions should be drawn from the visualizations alone. Additional investigation may be required to explain the reasons behind observed patterns.
- The project is intended for educational and portfolio purposes and demonstrates a business intelligence workflow rather than a complete financial audit.

---

**Author:** Data Analytics Portfolio Project

**Tools:** Power BI | Power Query | DAX

**Focus Areas:** Business Intelligence | Sales Analytics | Product Profitability | Data Visualization
