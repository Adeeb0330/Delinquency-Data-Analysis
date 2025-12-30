📊 Customer Delinquency Analysis & Power BI Dashboard
📌 Project Overview

This project analyzes customer delinquency behavior by combining Excel for data cleaning, Python for feature engineering, and Power BI for visualization. The goal is to identify high-risk customers, understand delinquency drivers, and present insights through an interactive dashboard for business and risk teams.

🎯 Objectives

Clean and standardize raw customer credit data

Engineer meaningful risk indicators using Python

Analyze delinquency trends and customer risk segments

Build an executive-level Power BI dashboard for decision-making

🧰 Tools & Technologies

Excel: Data cleaning & missing value treatment

Python: Pandas, NumPy (feature engineering)

Power BI: Power Query, DAX, Interactive Visualizations

Data Format: CSV

🗂 Dataset Description

The dataset includes customer-level credit and payment attributes such as:

Demographics: Age, Location, Employment Status

Financials: Income, Loan Balance, Credit Utilization, DTI Ratio

Credit Behavior: Missed Payments, Delinquent Account

Monthly Payment Status: Month_1 to Month_6 (categorical)

Risk Metrics: Delinquency Rate, Risk Band, Utilization & DTI Flags

🔄 Project Workflow
1️⃣ Data Cleaning (Excel)

Removed inconsistencies and formatting issues

Handled missing values using median imputation for:

Income

Credit Score

Loan Balance

Ensured correct data types for numerical analysis

Exported cleaned data as CSV for further processing

2️⃣ Feature Engineering (Python)

Python was used to derive new calculated columns that enhance risk analysis.

Key transformations include:

Delinquency Rate calculation

Delinquency Risk Band classification (Low / Medium / High)

High Credit Utilization Flag

High Debt-to-Income (DTI) Flag

Loan Size Categorization (Small / Medium / Large)

import pandas as pd

df = pd.read_csv("cleaned_delinquency_data.csv")

df['Delinquency_Rate'] = df['Missed_Payments'] / df['Account_Tenure']

df['High_Utilization_Flag'] = (df['Credit_Utilization'] > 0.7).astype(int)
df['High_DTI_Flag'] = (df['Debt_to_Income_Ratio'] > 0.4).astype(int)

df['Delinquency_Risk_Band'] = pd.cut(
    df['Delinquency_Rate'],
    bins=[-1, 0.2, 0.5, 1],
    labels=['Low', 'Medium', 'High']
)

df.to_csv("final_delinquency_data.csv", index=False)

3️⃣ Data Transformation (Power BI)

Imported the final CSV file into Power BI

Unpivoted categorical monthly columns (Month_1 → Month_6)

Created a normalized structure for trend analysis

Built relationships and optimized data model

4️⃣ DAX Measures & KPIs

Key measures created using DAX:

Total Customers

Delinquent Customers

Monthly Missed Payments

Monthly Delinquency Rate

High-Risk Customer Count

Average Credit Score (High Risk)

These measures dynamically respond to slicers and filters.

📊 Dashboard Visualizations
🔹 Customer Profile

Age & income distribution

Employment status by location

🔹 Credit Risk Analysis

Credit score distribution

Missed payments vs delinquency rate

Credit utilization impact on risk

🔹 Temporal Analysis

Monthly delinquency trends

Missed payments by month

🔹 Risk Band & Executive KPIs

Risk band distribution

High-risk customers by location and employment status

KPI cards for management monitoring

📈 Key Insights

Customers with high credit utilization and DTI show higher delinquency risk

Missed payments strongly correlate with delinquency rate

Specific customer segments contribute disproportionately to high-risk bands

Monthly trend analysis highlights early warning signals

📌 Business Impact

Enables proactive identification of risky customers

Supports data-driven credit risk decisions

Provides an executive-ready reporting solution

🚀 Future Enhancements

Integrate machine learning models for delinquency prediction

Automate data ingestion and refresh

Deploy dashboard to Power BI Service with scheduled refresh
