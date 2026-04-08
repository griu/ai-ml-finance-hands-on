# Instructor Teaching Map

## Course overview

| Session | Date | Duration | Focus |
|---------|------|----------|-------|
| Session 1 | 8 April 2026 | 3 h | Python introduction & data literacy |
| Session 2 | 15 April 2026 | 3 h | EDA wrap-up & modelling-table construction |
| Session 3 | 22 April 2026 | 3 h | Baseline models → XGBoost → validation & business interpretation |

---

## Session 1 — Python Introduction & Data Literacy

| Notebook | Mode | Notes |
|----------|------|-------|
| **01 — Python Setup and First Steps** | In-class (selective) | Walk through environment setup, run first cells together. Skip sections students can follow on their own. ~30 min. |
| **02 — Python Warmup for Finance Students** | In-class (main guided practice) | Core Python essentials: data structures, pandas intro, finance-flavoured exercises. ~90 min. |
| **03 — Descriptive Statistics and EDA** | Begin in class if time allows; otherwise assign as homework | Start the data-reading and EDA sections. Students complete the rest before Session 2. |

**Between Sessions 1 & 2:** Students finish Notebook 03, complete the self-practice exercises in Notebooks 02 and 03, and optionally run **03b — Official Statistics and API Practice for Finance** as the first external-data extension of Topic 1.

---

## Session 2 — Data & Framing

| Notebook | Mode | Notes |
|----------|------|-------|
| **03 — Descriptive Statistics and EDA** (continued) | Quick review / Q&A | Recap key EDA findings; answer student questions. ~15 min. |
| **04 — Building the First Modelling Table** | In-class (guided lab) | Target definition, missing values, feature engineering, train/test split. ~60 min. |

**Between Sessions 2 & 3:** Students review Notebook 04 self-practice tasks and read the introductory markdown cells of Notebook 05.

---

## Session 3 — Modelling & AI Methods

| Notebook | Mode | Notes |
|----------|------|-------|
| **05 — Linear and Logistic Baseline Models** | In-class | Establish supervised baselines, first metrics, interpretation. ~60 min. |
| **05b — Decision Trees, Ensembles and XGBoost** | In-class (main ML content) | Trees → random forests → boosting → XGBoost. Central hands-on AI example. ~90 min. |
| **06 — Validation, Regularisation, XGBoost & Business Interpretation** | In-class (closing) | Validation discipline, class imbalance, feature importance, error analysis, business recommendations. ~90 min. |

**After Session 3:** Students complete self-practice tasks in Notebooks 05, 05b, and 06. Optionally explore the enrichment notebooks below.

---

## Optional Enrichment (Self-Study)

These notebooks are **not covered in class**. They are designed for motivated students or as additional homework.

| Notebook | Topic | Estimated time |
|----------|-------|---------------|
| **06b — Temporal, Spatial & Unsupervised Awareness** | Time-series awareness, unsupervised teaser (K-Means on Dataset D) | ~45 min |
| **06c — Neural Networks & Deep Learning Awareness** | Conceptual deep-learning overview, MLP demo (Dataset F) | ~45 min |
| **06d — K-Means, PCA & Sentiment in Finance** | Clustering, dimensionality reduction, keyword-based sentiment (Datasets D & G) | ~45 min |

---

## Datasets used per session

| Session | Datasets |
|---------|----------|
| Session 1 | A (Python warmup), B (EDA), official-statistics API practice |
| Session 2 | B (EDA recap), C (bank attrition — core modelling) |
| Session 3 | C (bank attrition — models, validation, interpretation) |
| Optional enrichment | D (unsupervised extension), E (temporal), F (deep-learning awareness), G (sentiment headlines) |

---

## Self-practice summary

Every core notebook ends with a **Self-Practice** section containing 4–6 exercises that reinforce the session material. The optional notebooks also include self-practice tasks. No additional exercise sheets are needed.

## Additional compact notebooks added for programme alignment

These notebooks extend Topic 2 coverage so the theory can map more explicitly to the official programme structure:

- `04a_data_structures_for_finance.ipynb` → **2.2.2.2 Data structures: tables, graphs, trees, etc.**
- `04b_data_treatment_for_model_ready_data.ipynb` → **2.2.2.3 Data treatment**
- `05c_compact_supervised_methods_nb_svm_knn.ipynb` → **2.3.1.c Naïve Bayes / SVM / k-NN**
- `05d_supervised_neural_networks_with_pytorch.ipynb` → **2.3.1.d Neural networks within supervised ML**
- `06e_hierarchical_clustering_and_gaussian_mixtures.ipynb` → **2.3.2.b Hierarchical clustering / Gaussian mixtures**
- `06f_association_rules_apriori_for_finance.ipynb` → **2.3.2.c Association rules / Apriori**

Design principle: these are **compact notebooks**. They do not replace the core pathway, but they ensure that no major Topic 2 sub-point remains without a practical example.
