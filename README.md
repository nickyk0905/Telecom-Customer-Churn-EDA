# Telecom Customer Churn Analysis

An exploratory data analysis (EDA) project on a telecom company's customer data, aimed at understanding **why customers churn** and identifying actionable levers to reduce it.

## Business Problem

The company is losing a significant portion of its customers to churn. This analysis digs into customer demographics, account details, and subscribed services to identify **which customers are at risk and why**, so the business can act early and maximize customer lifetime value.

## Dataset

- **File:** `Customer_Churn.csv`
- **Rows:** 7,043 customers
- **Columns:** 21 (demographics, account info, subscribed services, and churn label)
- **Key fields:** `customerID`, `Gender`, `SeniorCitizen`, `Partner`, `Dependents`, `Tenure`, `Contract`, `PaymentMethod`, `MonthlyCharges`, `TotalCharges`, `Churn`, plus service add-ons (`InternetService`, `OnlineSecurity`, `OnlineBackup`, `DeviceProtection`, `TechSupport`, `StreamingTV`, `StreamingMovies`, `PhoneService`, `MultipleLines`)

## Project Structure

```
telecom-churn-analysis/
├── data/
│   └── Customer_Churn.csv
├── notebooks/
│   └── Teleco_Customer_Churn_EDA.ipynb
├── outputs/              # exported charts (optional)
├── requirements.txt
├── README.md
└── .gitignore
```

## Approach

1. **Data Loading** — read the raw CSV into a DataFrame
2. **Data Inspection** — shape, dtypes, summary stats, churn value counts
3. **Data Cleaning**
   - Fixed `TotalCharges` (blank strings → 0, converted to float)
   - Recoded `SeniorCitizen` (1/0 → Yes/No)
   - Checked for nulls and duplicate records
   - Renamed columns for consistency (`gender` → `Gender`, `tenure` → `Tenure`)
4. **Exploratory Data Analysis** — churn distribution, and churn broken down by gender, senior citizen status, contract type, tenure, subscribed services, payment method, and monthly charges

## Key Findings

- **Overall churn rate:** 26.54% (1,869 of 7,043 customers)
- **Tenure:** Churn is heavily front-loaded — 47.7% churn in the first year vs. 9.5% after 49+ months
- **Contract type:** The biggest driver of churn — Month-to-month customers churn far more than One-year/Two-year customers, mostly within their first year
- **Add-on services:** Customers without TechSupport, OnlineSecurity, OnlineBackup, or DeviceProtection churn 2–3x more than those who have them; streaming add-ons barely matter
- **Internet service:** Fiber optic users churn at 41.9% — more than double DSL users (19%)
- **Monthly charges:** Churned customers pay more per month (\$74.44 vs \$61.27) but stay roughly half as long, generating far less total revenue
- **Senior citizens:** Churn at 41.68%, well above the 26.54% overall average
- **Payment method:** Electronic Check users churn the most
- **Gender:** No meaningful impact on churn

## Recommendations

- Focus retention efforts on the first 12 months (onboarding support, check-ins, loyalty perks)
- Incentivize longer contracts to shift Month-to-month customers toward annual plans
- Bundle and promote protective add-ons (TechSupport, OnlineSecurity) — strongest retention levers in the data
- Investigate Fiber optic service specifically for pricing/reliability issues
- Offer loyalty discounts to high-paying customers to reduce price-driven churn
- Prioritize senior citizens in retention programs
- Encourage a shift away from Electronic Check toward automatic payment methods

## Tools Used

- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Jupyter Notebook

## How to Run

```bash
git clone <your-repo-url>
cd telecom-churn-analysis
pip install -r requirements.txt
jupyter notebook notebooks/Teleco_Customer_Churn_EDA.ipynb
```

## Author

Nicky Kumari
