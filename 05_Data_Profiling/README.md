# Phase 5 — Data Profiling

## 1. Overview

This phase focuses on systematically profiling the raw Olist datasets before
performing data cleaning and transformation.

The objective is to understand the structure, completeness, consistency,
relationships, distributions, and potential quality issues present in the
source data.

The profiling was performed using Python and Pandas in a Jupyter Notebook.

---

## 2. Objectives

The main objectives of this phase were to:

- Understand the structure of all available datasets
- Identify row and column counts
- Inspect data types and missing values
- Identify candidate primary keys
- Validate relationships between related datasets
- Analyze duplicate records
- Examine one-to-many relationships
- Analyze missing-value patterns
- Check categorical and value consistency
- Validate important business rules
- Identify statistical outliers
- Analyze distributions and skewness
- Document data-quality issues requiring attention
- Determine whether the datasets are suitable for further processing

---

## 3. Datasets Profiled

A total of 11 datasets were identified and profiled.

| Dataset | Rows | Columns |
|---|---:|---:|
| `olist_closed_deals_dataset.csv` | 842 | 14 |
| `olist_customers_dataset.csv` | 99,441 | 5 |
| `olist_geolocation_dataset.csv` | 1,000,163 | 5 |
| `olist_marketing_qualified_leads_dataset.csv` | 8,000 | 4 |
| `olist_orders_dataset.csv` | 99,441 | 8 |
| `olist_order_items_dataset.csv` | 112,650 | 7 |
| `olist_order_payments_dataset.csv` | 103,886 | 5 |
| `olist_order_reviews_dataset.csv` | 99,224 | 7 |
| `olist_products_dataset.csv` | 32,951 | 9 |
| `olist_sellers_dataset.csv` | 3,095 | 4 |
| `product_category_name_translation.csv` | 71 | 2 |

---

# 4. Profiling Process

## Step 1 — Dataset Discovery

All CSV files available in the raw data directory were discovered and loaded
for profiling.

A total of 11 CSV datasets were identified.

---

## Step 2 — Dataset Structure

Row and column counts were calculated for every dataset.

This established the initial size and structure of the available data sources.

The largest dataset is:

- `olist_geolocation_dataset.csv` — 1,000,163 rows

The smallest dataset is:

- `product_category_name_translation.csv` — 71 rows

---

## Step 3 — Data Type and Column Profiling

Each column was examined for:

- Data type
- Non-null count
- Null count
- Number of unique values

This helped identify identifiers, categorical fields, numeric fields,
and date/time fields.

Important observations included:

- Most identifier columns were stored as strings.
- Several date columns were initially stored as strings.
- Numeric fields were represented using integer or floating-point types.
- Some fields contained missing values.

---

## Step 4 — Candidate Key Analysis

Candidate keys were tested for:

- Null values
- Unique values
- Duplicate values
- Validity as a potential key

The following candidate keys were found to be unique:

| Dataset | Candidate Key |
|---|---|
| Customers | `customer_id` |
| Orders | `order_id` |
| Products | `product_id` |
| Sellers | `seller_id` |
| Marketing Qualified Leads | `mql_id` |
| Closed Deals | `mql_id` |

All tested candidate keys contained zero null values and zero duplicate values.

---

## Step 5 — Date and Timestamp Profiling

Date-related fields were identified across the datasets.

Important date fields include:

- `won_date`
- `first_contact_date`
- `order_purchase_timestamp`
- `order_approved_at`
- `order_delivered_carrier_date`
- `order_delivered_customer_date`
- `order_estimated_delivery_date`
- `shipping_limit_date`
- `review_creation_date`
- `review_answer_timestamp`

Missing values were identified in several order-related delivery timestamps.

These fields require business-context handling during the cleaning phase rather
than automatic replacement.

---

## Step 6 — Referential Integrity

Relationships between major datasets were validated.

The following relationships achieved a 100% match rate:

| Child Dataset | Child Key | Parent Dataset | Parent Key | Match Rate |
|---|---|---|---|---:|
| Orders | `customer_id` | Customers | `customer_id` | 100% |
| Order Items | `order_id` | Orders | `order_id` | 100% |
| Order Items | `product_id` | Products | `product_id` | 100% |
| Order Items | `seller_id` | Sellers | `seller_id` | 100% |
| Payments | `order_id` | Orders | `order_id` | 100% |
| Reviews | `order_id` | Orders | `order_id` | 100% |
| Closed Deals | `mql_id` | Marketing Qualified Leads | `mql_id` | 100% |

