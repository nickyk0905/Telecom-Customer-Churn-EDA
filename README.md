# Telecom Customer Churn Analysis

Exploratory data analysis on a telecom company's customer data, using Python (Pandas, Seaborn) to understand why customers churn and identify actionable retention levers.

## Dataset

`Customer_Churn.csv` — 7,043 customers, 21 columns covering demographics, account details (tenure, contract, charges), subscribed services, and churn status.

## Approach

- **Cleaned** the data — fixed `TotalCharges`, recoded `SeniorCitizen`, checked nulls/duplicates
- **Analyzed** churn against tenure, contract type, add-on services, internet type, payment method, and monthly charges

## Key Findings

- Overall churn rate: 26.54% (1,869 of 7,043 customers)
- Churn is front-loaded — 47.7% churn in year 1 vs. 9.5% after 49+ months
- Month-to-month contracts churn far more than annual/biennial plans
- Customers without TechSupport, OnlineSecurity, OnlineBackup, or DeviceProtection churn 2–3x more
- Fiber optic users churn at 41.9%, more than double DSL users
- Senior citizens churn at 41.68%, well above the average

Full write-up with methodology and detailed findings: [`docs/Telecom_Customer_Churn_Analysis_Report.docx`](docs/Telecom_Customer_Churn_Analysis_Report.docx)

## How to Run

```bash
git clone <your-repo-url>
cd telecom-churn-analysis
pip install -r requirements.txt
jupyter notebook notebooks/Teleco_Customer_Churn_EDA.ipynb
```

## Tools

Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook
