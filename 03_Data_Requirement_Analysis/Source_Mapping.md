# Source Mapping

## 1. Purpose

This document maps ShopSphere business entities and analytical
requirements to their actual source datasets.

The primary source is the Olist Brazilian E-Commerce Public Dataset.

---

# 2. Core Source Mapping

| ShopSphere Entity | Source File | Primary Key | Main Relationship |
|---|---|---|---|
| Customers | olist_customers_dataset.csv | customer_id | customer → orders |
| Orders | olist_orders_dataset.csv | order_id | order → customer |
| Order Items | olist_order_items_dataset.csv | order_id + order_item_id | order → products |
| Products | olist_products_dataset.csv | product_id | product → order items |
| Categories | product_category_name_translation.csv + product category field | product_category_name | category → products |
| Payments | olist_order_payments_dataset.csv | order_id + payment_sequential | order → payments |
| Reviews | olist_order_reviews_dataset.csv | review_id | review → order |
| Sellers | olist_sellers_dataset.csv | seller_id | seller → order items |
| Geography | olist_geolocation_dataset.csv | ZIP prefix | geographic enrichment |

---

# 3. Customer Mapping

| ShopSphere Requirement | Source | Column |
|---|---|---|
| Customer ID | customers | customer_unique_id |
| Customer record ID | customers | customer_id |
| City | customers | customer_city |
| State | customers | customer_state |
| ZIP Prefix | customers | customer_zip_code_prefix |

---

# 4. Order Mapping

| ShopSphere Requirement | Source | Column |
|---|---|---|
| Order ID | orders | order_id |
| Customer | orders | customer_id |
| Order Status | orders | order_status |
| Order Date | orders | order_purchase_timestamp |
| Approval Date | orders | order_approved_at |
| Carrier Date | orders | order_delivered_carrier_date |
| Delivery Date | orders | order_delivered_customer_date |
| Estimated Delivery | orders | order_estimated_delivery_date |

---

# 5. Order Item Mapping

| ShopSphere Requirement | Source | Column |
|---|---|---|
| Order | order_items | order_id |
| Order Item | order_items | order_item_id |
| Product | order_items | product_id |
| Seller | order_items | seller_id |
| Item Price | order_items | price |
| Freight Value | order_items | freight_value |
| Shipping Limit | order_items | shipping_limit_date |

---

# 6. Product Mapping

| ShopSphere Requirement | Source | Column |
|---|---|---|
| Product ID | products | product_id |
| Category | products | product_category_name |
| Product Weight | products | product_weight_g |
| Product Length | products | product_length_cm |
| Product Height | products | product_height_cm |
| Product Width | products | product_width_cm |
| Product Photos | products | product_photos_qty |

---

# 7. Review Mapping

| ShopSphere Requirement | Source | Column |
|---|---|---|
| Review ID | reviews | review_id |
| Order | reviews | order_id |
| Rating | reviews | review_score |
| Review Title | reviews | review_comment_title |
| Review Text | reviews | review_comment_message |
| Review Date | reviews | review_creation_date |
| Answer Date | reviews | review_answer_timestamp |

---

# 8. Payment Mapping

| ShopSphere Requirement | Source | Column |
|---|---|---|
| Order | payments | order_id |
| Payment Sequence | payments | payment_sequential |
| Payment Type | payments | payment_type |
| Installments | payments | payment_installments |
| Payment Value | payments | payment_value |

---

# 9. Seller Mapping

| ShopSphere Requirement | Source | Column |
|---|---|---|
| Seller ID | sellers | seller_id |
| Seller ZIP | sellers | seller_zip_code_prefix |
| Seller City | sellers | seller_city |
| Seller State | sellers | seller_state |

---

# 10. Marketing Mapping

## Marketing Qualified Leads

Source:

`olist_marketing_qualified_leads_dataset.csv`

| Requirement | Column |
|---|---|
| MQL ID | mql_id |
| First Contact | first_contact_date |
| Landing Page | landing_page_id |
| Lead Origin | origin |

## Closed Deals

Source:

`olist_closed_deals_dataset.csv`

Important fields include:

- mql_id
- seller_id
- won_date
- business_segment
- lead_type
- business_type
- declared_product_catalog_size
- declared_monthly_revenue

This domain represents seller acquisition rather than customer
advertising attribution.

---

# 11. Derived Data Mapping

| Analytical Field | Derived From |
|---|---|
| Revenue | order_items.price |
| Monthly Revenue | order_items.price + orders.order_purchase_timestamp |
| Average Order Value | Revenue / Order Count |
| Delivery Time | order delivery date - purchase timestamp |
| Delivery Delay | Actual delivery - estimated delivery |
| Repeat Customer | Customer purchase history |
| Customer Recency | Latest purchase date |
| Customer Frequency | Number of customer orders |
| Customer Monetary Value | Customer-associated revenue |
| Review Sentiment | Review text + NLP |
| Churn Risk | Customer behavior + ML |
| Sales Forecast | Historical sales + ML |

---

# 12. Unsupported Requirements

The following requirements currently have no reliable source mapping:

- Historical inventory
- Product cost
- Actual profit
- Customer campaign spend
- Customer advertising attribution
- Reliable historical discount information

These requirements require either another suitable source,
a documented simulation, or removal from the analytical scope.

---

## Version

Version: 1.0

Status: Draft based on source-schema inspection