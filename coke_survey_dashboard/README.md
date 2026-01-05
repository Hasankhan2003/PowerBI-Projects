This repository contains a small analytics project that explores market–survey data for Coca‑Cola’s **RedBox** loyalty feature in the CCI NEXT retailer application.

## Project overview

The dataset combines three survey sources:

- Field‑visit survey of outlets capturing REDBOX usage, app awareness, assistance needs, and qualitative comments (Table 1).
- Aggregated awareness and barrier counts for Red Box and CCI NEXT app usage (Table 2).
- Call‑center survey of registered CCI NEXT users with account‑level points, redemption behavior, and call remarks (Table 3).

The dashboards in `coke_dashboard.jpg` and `coke_dashboard_2.jpg` summarize key KPIs such as points earned/redeemed, redemption rate, call status, app and REDBOX awareness, usage, and clarity of communication.

## Dashboards

The repository includes two Power BI / BI-style report images:

- **Customer points & awareness dashboard** (`coke_dashboard.jpg`):  
  - Shows total points earned (1.36M), total points redeemed (344K), and overall 25% redemption rate.
  - Visualizes call status, redemption vs balance, and detailed breakdown of Red Box awareness and app‑usage barriers (e.g., no Android phone, not using CCI NEXT, issues with the app, preseller using the app on behalf of the customer).

- **RedBox market survey dashboard** (`coke_dashboard_2.jpg`):  
  - Summarizes usage of REDBOX (64%), redemption of points (52%), push‑notification reach (61%), story views (45%), and total surveyed outlets (33).
  - Includes distributions for CCI NEXT awareness, clarity of REDBOX campaign text, and sources of assistance (independent, not using, staff/family, FSE).

## Data structure

The core tables used to build the dashboards are:

| Table | Description | Key fields |
| --- | --- | --- |
| `field_survey_outlets` | Outlet‑level visit survey (Table 1) | `Timestamp`, `Outlet Name`, `Outlet Code`, `ASM Name`, `FSE Name`, `Sell CocaCola?`, `Aware CCI NEXT?`, `Using REDBOX?`, `Assistance Source`, `Redeeming Independently?`, `Receiving Push Notifications?`, `Viewing Stories?`, `Campaign Text Clarity`, `Informed about REDBOX?`, `Comments`. |
| `awareness_barriers_summary` | Aggregated counts for Red Box and app‑related awareness and barriers (Table 2) | `Awareness About Red Box?`, `Count`. |
| `account_call_survey` | Account‑level CCI NEXT call survey with Red Box questions (Table 3) | `Account Number`, `Account Name`, `Last Login Status`, `Earned Points(New)`, `Redeemed Points(New)`, `Balance`, `User Phone`, `User`, `Survey From`, `Survey Number`, Q1–Q4 responses on awareness, ordering behavior, Red Box points knowledge, redemption knowledge, `Remarks`, `Call Status`, `Total Time`, `Date`.

