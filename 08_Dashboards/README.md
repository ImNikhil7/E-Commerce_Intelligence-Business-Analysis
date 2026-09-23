# ShopSphere — Business Intelligence Dashboard

## Overview

**ShopSphere Business Intelligence** is an end-to-end Business Analysis and Power BI reporting solution built to transform raw e-commerce data into actionable business insights.

The dashboard brings together sales, customers, products, categories, operations, delivery performance, customer satisfaction, marketing funnel performance, and geographic performance into a structured multi-page Power BI report.

The objective is not only to visualize historical performance, but to provide a business-oriented view of key performance indicators, operational risks, customer behavior, and growth opportunities.

---

## Dashboard Objective

The ShopSphere dashboard was designed to answer five major business questions:

1. How is the overall business performing?
2. Where are sales and customers concentrated?
3. Which products and categories are performing well or poorly?
4. What operational and customer-experience problems require attention?
5. Which marketing channels and customer segments contribute most to business outcomes?

The dashboard is designed for business stakeholders who need to move from raw data to insight without requiring access to the underlying analytical code.

---

## Dashboard Structure

The Power BI report contains the following pages:

| # | Dashboard Page | Purpose |
|---|---|---|
| 1 | Executive Overview | High-level business performance |
| 2 | Sales & Revenue Intelligence | Revenue, orders, AOV, and sales trends |
| 3 | Product & Category Performance | Category sales, freight, reviews, and delivery performance |
| 4 | Customer Intelligence & Retention | Customer mix, repeat behavior, frequency, and customer value |
| 5 | Operations & Delivery Performance | Delivery speed, late orders, variance, and operational risk |
| 6 | Customer Satisfaction | Review performance and relationship between delivery and satisfaction |
| 7 | Marketing & Sales Funnel | MQLs, closed deals, conversion, lead types, and business segments |
| 8 | Geographic Customer Intelligence | State-level customer, sales, and customer-value analysis |
| 9 | KPI Validation | Validation of key business metrics |
| 10 | Predictive Insights | Planned extension for future forecasting and predictive analysis |

> **Note:** The Predictive Insights page is a planned extension of the current descriptive/diagnostic dashboard and is not part of the current dashboard release.

---

# 1. Executive Overview

The Executive Overview provides a consolidated view of the overall business.

### Key KPIs

- Total Orders
- Total Sales
- Average Order Value
- Repeat Customer Rate
- Late Delivery Rate

### Key Visuals

- Delivered Sales by Month
- Delivered Orders by Month
- Top 10 Customer States by Delivered Sales
- Total Orders by Order Status
- Interactive date, state, and order-status filters

### Business Purpose

This page is designed as the primary entry point for management and decision-makers.

It provides a quick understanding of:

- business scale
- revenue performance
- order activity
- customer retention
- delivery performance
- geographic sales concentration

---

# 2. Sales & Revenue Intelligence

This dashboard focuses on the financial and sales performance of the marketplace.

### Key KPIs

- Total Orders
- Total Sales
- Average Order Value
- Product Sales
- Freight Value

### Key Visuals

- Orders vs Sales Trend
- Average Order Value Trend
- Monthly Delivered Sales
- Order Status — Orders & Sales
- Delivered Sales by Customer State

### Business Questions Answered

- How are sales changing over time?
- What is the average value of an order?
- How much value comes from products versus freight?
- Which states contribute the most delivered sales?
- How are orders distributed across order statuses?

---

# 3. Product & Category Performance

This page evaluates product-category performance from multiple business perspectives.

### Key KPIs

- Product Sales
- Freight Value
- Freight Burden %
- Average Review Score
- Late Delivery Rate

### Key Visuals

- Top Categories by Total Sales
- Category Performance Matrix
- Freight Burden by Category
- Bottom 10 Categories by Review Score
- Top 10 Categories by Late Delivery Rate

### Category-Level Metrics

The category analysis includes:

- Average Review
- Freight Burden
- Items
- Late Delivery Rate
- Sales

### Business Purpose

This page helps identify:

- high-performing categories
- categories with weak customer satisfaction
- categories with high logistics cost
- categories with delivery problems
- categories requiring operational attention

---

# 4. Customer Intelligence & Retention

This page focuses on customer behavior, repeat purchasing, and customer value.

### Key KPIs

- Unique Customers
- Repeat Customers
- Repeat Customer Rate
- Repeat Customer Sales
- Average Repeat Customer Sales

