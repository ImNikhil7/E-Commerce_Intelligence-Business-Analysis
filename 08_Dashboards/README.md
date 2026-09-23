# ShopSphere — Business Intelligence & Predictive Analytics Dashboard

## Overview

**ShopSphere Business Intelligence** is an end-to-end Business Analysis, Business Intelligence, and Predictive Analytics solution built to transform e-commerce data into understandable and actionable business insights.

The Power BI report brings together:

- Sales and revenue performance
- Customer behavior and retention
- Product and category performance
- Operations and delivery performance
- Customer satisfaction
- Marketing and sales funnel performance
- Geographic customer intelligence
- KPI validation
- Historical sales forecasting

The report is designed for business stakeholders who want to move from raw data to insights without needing to work directly with the underlying Python notebooks or data-processing code.

---

# Dashboard Objective

The ShopSphere dashboard was designed to answer the following business questions:

1. How is the overall business performing?
2. Where are sales and customers concentrated?
3. Which product and category areas are performing strongly or showing risk?
4. What operational issues are affecting delivery and customer experience?
5. How does delivery performance relate to customer satisfaction?
6. How are marketing leads moving through the sales funnel?
7. Which geographic areas contribute the most sales and customer value?
8. Can historical sales data be used to estimate future sales?

The dashboard combines descriptive and diagnostic analysis with a predictive sales-forecasting page.

---

# Dashboard Structure

The current Power BI report contains **10 pages**:

| # | Dashboard Page | Purpose |
|---|---|---|
| 1 | KPI Validation | Validate the major business KPIs |
| 2 | Executive Overview | High-level view of overall business performance |
| 3 | Sales & Revenue | Sales trends, orders, AOV, product sales and freight |
| 4 | Product & Category | Category sales, freight burden, reviews and delivery performance |
| 5 | Customer Intelligence | Customer mix, repeat behavior, frequency and customer value |
| 6 | Operations & Delivery | Delivery speed, late orders and delivery variance |
| 7 | Customer Satisfaction | Review performance and delivery/customer-experience relationship |
| 8 | Marketing & Sales Funnel | MQLs, closed deals, conversion and lead characteristics |
| 9 | Geographic Customer Intelligence | State-level customer, sales and customer-value analysis |
| 10 | Predictive Insights — Sales Forecast | Historical sales and six-month forecast |

---

# 1. KPI Validation

The KPI Validation page is the quality-assurance layer of the report.

It is used to verify that the major dashboard numbers match the analytical calculations before they are presented to business users.

## Main KPIs

- Total Orders
- Delivered Orders
- Delivered Sales
- Average Order Value
- Unique Delivered Customers
- Repeat Customers
- Repeat Customer Rate
- Late Orders
- Late Delivery Rate
- Average Review Score
- Freight Burden

## Validated Values

| KPI | Value |
|---|---:|
| Total Orders | 99,441 |
| Delivered Orders | 96,478 |
| Delivered Sales | ₹15,419,773.75 |
| Average Order Value | ₹159.83 |
| Unique Delivered Customers | 93,358 |
| Repeat Customers | 2,801 |
| Repeat Customer Rate | 3.00% |
| Late Orders | 6,534 |
| Late Delivery Rate | 6.77% |
| Average Review Score | 4.09 |
| Freight Burden | 16.63% |

## Business Purpose

This page is primarily intended for analytical validation and quality assurance rather than executive presentation.

---

# 2. Executive Overview

The Executive Overview is the main management view of the report.

It provides a quick understanding of the overall business without requiring the user to open multiple detailed pages.

## Key KPIs

- Total Orders
- Delivered Sales
- Average Order Value
- Repeat Customer Rate
- Late Delivery Rate

## Key Visuals

- Delivered Sales by Month
- Delivered Orders by Month
- Top Customer States by Delivered Sales
- Orders by Order Status
- Key business KPI cards
- Interactive filters

## Business Purpose

This page helps answer:

- How large is the business?
- How are sales changing over time?
- How many orders are being delivered?
- How strong is customer retention?
- How is delivery performing?
- Where is business activity concentrated geographically?

---

