# Data Dictionary — Dataset B: Descriptive Statistics & EDA

**File:** `data/processed/dataset_B_descriptive_stats_eda.csv`
**Source:** Adapted from `data/raw/Facturas_empresa_update202504.csv` (original in Spanish)
**Rows:** 45 | **Columns:** 10

| Column | Type | Description |
|---|---|---|
| `invoice_id` | integer | Sequential invoice identifier |
| `date` | string (ISO) | Invoice date (YYYY-MM-DD) |
| `month_name` | categorical | Calendar month in English (January, February, …) |
| `customer_segment` | categorical | Customer label: customer_A, customer_B, customer_C, customer_D |
| `invoice_paid` | categorical | Payment status: "yes" or "no" |
| `vat_type` | categorical | VAT category: standard, reduced, super_reduced |
| `vat_pct` | float | VAT percentage applied |
| `invoice_amount` | float | Pre-tax invoice amount in EUR |
| `vat_amount` | float | VAT amount in EUR (**contains 3 missing values for EDA practice**) |
| `total_amount` | float | Total invoiced amount including VAT |

## Transformations applied
- Column names translated from Spanish to English.
- `mes` (month) values translated: Enero→January, Febrero→February, etc.
- `factura_pagada` translated: si→yes, no→no.
- `tipo_IVA` translated: normal→standard, reducido→reduced.
- `cliente` values renamed: clienteA→customer_A, etc.
- `fecha` parsed to ISO date format (YYYY-MM-DD).
- 3 `vat_amount` values set to NaN (at random indices) for missing-value exercises.

## Notes
- Not expanded beyond original 45 rows (per user constraint).
- Suitable for descriptive statistics, grouped summaries, missing-value handling, basic plots.
