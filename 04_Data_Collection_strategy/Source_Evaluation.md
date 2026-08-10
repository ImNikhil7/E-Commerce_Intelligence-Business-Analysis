# Source Evaluation

## Objective

Evaluate potential data sources against the business and data
requirements of the ShopSphere E-Commerce Intelligence Platform.

## Candidate Sources

### 1. Olist Brazilian E-Commerce Public Dataset

Source:
Kaggle - Brazilian E-Commerce Public Dataset by Olist

Strengths:
- Real anonymized commercial data
- Approximately 100,000 orders
- Multiple relational datasets
- Customer information
- Order information
- Order items
- Product information
- Payments
- Reviews
- Geography
- Freight and delivery information
- Marketing Funnel dataset available separately

Limitations:
- No reliable product cost
- No historical inventory movement data
- Discount analysis may not be directly supported
- Historical period is 2016–2018

Decision:
Selected as the primary/core data source.

---

### 2. DummyJSON

Strengths:
- Product API
- User API
- Cart API
- Product ratings
- Product stock
- Product discount fields

Limitations:
- Synthetic/sample data
- Cannot naturally join with Olist product IDs
- Not suitable as core transactional data

Decision:
Potential API learning/reference source only.

---

### 3. Google Analytics E-Commerce Sample

Strengths:
- Real-world style event structure
- Useful for web analytics and funnel analysis
- Public BigQuery dataset

Limitations:
- Only three months
- Obfuscated
- Limited internal consistency
- Different analytical model from our core transactional model

Decision:
Not selected as core data source.