# 3. Sales & Revenue

This page focuses on sales performance and the main financial components of delivered-order value.

## Key KPIs

- Total Orders
- Delivered Sales
- Average Order Value
- Product Sales
- Freight Value

## Key Visuals

- Monthly sales trends
- Order and sales trends
- Average Order Value trend
- Orders and sales by order status
- Delivered sales by customer state

## Business Questions Answered

- How are sales changing over time?
- What is the average value of a delivered order?
- How much value comes from products?
- How much value comes from freight?
- Which states contribute more delivered sales?
- How are orders distributed across statuses?

---

# 4. Product & Category

This page evaluates product-category performance from both financial and operational perspectives.

## Key KPIs

- Product Sales
- Freight Value
- Freight Burden %
- Average Review Score
- Late Delivery Rate

## Key Visuals

- Top categories by total sales
- Category performance matrix
- Freight burden by category
- Bottom categories by review score
- Categories with high late-delivery rates

## Category-Level Metrics

The category analysis includes:

- Sales
- Items
- Product Sales
- Freight Value
- Freight Burden
- Average Review
- Late Delivery Rate

## Business Purpose

This page helps identify:

- High-sales categories
- Categories with high logistics costs
- Categories with lower customer satisfaction
- Categories with elevated late-delivery rates
- Areas that may require operational attention

---

# 5. Customer Intelligence

This page focuses on customer behavior, repeat purchasing and customer value.

## Key KPIs

- Unique Delivered Customers
- Repeat Customers
- Repeat Customer Rate
- Repeat Customer Sales
- Average Repeat Customer Sales
- Average Sales per Customer

## Key Visuals

- One-Time vs Repeat Customer Mix
- Sales Contribution by Customer Type
- Customer Purchase Frequency
- Top Customer States by Sales
- Average Sales per Customer Type
- Repeat Customer Frequency

## Business Purpose

This page helps answer:

- How many customers placed only one order?
- How many customers returned?
- What share of customers are repeat customers?
- How much sales value is associated with repeat customers?
- What purchase-frequency patterns exist?
- Which customer groups contribute more value?

The current dashboard intentionally focuses on clear, actionable retention metrics rather than relying on a complex cohort-retention visual.

---

# 6. Operations & Delivery

This page focuses on operational execution and delivery performance.

## Key KPIs

- Total Delivered Orders
- Late Orders
- Late Delivery Rate
- Average Delivery Days
- Average Delivery Variance

## Key Visuals

- Late Delivery Rate by State
- Average Delivery Time by State
- Average Delivery Variance Over Time
- On-Time vs Late Deliveries
- Delivery Performance vs Customer Satisfaction

## Business Purpose

This page helps identify:

- Geographic areas with higher late-delivery rates
- Areas with longer delivery times
- Changes in delivery performance over time
- The overall share of late deliveries
- The relationship between delivery performance and customer satisfaction

## Delivery Variance

Delivery variance compares the actual delivery timeline with the estimated delivery timeline using the project's documented calculation.

Interpretation of positive or negative values should follow the project's calculation definition rather than assuming a sign meaning without checking the formula.

---

# 7. Customer Satisfaction

This page analyzes customer review performance and its relationship with delivery experience.

## Key KPIs

- Average Review Score
- On-Time Order Review Score
- Late Order Review Score

## Validated Values

| KPI | Value |
|---|---:|
| Average Review Score | 4.09 |
| On-Time Order Review Score | 4.29 |
| Late Order Review Score | 2.27 |

## Key Visuals

- On-Time vs Late Customer Satisfaction
- Category review performance
- Categories with elevated late-delivery rates
- Category satisfaction/risk table

## Business Purpose

The page helps understand customer experience and how it differs across operational conditions.

A major descriptive finding is that late orders have substantially lower average review scores than on-time orders in the analyzed data.

---

# 8. Marketing & Sales Funnel

This page analyzes marketing-qualified leads and their movement toward closed deals.

## Key KPIs

- Total MQLs
- Closed Deals
- MQL-to-Closed Conversion

## Validated Values