No orphan records were identified in the tested relationships.

This indicates strong referential integrity across the tested transactional
relationships.

---

## Step 7 — Relationship Cardinality

The number of related records per entity was examined.

Observed maximum counts included:

- Maximum orders per customer: 17
- Maximum items per order: 21
- Maximum payments per order: 29
- Maximum reviews per order: 3
- Maximum times a product was sold: 527
- Maximum items associated with a product: 2,033

The analysis confirmed that the datasets contain important one-to-many
relationships.

For example:

- One customer can have multiple orders.
- One order can contain multiple order items.
- One order can have multiple payment records.
- One product can appear across many order-item records.

---

# Step 8 — Missing Value Analysis

Missing values were analyzed at both column and dataset levels.

Major findings included:

### Closed Deals

Several fields contain very high levels of missingness:

- `has_company` — 92.52%
- `has_gtin` — 92.40%
- `average_stock` — 92.16%
- `declared_product_catalog_size` — 91.81%

### Order Reviews

- `review_comment_title` — 88.34%
- `review_comment_message` — 58.70%

### Other Important Missing Values

- `lead_behaviour_profile` — 21.02%
- `order_delivered_customer_date` — 2.98%
- `order_delivered_carrier_date` — 1.79%
- Several product attributes — approximately 1.85%

The missing values are not automatically considered errors.

Their treatment will depend on the meaning of the field and the business
requirements.

---

# Step 9 — Missing Value Patterns

Missing values were also analyzed against relevant categorical variables.

### Order Status

Delivered orders had very low levels of missing delivery dates, while several
non-delivered statuses naturally had missing delivery timestamps.

This indicates that missing delivery dates are strongly related to order status
and should not be blindly imputed.

### Review Score

Missing review comments were observed across all review scores.

The comment fields therefore represent optional customer feedback rather than
mandatory transactional attributes.

### Product Attributes

The same 610 product records were missing values in:

- `product_category_name`
- `product_name_lenght`
- `product_description_lenght`
- `product_photos_qty`

This indicates a shared missing-record pattern that should be considered during
cleaning.

---

# Step 10 — Duplicate Analysis

Duplicate rows were checked across all datasets.

Most datasets contained no duplicate rows.

However:

`olist_geolocation_dataset.csv`

contained:

- Total rows: 1,000,163
- Duplicate rows: 261,831
- Duplicate percentage: 26.18%

The geolocation dataset requires special consideration because repeated
geographical records can occur for the same ZIP-code prefix and location.

Duplicates should therefore not automatically be deleted without understanding
their purpose.

---

# Step 11 — Customer and Geolocation Consistency

The relationship between `customer_unique_id` and `customer_id` was examined.

Some customers have multiple `customer_id` records.

For example, the highest observed count was:

- `customer_unique_id` → 17 customer records

However, these records generally maintained consistent:

- Customer city
- Customer state

This indicates that `customer_unique_id` represents a broader customer identity
than the individual `customer_id`.

Geolocation data was also examined by ZIP-code prefix.

Some ZIP-code prefixes contain many geographical coordinate records, confirming
that a single ZIP-code prefix can map to multiple coordinate points.

---

# Step 12 — Categorical and Value Consistency

Categorical fields were profiled for:

- Number of unique values
- Missing values
- Potentially inconsistent categories

Important categorical fields included:

- `order_status`
- `payment_type`
- `review_score`
- `customer_state`
- `seller_state`
- `business_type`
- `lead_type`
- `origin`
- `product_category_name`

Two product categories were identified without corresponding English
translations:

- `pc_gamer`
- `portateis_cozinha_e_preparadores_de_alimentos`

These values should be reviewed during the transformation phase.

---

# Step 13 — Business Rule Validation

Business rules were tested against the datasets.

The following checks produced the results below:

