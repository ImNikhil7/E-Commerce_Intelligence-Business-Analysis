# Phase 6 — Data Standardization & Validation

## Objective

Standardize important data types and values across the ShopSphere datasets and validate that the prepared datasets maintain their structural and relational integrity.


> For the overall ShopSphere project overview, see the
> [main project README](../README.md).

---

## Step 12 — Data Type & Value Standardization

The datasets were reviewed and standardized where appropriate.

### Data type standardization

- Identifier columns were standardized as string values.
- Date/time columns were converted to datetime format.
- `has_company` was converted to nullable boolean.
- `has_gtin` was converted to nullable boolean.
- `average_stock` was converted into a numeric ordinal field, `average_stock_level`.

### `average_stock` mapping

| Original value | `average_stock_level` |
|---|---:|
| `1-5` | 1 |
| `5-20` | 2 |
| `20-50` | 3 |
| `50-200` | 4 |
| `200+` | 5 |
| `unknown` | `<NA>` |
| Missing | `<NA>` |

### Revenue review

`declared_monthly_revenue` was reviewed for invalid values.

- Missing values: 0
- Negative values: 0
- Zero values: 797
- Positive values: 45
- Maximum value: 50,000,000

The field was **not transformed** because the high number of zero values and extreme positive values require business context before deciding whether they represent valid business values, unavailable reporting, or outliers.

No unjustified values were removed or modified.

---

## Step 13 — Structural Validation

All 11 prepared datasets were checked against their expected row and column counts.

### Result

All datasets passed structural validation.

- No unexpected rows were removed.
- No unexpected columns were removed.
- No unexpected columns were added.
- `closed_deals` contains 15 columns because `average_stock_level` was added intentionally.

**Status: PASS**

---

## Step 14 — Key & Relationship Validation

Key relationships between datasets were validated.

### Results

| Relationship | Invalid records | Status |
|---|---:|---|
| Orders → Customers | 0 | PASS |
| Order Items → Orders | 0 | PASS |
| Order Items → Products | 0 | PASS |
| Order Items → Sellers | 0 | PASS |
| Order Payments → Orders | 0 | PASS |
| Order Reviews → Orders | 0 | PASS |
| Category Translation → Products | 0 | PASS |

No invalid foreign-key relationships were identified.

**Status: PASS**

---

## Phase 6 Final Status

| Step | Description | Status |
|---|---|---|
| 12 | Data Type & Value Standardization | COMPLETE |
| 13 | Structural Validation | COMPLETE |
| 14 | Key / Relationship Validation | COMPLETE |

### Overall Status

**PHASE 6 — COMPLETE**

The prepared datasets are structurally consistent, have standardized important data types, and maintain valid relationships across the major analytical tables.

Known review items have been documented without applying unsupported transformations.