| KPI | Value |
|---|---:|
| Total MQLs | 8,000 |
| Closed Deals | 842 |
| MQL → Closed Conversion | 10.53% |

## Key Visuals

- MQL-to-Closed conversion by origin
- MQL-to-Closed funnel
- Closed deals by business type
- Closed deals by lead type
- Closed deals by lead behaviour
- Top business segments by closed deals

## Business Purpose

This page helps identify:

- Differences in conversion across lead origins
- Dominant lead types
- Business segments contributing closed deals
- Business-type distribution
- Lead behaviour patterns
- Marketing-to-sales conversion performance

Missing or unknown values are explicitly represented as `Unknown / Missing` where applicable.

---

# 9. Geographic Customer Intelligence

This page provides a deeper geographic analysis of customer distribution, sales and customer value.

## Key KPIs

- Unique Delivered Customers
- Delivered Sales
- Delivered Orders
- Average Sales per Customer
- Repeat Customer Rate

## Key Visuals

- Top states by delivered sales
- Top states by customer count
- Top states by sales per customer
- State performance table

## State-Level Metrics

The detailed geographic analysis includes:

- Unique Delivered Customers
- Delivered Sales
- Delivered Orders
- Sales per Customer
- Repeat Customer Rate

## Business Purpose

This page helps management understand:

- Where the customer base is concentrated
- Where revenue is concentrated
- Which states have higher customer value
- How customer retention varies geographically

---

# 10. Predictive Insights — Sales Forecast

This page extends the descriptive BI report with a basic predictive analytics workflow.

Instead of only asking:

> **What happened?**

the project also asks:

> **What could historical sales data suggest for future periods?**

## Forecast Objective

Use historical monthly delivered sales to estimate the next six months of sales.

## Forecasting Workflow

```text
Historical Order Data
        ↓
Filter Delivered Orders
        ↓
Aggregate Sales by Month
        ↓
Create Continuous Monthly Time Series
        ↓
Time-Based Train/Test Split
        ↓
Evaluate Forecasting Models
        ↓
Train Final Model
        ↓
Generate Six-Month Forecast
        ↓
Export CSV
        ↓
Import into Power BI
```

## Models Tested

### 1. Naive Baseline

Uses the last observed training value as the forecast for future periods.

### 2. Simple Exponential Smoothing

Estimates the current level of the sales series while placing greater emphasis on recent observations.

### 3. Holt Linear Trend

Models both the current level and the historical trend.

---

## Forecast Model Validation

The validation uses a chronological split rather than a random split.

### Training Period

```text
September 2016 to April 2018
```

### Test Period

```text
May 2018 to August 2018
```

The same four-month holdout period was used to compare the models.

## Validation Metrics

- MAE — Mean Absolute Error
- RMSE — Root Mean Squared Error
- MAPE — Mean Absolute Percentage Error

## Model Results

| Model | MAE | RMSE | MAPE |
|---|---:|---:|---:|
| Simple Exponential Smoothing | ₹87,270.26 | ₹100,235.80 | 8.66% |
| Naive Baseline | ₹94,366.00 | ₹108,854.12 | 9.37% |
| Holt Linear Trend | ₹331,448.01 | ₹354,242.37 | 32.57% |

Simple Exponential Smoothing produced the lowest error among the three tested approaches on the selected validation period and was therefore used for the final forecast.

---

## Final Six-Month Forecast

The forecasting series ends in August 2018.

The final forecast is:

| Month | Forecast Sales |
|---|---:|
| September 2018 | ₹995,710.73 |
| October 2018 | ₹995,710.73 |
| November 2018 | ₹995,710.73 |
| December 2018 | ₹995,710.73 |
| January 2019 | ₹995,710.73 |
| February 2019 | ₹995,710.73 |

Total six-month forecast:

```text
Approximately ₹5.97M
```

The forecast is approximately ₹996K per month.

## Why Is the Forecast Flat?

The selected Simple Exponential Smoothing configuration models the current level of the series without explicitly adding a separate trend or seasonal component.

Therefore, the model produces approximately the same forecast level for each future month.

The flat line is expected behavior for this model configuration and is not a data error.

---

# Predictive Output Files