### Key Visuals

- Customer Mix — One-Time vs Repeat
- Sales Contribution by Customer Type
- Customer Purchase Frequency
- Top 10 Customer States by Sales
- Average Sales per Customer Type
- Repeat Customer Frequency

### Business Purpose

This dashboard helps identify:

- the size of the customer base
- the proportion of repeat customers
- the value contributed by repeat customers
- customer purchase frequency
- high-value customer groups
- geographic customer concentration

The current dashboard intentionally focuses on actionable retention metrics rather than relying on a complex cohort visualization.

---

# 5. Operations & Delivery Performance

This page focuses on operational execution and delivery quality.

### Key KPIs

- Total Delivered Orders
- Late Orders
- Late Delivery Rate
- Average Delivery Days
- Average Delivery Variance (Days)

### Key Visuals

- Late Delivery Rate by Customer State
- Average Delivery Time by State
- Average Delivery Variance Over Time
- On-Time vs Late Deliveries
- Delivery Performance vs Customer Satisfaction

### Business Purpose

This page helps identify:

- states with high delivery risk
- states with longer delivery times
- changes in delivery performance over time
- the proportion of late deliveries
- the relationship between delivery performance and customer satisfaction

### Delivery Variance Definition

The dashboard uses delivery variance to compare actual delivery performance against the estimated delivery timeline.

The sign of the metric should be interpreted according to the project's documented calculation definition.

---

# 6. Customer Satisfaction

This page analyzes customer review performance and its relationship with delivery quality.

### Key KPIs

- Average Review Score
- Late Order Review Score
- On-Time Order Review Score

### Current Validated Values

| KPI | Value |
|---|---:|
| Average Review Score | 4.09 |
| On-Time Order Review Score | 4.29 |
| Late Order Review Score | 2.27 |

### Key Visuals

- Customer Satisfaction: On-Time vs Late
- Bottom 10 Categories by Review Score
- Top 10 Categories by Late Delivery Rate
- Category Satisfaction Risk Table

### Business Purpose

The dashboard demonstrates the relationship between operational performance and customer experience.

A key insight is that late orders have substantially lower average review scores than on-time orders.

---

# 7. Marketing & Sales Funnel

This page analyzes lead generation and downstream sales conversion.

### Key KPIs

- Total MQLs
- Closed Deals
- MQL to Closed Conversion

### Current Validated Values

| KPI | Value |
|---|---:|
| Total MQLs | 8,000 |
| Closed Deals | 842 |
| MQL → Closed Conversion | 10.53% |

### Key Visuals

- MQL → Closed Conversion by Origin
- MQL → Closed Deal Funnel
- Closed Deals by Business Type
- Closed Deals by Lead Type
- Closed Deals by Lead Behaviour Profile
- Top 10 Business Segments by Closed Deals

### Business Purpose

This page helps identify:

- high-converting lead origins
- dominant lead types
- successful business segments
- business-type distribution
- lead behavior patterns
- marketing-to-sales conversion performance

Missing or unknown values are explicitly represented as `Unknown / Missing` where applicable.

---

# 8. Geographic Customer Intelligence

This page provides a deeper geographic analysis of customer value and sales concentration.

### Key KPIs

- Unique Delivered Customers
- Delivered Sales
- Delivered Orders
- Average Sales per Customer
- Repeat Customer Rate

### Key Visuals

- Top 10 States by Delivered Sales
- Top 10 States by Customer Count
- Top 10 States by Sales per Customer
- State Performance Table

### State Performance Metrics

The detailed state analysis includes:

- Unique Delivered Customers
- Delivered Sales
- Sales per Customer
- Repeat Customer Rate

### Business Purpose

This dashboard helps management understand:

- where the customer base is concentrated
- where revenue is concentrated
- which states have high customer value
- where retention performance differs geographically

---

# 9. KPI Validation

The KPI Validation page serves as a quality-assurance layer for the dashboard.

It contains the major business KPIs used throughout the report.

### Validated KPIs

| KPI | Value |
|---|---:|
| Total Orders | 99,441 |
| Delivered Orders | 96,478 |
| Total Sales | 15,419,773.75 |
| Average Order Value | 159.83 |
| Unique Customers | 93,358 |
| Repeat Customers | 2,801 |
| Repeat Customer Rate | 3.00% |
| Late Orders | 6,534 |
| Late Delivery Rate | 6.77% |
| Average Review Score | 4.09 |
| Freight Burden | 16.63% |

