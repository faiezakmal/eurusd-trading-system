# Credit Risk Model Pipeline

An end-to-end machine learning pipeline for predicting credit default probability using the German Credit dataset.

---

## Dataset

**Source:** German Credit Dataset (Prof. Hofmann, UCI ML Repository)  
**Size:** 1,000 applicants · 20 features · Binary target (Good / Bad credit)

Features include: loan duration, credit amount, employment history, savings, housing status, age, job type, and more.

---

## Pipeline

```
Data Loading & Inspection
    └── Shape, dtypes, missing values, unique value counts

Exploratory Data Analysis
    ├── Age distribution
    ├── Feature cross-tabulations
    └── Seaborn visualisations

Feature Engineering
    ├── Categorical encoding
    ├── Ordinal mapping
    └── Train / test split

Modelling
    ├── [Model(s) — see notebook]
    └── Hyperparameter tuning

Evaluation
    ├── Confusion matrix
    ├── Classification report (precision / recall / F1)
    ├── ROC-AUC curve
    └── Feature importance
```

---

## Business Context

Credit risk modelling is a core function at banks and lenders. A well-calibrated model:
- Reduces default losses by identifying high-risk applicants early
- Ensures fair, consistent lending decisions
- Provides regulators with an auditable scoring methodology

---

## Files

| File | Description |
|---|---|
| `predicting-credit-risk-model-pipeline.ipynb` | Full ML pipeline notebook |

---

## Setup

```bash
pip install pandas numpy matplotlib seaborn scikit-learn ipykernel
```
