# SmartKart Churn Risk Intelligence

> A customer-churn analytics project that transforms messy retail data into an actionable churn-risk report.

## Overview

SmartKart Churn Risk Intelligence identifies customers who may be at risk of leaving and helps prioritize retention efforts. The project covers data-quality checks, churn analysis, customer risk scoring, and business-ready reporting.

## Business question

**Which SmartKart customers are most likely to churn, and where should retention efforts be focused first?**

## Data

| File | Purpose | Rows |
| --- | --- | ---: |
| `SmartKart_dirty_100_rows.csv` | Raw customer dataset for cleaning and analysis | 100 |
| `smartkart_churn_risk_report.csv` | Customer-level churn-risk output | 19 |

The raw dataset includes:

- `Customer_ID`
- `Age`
- `Monthly_Spend`
- `Complaints`
- `Churn`

The churn-risk report includes:

- `Customer_ID`
- Customer attributes
- Actual and predicted churn
- Churn probability
- Risk label

## Data-quality checks

The raw dataset contains realistic issues that should be addressed before analysis or modelling:

- Duplicate customer records
- Missing values in age, monthly spend, and complaints
- Invalid or implausible ages
- Negative and unusually high monthly-spend values
- Unusually high complaint counts

These issues make the project suitable for demonstrating data cleaning, validation, outlier handling, and repeatable preprocessing.

## Risk-report snapshot

The supplied churn-risk report flags **12 of 19 customers** as **Likely to Churn**.

Within this scored subset:

- True positives: 10
- False positives: 2
- True negatives: 7
- False negatives: 0
- Observed accuracy: 89.5%

> These results describe a small supplied report. Any production model should be validated using a clearly defined holdout dataset before business use.

## Suggested workflow

1. Load and inspect the raw customer dataset.
2. Identify missing values, duplicates, invalid values, and outliers.
3. Clean the data using documented business rules.
4. Explore relationships between customer attributes and churn.
5. Train and evaluate a churn-classification model.
6. Score customers by churn probability.
7. Label high-risk customers and share findings with retention teams.

## Potential business actions

- Contact high-risk customers with frequent complaints before they leave.
- Investigate recurring service issues driving complaints.
- Personalize retention offers based on customer spending levels.
- Measure which retention campaigns successfully reduce churn.

## Recommended project structure

```text
smartkart-churn-risk-intelligence/
├── data/
│   ├── raw/
│   │   └── SmartKart_dirty_100_rows.csv
│   └── processed/
│       └── smartkart_churn_risk_report.csv
├── notebooks/
├── src/
├── reports/
├── README.md
└── requirements.txt
```

## Technologies

Suggested tools for this project:

- Python
- pandas
- scikit-learn
- Jupyter Notebook
- Matplotlib / Seaborn

## License

This project can be released under the MIT License.
