# Data Dictionary

## 1. Purpose

This document defines the structure, meaning, and analytical purpose
of the data used in the ShopSphere E-Commerce Intelligence Platform.

The primary data source is the Olist Brazilian E-Commerce Public Dataset.

The dictionary will be expanded as the data is transformed into the
ShopSphere analytical model.

---

# 2. Customer Data

## Source Table
`olist_customers_dataset.csv`

| Column | Data Type | Description | Business Meaning |
|---|---|---|---|
| customer_id | String | Unique identifier for a customer order record | Links customer records to orders |
| customer_unique_id | String | Unique identifier representing the actual customer | Used for customer-level analysis |
| customer_zip_code_prefix | Integer | Customer ZIP code prefix | Used for geographic analysis |
| customer_city | String | Customer city | Used for regional analysis |
| customer_state | String | Customer state | Used for geographic performance |

---

# 3. Order Data

## Source Table
`olist_orders_dataset.csv`

| Column | Data Type | Description | Business Meaning |
|---|---|---|---|
| order_id | String | Unique order identifier | Identifies a transaction |
| customer_id | String | Customer record associated with the order | Connects orders with customers |
| order_status | String | Current/final status of the order | Used for operational analysis |
| order_purchase_timestamp | DateTime | Time when the order was purchased | Main transaction date |
| order_approved_at | DateTime | Time when payment/order approval occurred | Order processing analysis |
| order_delivered_carrier_date | DateTime | Date order was handed to carrier | Shipping analysis |
| order_delivered_customer_date | DateTime | Date order was delivered to customer | Delivery performance |
| order_estimated_delivery_date | DateTime | Estimated delivery date | Delivery accuracy analysis |

---

# 4. Order Item Data

## Source Table
`olist_order_items_dataset.csv`

| Column | Data Type | Description | Business Meaning |
|---|---|---|---|
| order_id | String | Order identifier | Links item to an order |
| order_item_id | Integer | Sequential item number within an order | Identifies individual order lines |
| product_id | String | Product identifier | Links item to product |
| seller_id | String | Seller identifier | Links item to seller |
| shipping_limit_date | DateTime | Seller shipping deadline | Seller/shipping performance |
| price | Decimal | Price of the item | Revenue calculation |
| freight_value | Decimal | Freight/shipping value associated with the item | Freight analysis |

> Note: `order_item_id` identifies the item position within an order.
> It should not automatically be interpreted as the physical quantity
> purchased.

---

# 5. Product Data

## Source Table
`olist_products_dataset.csv`

| Column | Data Type | Description | Business Meaning |
|---|---|---|---|
| product_id | String | Unique product identifier | Links products to order items |
| product_category_name | String | Product category in Portuguese | Product classification |
| product_name_lenght | Integer | Length of product name | Product metadata |
| product_description_lenght | Integer | Length of product description | Product metadata |
| product_photos_qty | Integer | Number of product photos | Product presentation |
| product_weight_g | Decimal | Product weight in grams | Logistics analysis |
| product_length_cm | Decimal | Product length | Logistics analysis |
| product_height_cm | Decimal | Product height | Logistics analysis |
| product_width_cm | Decimal | Product width | Logistics analysis |

---

# 6. Category Data

## Source Table
`product_category_name_translation.csv`

| Column | Data Type | Description | Business Meaning |
|---|---|---|---|
| product_category_name | String | Original Portuguese category name | Category key |
| product_category_name_english | String | English translation | User-friendly category name |

---

# 7. Payment Data

## Source Table
`olist_order_payments_dataset.csv`

| Column | Data Type | Description | Business Meaning |
|---|---|---|---|
| order_id | String | Order identifier | Links payment to order |
| payment_sequential | Integer | Sequence of payment within an order | Supports multiple payments |
| payment_type | String | Payment method | Payment-method analysis |
| payment_installments | Integer | Number of installments | Installment analysis |
| payment_value | Decimal | Payment value | Payment/revenue analysis |

---

# 8. Review Data

## Source Table
`olist_order_reviews_dataset.csv`

| Column | Data Type | Description | Business Meaning |
|---|---|---|---|
| review_id | String | Review identifier | Identifies review |
| order_id | String | Associated order | Links review to order |
| review_score | Integer | Customer rating from 1 to 5 | Customer satisfaction |
| review_comment_title | String | Review title | Text analysis |
| review_comment_message | String | Review message | Sentiment/text analysis |
| review_creation_date | DateTime | Review creation date | Review trend analysis |
| review_answer_timestamp | DateTime | Time review was answered | Review response analysis |