This page is primarily intended for analytical validation rather than executive presentation.

---

# Data & Analytical Model

The dashboard is built around a consolidated order-level analytical model.

### Core Fact Table

- `Fact_Orders`

### Supporting / Staging Tables

- `Stg_Order_Items`
- `Stg_Products`
- `Stg_Category_Translation`

### Analytical Tables

- `Category_Sales`
- `Category_Experience`
- `Customer_Summary`
- `Cohort_Retention`

### Marketing Tables

- `Marketing_MQL`
- `Closed_Deals`

### Supporting Dimensions

- `Dim_Date`
- `Dim_Category`

### Measures

A centralized `_Measures` table is used to store major Power BI measures.

This helps maintain consistency across dashboards and reduces duplicated business logic.

---

# Key Business Metrics

The dashboard uses a consistent set of business KPIs.

### Sales

- Total Orders
- Delivered Orders
- Delivered Sales
- Product Sales
- Freight Value
- Average Order Value

### Customers

- Unique Customers
- Repeat Customers
- Repeat Customer Rate
- Repeat Customer Sales
- Average Sales per Customer

### Operations

- Late Orders
- Late Delivery Rate
- Average Delivery Days
- Average Delivery Variance

### Customer Experience

- Average Review Score
- On-Time Order Review Score
- Late Order Review Score

### Marketing

- Total MQLs
- Closed Deals
- MQL → Closed Conversion

---

# Dashboard Navigation

The report uses page navigation through the Power BI page tabs and Home buttons.

The Home button available on the major dashboard pages returns the user to:

> **Executive Overview**

This allows users to move from detailed departmental analysis back to the main business overview.

---

# Interactivity

The report supports interactive analysis through:

- Date filtering
- Customer state filtering
- Order-status filtering
- Cross-filtering between compatible visuals
- Dashboard page navigation
- Detailed table exploration

The report is designed so that users can move from high-level KPIs to detailed departmental analysis.

---

# Business Insight Themes

The dashboard is structured around several major insight themes discovered during the analysis:

### 1. Sales Performance

The business generates substantial sales volume, with delivered sales forming the primary revenue base.

### 2. Customer Retention

Repeat customers represent a relatively small share of the customer base, while repeat customers demonstrate higher average customer value.

### 3. Delivery Risk

A measurable proportion of delivered orders are late, with substantial variation across geographic regions and product categories.

### 4. Customer Satisfaction

Late deliveries are associated with significantly lower review scores than on-time deliveries.

### 5. Category Risk

Some categories combine weaker customer satisfaction with elevated delivery risk and therefore require closer monitoring.

### 6. Marketing Conversion

Marketing and sales performance differs substantially across lead origins, lead types, business segments, and business profiles.

### 7. Geographic Concentration

Sales and customer activity are concentrated in a relatively small number of states, while customer value varies across regions.

---

# Future Predictive Analytics Extension

The current report is primarily a **descriptive and diagnostic BI solution**.

The next analytical extension is predictive modeling.

## Planned Predictive Models

Potential models include:

- Sales Forecasting
- Order Volume Forecasting
- Delivery Delay Prediction
- Customer Repeat-Purchase Prediction
- Customer Churn/Risk Prediction
- Category Demand Forecasting

The exact models will be selected based on data quality, business value, and model validation results.

---


## One thing I'd change before putting that README into GitHub

I deliberately wrote **"Planned Extension"** for the predictive page rather than pretending it already exists. That's important for credibility.

When we actually build the models, we'll update the README from:

> Predictive Analytics (Planned Extension)

to:

> Predictive Analytics

and document the actual model(s), features, validation metrics, predictions, and Power BI integration.

---

# Now, about your model/dashboard doubt in more depth

Your concern is exactly why I recommend **integrating predictions into Power BI rather than leaving the model as a Python notebook**.

### We will have three layers

**Layer 1 — Historical BI**

Your current 9 dashboards.

``text
What happened?


# How Predictive Models Will Work with the Existing Dashboard

The predictive models will **not replace the current dashboard**.

Instead, the project will use the following pipeline:

``text
Historical Data
      ↓
Feature Engineering
      ↓
Model Training
      ↓
Model Validation
      ↓
Future Predictions
      ↓
Prediction Output Table
      ↓
Power BI
      ↓
Predictive Insights Dashboard