The predictive workflow produces the following files:

### Forecast Dataset

```text
Data/Analysis/sales_forecast.csv
```

This contains:

- `order_month`
- `actual_sales`
- `forecast_sales`
- `is_forecast`
- `model`

The file contains:

```text
30 rows
24 historical months
6 forecast months
```

### Model Comparison

```text
09_Predictive_Analytics/outputs/forecast_model_comparison.csv
```

Contains:

- Model
- MAE
- RMSE
- MAPE

### Forecast Chart

```text
09_Predictive_Analytics/outputs/sales_forecast.png
```

### Forecast Notebook

```text
09_Predictive_Analytics/notebooks/01_sales_forecasting.ipynb
```

---

# Data & Analytical Model

The Power BI report uses a structured analytical model.

## Core Fact Table

```text
Fact_Orders
```

This is the central order-level table.

## Supporting / Staging Tables

- `Stg_Order_Items`
- `Stg_Products`
- `Stg_Category_Translation`

## Analytical Tables

- `Category_Sales`
- `Category_Experience`
- `Customer_Summary`
- `Cohort_Retention`

## Marketing Tables

- `Marketing_MQL`
- `Closed_Deals`

## Supporting Dimensions

- `Dim_Date`
- `Dim_Category`

## Measures

A centralized `_Measures` table stores the major DAX measures used throughout the report.

This helps keep KPI definitions consistent across multiple pages.

---

# Key Power BI Measures

Examples of the core KPI logic include:

```DAX
Total Orders =
DISTINCTCOUNT(Fact_Orders[order_id])
```

```DAX
Delivered Orders =
CALCULATE(
    [Total Orders],
    Fact_Orders[is_delivered] = TRUE()
)
```

```DAX
Delivered Sales =
CALCULATE(
    SUM(Fact_Orders[sales_value_incl_freight]),
    Fact_Orders[is_delivered] = TRUE()
)
```

```DAX
Average Order Value =
DIVIDE(
    [Delivered Sales],
    [Delivered Orders]
)
```

```DAX
Repeat Customers =
COUNTROWS(
    FILTER(
        VALUES(Fact_Orders[customer_unique_id]),
        CALCULATE([Delivered Orders]) >= 2
    )
)
```

```DAX
Repeat Customer Rate =
DIVIDE(
    [Repeat Customers],
    [Unique Delivered Customers]
)
```

```DAX
Late Delivery Rate =
DIVIDE(
    [Late Orders],
    [Delivered Orders]
)
```

The project also uses a review-count-weighted average for the overall review score:

```DAX
Average Review Score =
DIVIDE(
    SUMX(
        Fact_Orders,
        Fact_Orders[average_review_score]
            * Fact_Orders[review_count]
    ),
    SUM(Fact_Orders[review_count])
)
```

This prevents simple averaging of order-level averages from distorting the overall review metric.

---

# Dashboard Navigation

The report uses Power BI page navigation and Home buttons.

Home buttons on the detailed dashboard pages return users to:

> **Executive Overview**

This creates a simple flow from the main management page to detailed analytical pages and back again.

The Predictive Insights page also follows the same navigation style.

---

# Interactivity

The report supports interactive exploration through:

- Date filtering
- State filtering
- Order-status filtering
- Cross-filtering between compatible visuals
- Page navigation
- Detailed tables and matrices

Users can start at the Executive Overview and move into sales, category, customer, operations, satisfaction, marketing, geographic and predictive analysis.

---

# Major Business Insight Themes

The Power BI report highlights several important business themes identified during the analysis.

## Sales Performance

Delivered sales provide the main realized-sales view of the business, with monthly sales showing significant changes over the analyzed period.

## Customer Retention

Repeat customers represent approximately 3.00% of unique delivered customers.

This means the analyzed customer base is dominated by one-time purchasers.

## Delivery Performance

The delivered-order rate is approximately 97.02%, while the late-delivery rate among delivered orders is approximately 6.77%.

## Customer Experience

On-time orders have an average review score of approximately 4.29, while late orders have an average review score of approximately 2.27.

This is a descriptive relationship found in the analyzed data.

