# Data Dictionary — Dataset C: Bank Customer Attrition (Core)

**File:** `data/processed/dataset_C_bank_attrition_core.csv`
**Source:** Adapted from `data/raw/Churn_Modelling.csv` (Kaggle Bank Churn dataset)
**Rows:** 10 000 | **Columns:** 14

| Column | Type | Description |
|---|---|---|
| `customer_id` | integer | Unique customer identifier |
| `credit_score` | integer | Credit score (350–850) |
| `geography` | categorical | Country: France, Spain, Germany |
| `gender` | categorical | Male or Female |
| `age` | integer | Customer age in years |
| `tenure` | integer | Years as bank customer (0–10) |
| `balance` | float | Current account balance in EUR |
| `num_of_products` | integer | Number of bank products held (1–4) |
| `has_credit_card` | integer (0/1) | 1 = has credit card, 0 = does not |
| `is_active_member` | integer (0/1) | 1 = active member, 0 = inactive |
| `estimated_salary` | float | Estimated annual salary in EUR |
| `attrition_flag` | integer (0/1) | **TARGET**: 1 = customer left the bank, 0 = stayed |
| `digital_usage_proxy` | integer | **DERIVED TEACHING FEATURE** (not in original data): Monthly digital-banking logins (0–30). Created for classroom use to illustrate digital engagement as a predictor. |
| `complaints_last_6m` | integer | **DERIVED TEACHING FEATURE** (not in original data): Support complaints in last 6 months (0–10). Created for classroom use to illustrate service-interaction signals. |

## Transformations applied
- Dropped `RowNumber` and `Surname` from original.
- Renamed all columns to snake_case.
- Renamed `Exited` → `attrition_flag` for clarity.
- **Added 2 derived teaching features** (seed=42) — these columns do not exist in the original Kaggle dataset and were created specifically for classroom exercises:
  - `digital_usage_proxy`: Poisson-distributed, λ=14 for active members, λ=5 for inactive. Simulates digital-banking engagement.
  - `complaints_last_6m`: Poisson-distributed, λ=1.8 for churned customers, λ=0.6 for retained. Simulates service-interaction history.

## Target variable
- `attrition_flag`: binary (0/1).
- Class distribution: ~20% churned, ~80% retained.
- Sufficient class imbalance for threshold-thinking exercises.

## Notes
- This is the **single core modelling dataset** used across notebooks 04–06.
- The original 12 columns come from a public Kaggle dataset; the 2 added columns (`digital_usage_proxy`, `complaints_last_6m`) are **derived teaching features** created for classroom use — they do not represent real observations.
- No data leakage by design (derived features are correlated with target but not deterministic).
