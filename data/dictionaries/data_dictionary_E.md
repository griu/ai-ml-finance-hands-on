# Data Dictionary — Dataset E: Time Awareness

**File:** `data/processed/dataset_E_time_awareness.csv`
**Source:** Adapted from `data/raw/Ventas_inversion_update202504.csv` (original in Spanish)
**Rows:** 46 | **Columns:** 4

| Column | Type | Description |
|---|---|---|
| `date` | string (ISO) | First day of the year in ISO format (YYYY-01-01), added for temporal-split exercises |
| `year` | integer | Calendar year (1980–2018) |
| `investment_index` | float | Investment level index (dimensionless, original units from source) |
| `sales_index` | float | Sales level index (dimensionless, original units from source) |

## Transformations applied
- Column names translated from Spanish to English: `Fecha_anual` → `year`, `Inversion` → `investment_index`, `Ventas` → `sales_index`.
- Decimal separator converted from comma to dot (source used `;` delimiter and `,` decimal).
- `date` column added as `YYYY-01-01` derived from `year`, to provide a parseable datetime for temporal exercises.

## Units
- `investment_index` and `sales_index` are **index values**, not absolute currency amounts. They represent relative magnitudes suitable for trend and correlation analysis.

## Intended teaching use
- **Time ordering:** show that row order matters when data has a temporal dimension.
- **Temporal train/test split:** demonstrate why random splits are inappropriate for time-ordered data.
- **Lag awareness:** create lagged variables (e.g. previous-year investment) and discuss look-ahead bias.
- **Rolling mean awareness:** compute simple rolling averages to illustrate smoothing and trend extraction.
- **Leakage risk:** discuss how using future information in features breaks model validity.

## Notes
- This is a very small dataset (46 annual observations). It is not intended for serious modelling — only for conceptual awareness of temporal structure.
- Used in notebook `06b_optional_temporal_spatial_and_unsupervised_awareness.ipynb`.
