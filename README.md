# Uplift Modeling for Marketing Campaigns
This project compares 5 Uplift models to measure the causal effect of marketing campaigns. The goal is to identify "Persuadables" — customers who will convert only if treated. X-learner and R-learner showed the best results (Qini validation: 877,615 and 805,556). Stack: Python, CausalML, CatBoost, Scikit-learn, Pandas.
## Project Overview
This project focuses on Uplift Modeling — a technique used to measure the causal effect of a marketing campaign on customer behavior. Unlike traditional predictive models, Uplift models identify which customers are most likely to respond positively to a treatment (e.g., a discount, an ad) and which ones would convert anyway.
## Business Problem
A company wants to optimize its marketing budget by targeting only those customers who will be **positively influenced** by a campaign. Uplift modeling solves this by segmenting customers into four groups:

- Persuadables — will convert only if treated.

- Sure Things — will convert regardless of treatment.

- Lost Causes — will not convert regardless of treatment.

- Sleeping Dogs — may react negatively to treatment.
## Dataset
- **Source*: criteo-uplift.csv (Criteo Uplift Prediction Dataset)

- **Features**: 12 anonymized features (f0–f11) describing customer attributes.

- **Treatment**: treatment (1 = treated, 0 = control)

- **Targets**: conversion (binary), visit (binary), exposure (binary)
## Methodology
1. **Data Exploration** — Checked hypotheses about treatment, visit, and conversion relationships.

2. **Train/Validation Split** — 80/20 split for both visit-exposure and treatment-conversion datasets.

3. **Models Implemented**:

- S-learner (Single model with treatment as a feature)

- T-learner (Two separate models for treatment and control)

- X-learner (Cross-learner using imputed treatment effects)

- R-learner (Residual-based learner)

- Uplift Random Forest (CausalML implementation)

4. **Evaluation Metric**: Qini Score and Qini Curve — the standard metric for uplift models.

| Model          | Qini Score (Train) | Qini Score (Validation) |
|----------------|-------------------:|------------------------:|
| S-learner      | 2,465,367          | 608,991                 |
| T-learner      | 2,031,344          | 541,990                 |
| X-learner      | 3,506,343          | 877,615                 |
| R-learner      | 3,217,531          | 805,556                 |
| Uplift Forest  | -620,264           | -149,373                |

**Conclusion**: X-learner and R-learner outperformed other approaches, showing the highest Qini scores on validation data.

**Technologies Used**
- Python
- CausalML
- CatBoost
- Scikit-learn
- Pandas, NumPy
- Matplotlib, Seaborn
- Jupyter Notebook

Oleksii Panin — [LinkedIn](https://www.linkedin.com/in/oleksii-panin-69a509342/) | [GitHub](https://github.com/ALEXP021)
