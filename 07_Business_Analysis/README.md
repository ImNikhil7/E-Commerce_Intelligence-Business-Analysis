# Phase 7 — Business Analysis

## Purpose

This phase transforms the cleaned and validated datasets into
business-level analytical tables, KPIs, insights, scenario analyses,
and recommendations.

## Main Analysis Areas

- Sales and order trends
- Product and category performance
- Seller performance
- Customer behavior and retention
- Payment behavior
- Delivery performance
- Customer satisfaction
- Geographic concentration
- High-value orders
- Marketing funnel
- Freight burden

## Analytical Model

A master order-level analytical dataset was created with:

> One row = one order

To avoid double-counting caused by one-to-many relationships, order
items, payments, and reviews are aggregated to the order level before
being joined to the main order table.

The resulting file is:

`../Data/Analysis/master_orders.csv`

## Final Outputs

- Core business KPI framework
- Master analytical dataset
- Business priority framework
- Retention scenario analysis
- Delivery improvement scenario analysis
- Final business recommendations

## Status

**Phase 7 — Complete**