| Validation Check | Result | Assessment |
|---|---:|---|
| Delivered orders with missing delivery dates | 9 | Review |
| Non-delivered orders with customer delivery date | 6 | Review |
| Customer delivery before purchase | 0 | Pass |
| Carrier date before purchase | 166 | Review |
| Estimated delivery before purchase | 0 | Pass |
| Invalid review scores | 0 | Pass |
| Invalid/negative product dimensions or weights | 0 | Pass |
| Negative payment values | 0 | Pass |
| Payments with zero installments | 2 | Review |
| Untranslated product categories | 2 | Review |
| Orders with invalid customer IDs | 0 | Pass |

The business-rule validation demonstrates that most critical rules passed.

However, several exceptions require investigation before the data is considered
fully analysis-ready.

---

# Step 14 — Statistical Profiling

Numeric columns were examined using:

- Minimum
- Maximum
- Mean
- Median
- Quartiles
- Standard deviation
- IQR
- Outlier counts
- Skewness

Several variables showed strong right-skewed distributions.

Notable examples include:

- `declared_monthly_revenue`
- `payment_value`
- `price`
- `freight_value`
- `product_weight_g`
- `payment_sequential`

These variables contain extreme values that should be investigated before
deciding whether transformation, capping, filtering, or retention is
appropriate.

Outliers were therefore treated as **review candidates**, not automatically as
errors.

---

# 5. Key Data Quality Findings

## Strengths

The profiling identified several positive characteristics:

- All 11 expected datasets were successfully identified.
- Candidate/master keys were unique.
- Tested foreign-key relationships had 100% match rates.
- No orphan records were found in the tested relationships.
- Major transactional datasets contained no complete duplicate rows.
- Review scores were valid.
- No negative payment values were identified.
- Product dimension/weight validation did not identify negative values.
- Order/customer relationships were structurally consistent.

## Issues Requiring Review

The following areas require attention during Phase 6:

1. High missingness in selected closed-deal attributes.
2. High missingness in review comments.
3. Missing delivery dates in selected orders.
4. Duplicate records in the geolocation dataset.
5. Multiple `customer_id` records associated with the same
   `customer_unique_id`.
6. Two product categories without English translations.
7. Carrier dates occurring before purchase dates in 166 records.
8. Two payments with zero installments.
9. Extreme values and skewed distributions in several numeric fields.
10. Six non-delivered orders containing customer delivery dates.
11. Nine delivered orders missing delivery dates.

---

# 6. Overall Data Quality Assessment

The raw datasets demonstrate **strong structural integrity**.

In particular:

- Candidate keys are valid.
- Tested relationships are intact.
- No major orphan-record problem was detected.
- Transactional datasets are largely free of complete duplicate rows.

However, the data is **not yet analysis-ready**.

Several missing-value patterns, duplicate geolocation records, categorical
inconsistencies, business-rule exceptions, and statistical outliers require
appropriate treatment or documentation.

Therefore, the overall Phase 5 assessment is:

> **Structurally suitable for further processing, but requires data cleaning
> and transformation before final analysis.**

---

# 7. Profiling Tools

The profiling was performed using:

- Python
- Pandas
- Jupyter Notebook
- Statistical analysis
- Data-quality validation rules

The main profiling notebook is:

`data_profiling.ipynb`

---

# 8. Output of Phase 5

The profiling process produced evidence for:

- Dataset structure
- Data types
- Missing values
- Candidate keys
- Referential integrity
- Relationship cardinality
- Duplicate records
- Categorical consistency
- Business-rule validation
- Statistical distributions
- Outlier identification
- Final data-quality assessment

These findings will be used as the basis for the next phase.

---

# 9. Next Phase

## Phase 6 — Data Cleaning & Transformation

The next phase will focus on converting the profiled raw datasets into
consistent, reliable, analysis-ready data.

Planned activities include:

- Handling missing values
- Standardizing data types
- Converting date/time fields
- Resolving categorical inconsistencies
- Handling duplicate geolocation records where appropriate
- Addressing business-rule exceptions
- Creating cleaned datasets
- Applying documented transformation rules
- Validating the cleaned data
- Preparing analysis-ready tables

---

## 10. Phase Status

**Phase:** 5 — Data Profiling

**Status:** ✅ Completed

**Final Assessment:**

> The Olist datasets have been systematically profiled and validated.
> Structural relationships are strong, but several data-quality issues require
> treatment during the cleaning and transformation phase.