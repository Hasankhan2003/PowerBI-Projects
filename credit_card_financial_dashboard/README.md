# Credit Card Analytics Dashboard

This repository contains an end‑to‑end analytics project that combines credit card **transaction** data with **customer** profile data to build interactive BI dashboards for portfolio monitoring and customer insights.

## Project overview

The solution uses two core datasets:

- `credit_card.csv` with weekly transaction and product metrics such as card category, credit limits, utilization, revenue, and interest earned.
- `customer.csv` with demographics, socio‑economic attributes, and satisfaction scores for each client.

Two dashboards, **Credit Card Customer Report** and **Credit Card Transaction Report**, summarize revenue, income, interest, and behavior across segments like age, income, education, dependency, marital status, card category, and spend type.

## Data model

The analytical model links transaction‑level and customer‑level data through the common field `Client_Num`.

| Table | Description | Key columns |
| --- | --- | --- |
| `credit_card` | Weekly credit card KPIs at client level | `Client_Num`, `Card_Category`, `Annual_Fees`, `Activation_30_Days`, `Customer_Acq_Cost`, `Week_Start_Date`, `Week_Num`, `Qtr`, `current_year`, `Credit_Limit`, `Total_Revolving_Bal`, `Total_Trans_Amt`, `Total_Trans_Vol`, `Avg_Utilization_Ratio`, `Use Chip`, `Exp Type`, `Interest_Earned`, `Delinquent_Acc`.
| `customer` | Customer profile and satisfaction | `Client_Num`, `Customer_Age`, `Gender`, `Dependent_Count`, `Education_Level`, `Marital_Status`, `state_cd`, `Zipcode`, `Car_Owner`, `House_Owner`, `Personal_loan`, `contact`, `Customer_Job`, `Income`, `Cust_Satisfaction_Score`. |

The relationship enables slicing transaction KPIs by demographic and behavioral attributes.

## Dashboards

### Credit Card Customer Report

The **customer‑focused** dashboard (`customer_dashboard.jpg`) highlights how portfolio performance varies by customer characteristics.

Key features:

- High‑level KPIs: total revenue (57M), income (588M), total interest (8M), and average customer satisfaction score (3.19).
- Trend view: `Revenue by Week` line chart for 2023 with filters for quarter, card category, week, and gender.
- Segment views:
  - Revenue by income group (Low/Medium/High).
  - Revenue by education level, dependency count, age group, and marital status.
  - Matrix table summarizing income, revenue, and interest earned by customer job (e.g., blue‑collar, businessman, self‑employed).

### Credit Card Transaction Report

The **transaction‑focused** dashboard (`Transaction_report.jpg`) analyses how cards are used and which products drive value.

Key features:

- Portfolio KPIs: revenue (57M), total transaction amount (46M), income (588M), and total transaction count (667K).
- Card category performance table with revenue, total transaction amount, and interest earned by category (Blue, Silver, Gold, Platinum).
- QTR performance: combined bar‑and‑line chart for quarterly revenue and transaction count.
- Behavioral breakdowns:
  - Revenue by expense type (Bills, Entertainment, Fuel, Grocery, Food).
  - Revenue by customer job and education level.
  - Revenue by usage type (Chip, Swipe, Online) via donut chart.

