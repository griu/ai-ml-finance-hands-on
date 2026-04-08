# Data Dictionary — Dataset D: Unsupervised Extension

**File:** `data/processed/dataset_D_unsupervised_extension.csv`
**Source:** Derived from Dataset C (numeric features only, no target or identifier)
**Rows:** 10 000 | **Columns:** 8

| Column | Type | Description |
|---|---|---|
| `credit_score` | integer | Credit score (350–850) |
| `age` | integer | Customer age in years |
| `tenure` | integer | Years as bank customer (0–10) |
| `balance` | float | Current account balance in EUR |
| `num_of_products` | integer | Number of bank products held (1–4) |
| `estimated_salary` | float | Estimated annual salary in EUR |
| `digital_usage_proxy` | integer | Monthly digital-banking logins (0–30) |
| `complaints_last_6m` | integer | Support complaints in last 6 months (0–10) |

## Notes
- This dataset is a numeric-only subset of Dataset C, without `customer_id`, `geography`, `gender`, `has_credit_card`, `is_active_member` or the target `attrition_flag`.
- Designed for unsupervised methods (K-Means, PCA, hierarchical clustering, Gaussian mixtures) where no target variable is used.
- Used in notebooks `06b`, `06d` and `06e`.
