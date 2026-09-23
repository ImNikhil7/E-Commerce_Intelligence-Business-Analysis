# 09 — Predictive Analytics

## Overview

This folder contains the predictive analytics part of the **ShopSphere Analysis** project.

The earlier phases of the project focused mainly on understanding what happened in the business:

- How much did we sell?
- How many orders did we receive?
- Which categories generated more sales?
- How many customers returned?
- How often were orders delivered late?
- Which locations generated more business?
- Which marketing channels produced closed deals?

Predictive analytics takes the next step:

> **Can historical business data be used to estimate what may happen in future periods?**

In this phase, the project focuses on **sales forecasting**.

The goal is to use historical monthly delivered sales to estimate the next six months of sales.

---

# 1. Business Problem

An e-commerce business needs to understand its future sales level for planning purposes.

A sales forecast can help a business think about questions such as:

- How much sales volume might be expected in upcoming months?
- Should inventory planning be increased or reduced?
- How much operational capacity may be required?
- What level of sales could be used for short-term planning?
- Can a simple forecasting model perform better than a basic baseline?

For this project, the business problem was defined as:

> **Use historical monthly delivered sales to forecast future monthly sales.**

---

# 2. Objective

The main objective of this phase is to:

1. Prepare monthly sales data from the cleaned order-level dataset.
2. Create a time-based training and testing dataset.
3. Build simple forecasting models.
4. Compare model performance using error metrics.
5. Select a forecasting approach based on validation results.
6. Forecast the next six months.
7. Save the forecast in a Power BI-ready CSV file.
8. Visualize the forecast inside Power BI.

---

# 3. Dataset Used

The forecasting process uses the prepared order-level dataset:

```text
Data/Analysis/master_orders.csv