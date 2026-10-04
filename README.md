# Customer Churn Analysis - PowerCo (BCG Data Science Simulation)

## Project Overview
This project analyzes customer and pricing data from an energy provider (PowerCo) to understand why customers churn and whether offering a price discount would actually help retain them. It was completed as part of the BCG Data Science Job Simulation (Forage).

## Business Question
We investigated if price sensitivity significantly predicts customer churn. If it's not price sensitivity causing the customers to leave, then what is affecting the company to face a customer churn?

## Data
- **client_data.csv** — details for ~14,600 customers (consumption, contract dates, sales channel, margin, churn status, etc.)
- **price_data.csv** — monthly pricing history (~12 months) for each customer across off-peak, peak, and mid-peak periods

## Tasks Done
1. **Data Cleaning** — converted date columns to proper date formats, identified and handled hidden missing values (disguised as the text "MISSING"), checked for duplicates and invalid values.

3. **Exploratory Data Analysis (EDA)** — examined data types, descriptive statistics, and distributions. Visualized churn rate by sales channel, contract type, and consumption patterns.

5. **Feature Engineering** — removed a redundant column, extracted year/month/day from date columns, and created new features including customer tenure and price volatility (average and maximum price swing across periods).

7. **Modeling** — merged both datasets, converted all columns to numeric format, and trained a Decision Tree and a Random Forest Classifier to predict churn.

9. **Evaluation** — assessed model performance using accuracy, precision, recall, and F1-score (not accuracy alone, due to class imbalance), and examined feature importance to see which columns the model relied on most.

## Key Findings
- Overall churn rate was approximately **9.7%**.

- **Net margin** and **12-month consumption** were the strongest predictors of churn, not price sensitivity.

- The engineered price-volatility features did not rank as important, suggesting the original assumption (that price swings drive churn) was not strongly supported by the data.

- The model's accuracy looked high (~91%), but this was misleading due to the class imbalance, recall was low (~6.7%), meaning the model missed most actual churners. Further tuning would be needed before using this model operationally.

## Recommendation
Retention efforts should focus on low-margin, low-consumption customer segments, rather than a blanket price discount.

## Tools Used
Python (pandas, NumPy, scikit-learn, seaborn, matplotlib), Jupyter Notebook, Excel

## Files in This Repository
- `BCGsimulationcasestudy.ipynb` — full analysis: data cleaning, EDA, feature engineering, modeling, and evaluation.
- `Executive Summary for Customer Churn (BCG Simulation).pptx` — one-page executive summary of the business recommendation, in Answer-Situation-Complication-Question format.
