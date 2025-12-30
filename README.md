.

📊 Customer Delinquency Analysis & Power BI Dashboard
📌 Project Overview

This project focuses on analyzing customer delinquency behavior using Python for data preprocessing and Power BI for interactive visualization. The objective is to identify high-risk customers, analyze payment patterns, and provide executive-level insights to support credit risk decision-making.

🎯 Objectives

Clean and preprocess delinquency data using Python

Transform categorical monthly payment data for trend analysis

Identify key risk indicators such as missed payments and delinquency rate

Build an interactive Power BI dashboard for business users

🧰 Tools & Technologies

Python: Pandas, NumPy

Power BI: Data Modeling, Power Query, DAX, Interactive Visuals

Data Format: CSV

🗂 Dataset Description

The dataset contains customer-level credit and payment information, including:

Demographics (Age, Location, Employment Status)

Financial metrics (Income, Loan Balance, DTI Ratio, Credit Utilization)

Credit behavior (Missed Payments, Delinquent Account)

Monthly payment status (Month_1 to Month_6)

Risk indicators (Delinquency Rate, Risk Band)

🔄 Project Workflow
1️⃣ Data Cleaning & Preparation (Python)

Loaded raw delinquency dataset using Pandas

Handled incorrect data types (converted income and loan fields)

Verified missing values and data consistency

Exported the cleaned dataset as a CSV file for Power BI

import pandas as pd

df = pd.read_csv("raw_delinquency_data.csv")

# Basic cleaning
df['Income'] = df['Income'].str.replace(',', '').astype(float)
df.to_csv("cleaned_delinquency_data.csv", index=False)

2️⃣ Data Transformation (Power BI – Power Query)

Imported cleaned CSV into Power BI

Unpivoted categorical monthly columns (Month_1 → Month_6)

Converted data into a normalized format for time-series analysis

Created calculated columns and measures for analysis

3️⃣ DAX Measures Created

Key metrics calculated using DAX:

Total Customers

Delinquent Customers

Monthly Missed Payments

Monthly Delinquency Rate

High-Risk Customer Count

These measures dynamically respond to filters and slicers.

4️⃣ Dashboard Visualizations

The Power BI dashboard includes:

🔹 Customer Demographics

Age and income distribution

Employment status by location

🔹 Credit Risk Analysis

Credit score distribution

Missed payments vs delinquency rate (scatter plot)

Credit utilization impact on risk

🔹 Temporal Analysis

Monthly delinquency trend (line chart)

Missed payments by month

🔹 Risk Band & Executive KPIs

Risk band distribution

High-risk customers by location and employment

KPI cards for executive monitoring

📈 Key Insights

Higher missed payments strongly correlate with increased delinquency rate

Customers with high DTI and credit utilization show elevated risk

Certain locations and employment groups contribute more to high-risk segments

Delinquency trends vary across months, highlighting early warning signals

📌 Business Impact

Helps financial institutions proactively identify risky customers

Supports credit risk monitoring and decision-making

Provides an executive-ready dashboard for stakeholders

🚀 Future Enhancements

Integrate machine learning models for delinquency prediction

Automate data refresh using APIs

Deploy Power BI dashboard to Power BI Service with scheduled refresh
