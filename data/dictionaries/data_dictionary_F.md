# Data Dictionary — Dataset F: Deep Learning Awareness

**File:** `data/processed/dataset_F_deep_learning_awareness.csv`
**Source:** Stratified sample from Dataset C (2 000 rows, same schema)
**Rows:** 2 000 | **Columns:** 14

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
| `digital_usage_proxy` | integer | Monthly digital-banking logins (0–30) |
| `complaints_last_6m` | integer | Support complaints in last 6 months (0–10) |

## Notes
- Identical schema to Dataset C, but reduced to 2 000 rows via stratified sampling to keep neural-network training fast.
- Used in notebooks `05d` (PyTorch MLP) and `06c` (conceptual neural network overview with scikit-learn).