## Freight Economics

Freight value represents approximately 16.63% of product sales overall, with meaningful variation across categories.

## Marketing Funnel

The report contains 8,000 MQLs and 842 closed deals, resulting in an overall MQL-to-Closed conversion rate of approximately 10.53%.

## Geographic Concentration

The top geographic areas account for a meaningful share of sales and customer activity, making state and city-level performance useful for business analysis.

---

# Dashboard Design Approach

The report uses a consistent professional dashboard theme:

- Light gray/off-white page background
- Dark navy headers
- Blue and teal accents
- White KPI cards and visual containers
- Muted risk-oriented colors where needed
- Consistent typography
- Clear page titles
- Home navigation buttons

The goal is to make the report readable for both business users and technical reviewers.

---

# Power BI Report File

The main Power BI report is:

```text
08_Dashboards/ShopSphere_Business_Intelligence.pbix
```

The dashboard screenshots are stored in:

```text
reports/
```

The screenshots document the major report pages for GitHub and portfolio presentation.

---

# Reproducing the Dashboard

## Step 1 — Prepare the data

Ensure the required analysis-ready data exists under:

```text
Data/Analysis/
```

The main order-level analytical file is:

```text
Data/Analysis/master_orders.csv
```

## Step 2 — Open Power BI

Open:

```text
08_Dashboards/ShopSphere_Business_Intelligence.pbix
```

## Step 3 — Refresh the data

Use Power BI's refresh functionality when the underlying CSV files have changed.

## Step 4 — Predictive output

If the forecasting notebook is rerun, the updated:

```text
Data/Analysis/sales_forecast.csv
```

can be loaded/refreshed into the Power BI model so the Predictive Insights page reflects the new forecast output.

---

# Predictive Analytics Integration

The predictive layer is intentionally kept separate from the descriptive order-level analysis.

The architecture is:

```text
Python
  ↓
Forecast Model
  ↓
Prediction CSV
  ↓
Power BI
  ↓
Predictive Insights Page
```

This means the Power BI report can continue to provide historical business intelligence while also displaying the predictive results.

The forecast does not replace the existing dashboard pages.

---

# Important Predictive Analytics Limitations

The forecasting results should be interpreted carefully.

## Historical Scope

The forecasting series ends in August 2018.

Therefore:

> The September 2018 to February 2019 forecast is a historical forecasting exercise and should not be presented as a current 2026 sales forecast.

## Limited Time-Series Length

Only about two years of monthly history are available.

This limits the ability to confidently model long-term behavior and recurring seasonal patterns.

## Simple Model Configuration

The final model is Simple Exponential Smoothing without an explicit trend or seasonal component.

## Limited Validation Window

The model comparison uses a four-month holdout period.

A production forecasting workflow should use more extensive rolling or walk-forward validation.

## External Variables

The forecast does not explicitly include:

- Promotions
- Marketing spend
- Pricing changes
- Inventory availability
- Holidays
- Competitor actions
- Economic conditions

These factors could affect real-world sales.

---

# Future Extensions

The current report already contains a complete descriptive, diagnostic and basic predictive workflow.

Potential future extensions include:

- Delivery delay risk prediction
- Customer repeat-purchase prediction
- Customer inactivity/churn analysis
- Category-level sales forecasting
- Order-volume forecasting
- Seasonal forecasting models
- ARIMA/SARIMA
- Prophet
- Machine-learning-based forecasting

These are future extensions rather than missing components of the current dashboard.

---

# Tools & Technologies

## Business Intelligence

- Power BI Desktop
- Power Query
- DAX
- Data Modeling

## Data Analysis

- Python
- Pandas
- NumPy
- Jupyter Notebook

## Visualization

- Power BI
- Matplotlib

## Predictive Analytics

- Statsmodels
- Scikit-learn
- Simple Exponential Smoothing
- Holt Linear Trend
- MAE
- RMSE
- MAPE

## Version Control

- Git
- GitHub

---

# Repository Structure