---

# 9. Seller Data

## Source Table
`olist_sellers_dataset.csv`

| Column | Data Type | Description | Business Meaning |
|---|---|---|---|
| seller_id | String | Unique seller identifier | Identifies seller |
| seller_zip_code_prefix | Integer | Seller ZIP code prefix | Seller geography |
| seller_city | String | Seller city | Seller location |
| seller_state | String | Seller state | Seller regional analysis |

---

# 10. Geolocation Data

## Source Table
`olist_geolocation_dataset.csv`

| Column | Data Type | Description | Business Meaning |
|---|---|---|---|
| geolocation_zip_code_prefix | Integer | ZIP code prefix | Geographic lookup |
| geolocation_lat | Decimal | Latitude | Geographic analysis |
| geolocation_lng | Decimal | Longitude | Geographic analysis |
| geolocation_city | String | City | Geographic analysis |
| geolocation_state | String | State | Geographic analysis |

---

# 11. Marketing Qualified Lead Data

## Source Table
`olist_marketing_qualified_leads_dataset.csv`

| Column | Data Type | Description | Business Meaning |
|---|---|---|---|
| mql_id | String | Marketing qualified lead identifier | Identifies potential seller lead |
| first_contact_date | Date | Date of first contact | Lead acquisition analysis |
| landing_page_id | String | Landing page associated with lead | Marketing source analysis |
| origin | String | Lead origin/source | Lead acquisition analysis |

---

# 12. Closed Deal Data

## Source Table
`olist_closed_deals_dataset.csv`

| Column | Data Type | Description | Business Meaning |
|---|---|---|---|
| mql_id | String | Marketing qualified lead identifier | Links lead to closed deal |
| seller_id | String | Seller created from the lead | Links acquisition to seller |
| sdr_id | String | Sales development representative | Sales performance analysis |
| sr_id | String | Sales representative identifier | Sales performance analysis |
| won_date | Date | Date the deal was won | Seller acquisition timing |
| business_segment | String | Business segment | Seller segmentation |
| lead_type | String | Type of lead | Lead analysis |
| lead_behaviour_profile | String | Lead behavior classification | Lead segmentation |
| business_type | String | Type of business | Seller segmentation |
| declared_product_catalog_size | Numeric | Declared catalog size | Seller characteristics |
| declared_monthly_revenue | Numeric | Declared monthly revenue | Seller characteristics |

---

# 13. Derived Data

The following values are not directly collected as raw fields.
They will be calculated during transformation or analysis.

| Derived Metric | Basis |
|---|---|
| Revenue | Order item price |
| Freight Cost | Freight value |
| Average Order Value | Revenue / Orders |
| Customer Order Count | Count of orders per customer |
| Repeat Customer | Customer with multiple purchases |
| Customer Recency | Latest purchase date relative to analysis date |
| Customer Frequency | Number of purchases |
| Customer Monetary Value | Customer revenue |
| Delivery Time | Delivery date - purchase date |
| Delivery Delay | Actual delivery - estimated delivery |
| Monthly Revenue | Revenue aggregated by month |
| Product Sales | Order-item-level sales aggregation |
| Review Sentiment | Derived from review text |
| Churn Label | Defined from customer purchase behavior |
| Sales Forecast | Machine learning model output |

---

# 14. Data Not Available in the Primary Source

The following requirements are not directly supported by the
primary Olist dataset:

- Historical inventory levels
- Inventory movements
- Product cost
- Actual product profit
- Reliable customer advertising attribution
- Historical campaign spend for customer campaigns

These will not be fabricated or presented as observed data.

If required later, a clearly documented synthetic or scenario-based
component may be considered.

---

# 15. Data Classification

| Classification | Examples |
|---|---|
| Observed | Customers, orders, products, reviews, payments |
| Derived | Revenue, AOV, retention, delivery time |
| Enriched | Geographic information / category translation |
| ML Output | Churn probability, sales forecast |
| AI Output | Business recommendations |
| Synthetic | Potential inventory simulation |

---

## Version

Version: 1.0

Status: Draft based on source-schema inspection