```text
ShopSphere_Analysis/
│
├── 01_Business_Understanding/
│
├── 02_Business_Requirement_Gathering/
│
├── 03_Data_Requirement_Analysis/
│
├── 04_Data_Collection_strategy/
│
├── 05_Data_Profiling/
│   ├── reports/
│   ├── profiling.ipynb
│   └── README.md
│
├── 06_Data_Cleaning/
│   ├── data_cleaning.ipynb
│   └── README.md
│
├── 07_Business_Analysis/
│   ├── business_analysis.ipynb
│   └── README.md
│
├── 08_Dashboards/
│   ├── README.md
│   └── ShopSphere_Business_Intelligence.pbix
│
├── 09_Predictive_Analytics/
│   ├── notebooks/
│   │   └── 01_sales_forecasting.ipynb
│   │
│   ├── outputs/
│   │   ├── forecast_model_comparison.csv
│   │   └── sales_forecast.png
│   │
│   └── README.md
│
├── Data/
│   ├── Raw/
│   ├── Cleaned/
│   └── Analysis/
│       ├── master_orders.csv
│       └── sales_forecast.csv
│
├── reports/
│   ├── 1. KPI Validation.png
│   ├── 2. Executive Overview.png
│   ├── 3. Sales & Revenue.png
│   ├── 4. Product & Category.png
│   ├── 5. Customer Intelligence.png
│   ├── 6. Operations & Delivery.png
│   ├── 7. Customer Satisfaction.png
│   ├── 8. Marketing & Sales Funnel.png
│   ├── 9. Geographic Customer Intelligence.png
│   └── 10. Predictive Insights - Sales Forecast.png
│
├── .gitignore
├── requirements.txt
└── README.md
```

---

# Interview Explanation

A simple way to explain the dashboard is:

> I built a 10-page Power BI report for an e-commerce business called ShopSphere. I first created and validated an order-level analytical model, then analyzed sales, customers, categories, delivery, customer satisfaction, marketing and geography. I also added a predictive page where I used Python to aggregate monthly delivered sales, compared a naive baseline, Simple Exponential Smoothing and Holt's trend method, evaluated them using MAE, RMSE and MAPE, and connected the final six-month forecast back to Power BI.

## Short Explanation of Each Page

| Page | Easy Interview Explanation |
|---|---|
| KPI Validation | I used this page to verify that the main KPIs were correct before presenting them. |
| Executive Overview | This is the management summary of the business. |
| Sales & Revenue | This explains sales trends, order volume, AOV and freight. |
| Product & Category | This compares category sales, cost burden, reviews and delivery performance. |
| Customer Intelligence | This focuses on one-time customers, repeat customers and customer value. |
| Operations & Delivery | This analyzes delivery timing, late orders and variance. |
| Customer Satisfaction | This examines review scores and the relationship with delivery experience. |
| Marketing & Sales Funnel | This shows how MQLs move toward closed deals. |
| Geographic Customer Intelligence | This compares customer and sales performance across states. |
| Predictive Insights | This connects historical sales with a validated six-month sales forecast. |

---

# Final Outcome

ShopSphere now combines:

```text
Business Analysis
       +
Data Quality & Preparation
       +
Power BI Business Intelligence
       +
Predictive Sales Forecasting
```

The report is designed to answer both:

> **What happened in the business?**

and:

> **What does the historical data suggest for the next few periods?**

The predictive page is clearly separated from historical reporting so that forecast values are not confused with actual historical sales.

---

# Conclusion

The ShopSphere Power BI solution provides an end-to-end business analytics experience.

It starts with validated business data, converts that data into meaningful KPIs and business insights, presents those insights through interactive Power BI pages, and extends the analysis into predictive sales forecasting.

The final solution demonstrates practical skills in:

- Business Analysis
- Data Profiling
- Data Cleaning
- KPI Validation
- Data Modeling
- Power Query
- DAX
- Power BI Dashboard Development
- Customer and Sales Analysis
- Operational Analysis
- Marketing Funnel Analysis
- Geographic Analysis
- Time-Series Forecasting
- Model Evaluation
- Python-to-Power BI Integration

The most important principle behind the report is:

> **Build reliable business logic first, validate the numbers, communicate the findings clearly, and only then add predictive analysis.**
