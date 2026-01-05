# HR Analytics Power BI Project

This repository contains an HR analytics project that transforms raw employee data into interactive dashboards for workforce overview, retention risk, and promotion or retrenchment planning.

## Project overview

The solution combines:

- `HR Analytics Data.csv` with rich employee attributes such as demographics, role, compensation, satisfaction scores, and tenure.
- `HR employee data.csv` with a simple employee directory mapping `EmployeeNumber` to employee names.

Three Power BI pages — **Home**, **Detail**, and **Action** dashboards — provide a holistic view of headcount, gender mix, job satisfaction, overtime, attrition risk, and lists of employees who are due for promotion or likely retrenchment.

## Data model

The core relationship is based on `EmployeeNumber`, which appears in both files.

| Table | Description | Key columns |
| --- | --- | --- |
| `hr_analytics_data` | Main fact table with individual employee records and HR metrics | `Age`, `Attrition`, `BusinessTravel`, `DailyRate`, `Department`, `DistanceFromHome`, `Education`, `EducationField`, `EmployeeCount`, `EmployeeNumber`, `EnvironmentSatisfaction`, `Gender`, `HourlyRate`, `JobInvolvement`, `JobLevel`, `JobRole`, `JobSatisfaction`, `MaritalStatus`, `MonthlyIncome`, `MonthlyRate`, `NumCompaniesWorked`, `Over18`, `OverTime`, `PercentSalaryHike`, `PerformanceRating`, `RelationshipSatisfaction`, `StandardHours`, `StockOptionLevel`, `TotalWorkingYears`, `TrainingTimesLastYear`, `WorkLifeBalance`, `YearsAtCompany`, `YearsInCurrentRole`, `YearsSinceLastPromotion`, `YearsWithCurrManager`.[1] |
| `hr_employee_data` | Employee master data | `EmployeeNumber`, `Emplyee name`. |

This structure allows the dashboards to show readable employee names while slicing metrics by any HR dimension.

## Dashboards

### HR Home Dashboard

The **home** view (`HR_Home_Dashboard.jpg`) offers a high‑level snapshot.

- KPIs: total employees (1,470), male count and share (882, 60%), female count and share (588, 40%).
- Retrenchment vs on‑service counts (117 retrench, 1,353 on service) with percentages.
- Visuals:
  - `Total Emp by Service Years` bar chart showing headcount by tenure bands (e.g., 1, 2, 3, 5, 10 years).
  - `Total Emp by Job Levels` column chart across JobLevel 1–5.
  - `Total Emp by Distance Status` donut chart (very close, close, very far) using `DistanceFromHome` grouping.
  - Cards for **Due For Promotion** (72 employees, 5%) and **Not Due For Promotion** (1,398 employees, 95%).

### HR Detail Dashboard

The **detail** page (`HR_Detail_Dashboard.jpg`) focuses on satisfaction and performance.

- Job satisfaction distribution (High, Low, Medium) with counts.
- `Total Emp by OverTime` donut chart splits employees who work overtime vs those who do not.
- KPIs for **High Rating** vs **Low Rating** employees with counts and percentages, based on performance ratings.
- JobRole matrix with total employees, those marked *Will be retrenched*, and *Due for promotions* for each role (e.g., Healthcare Representative, Research Scientist, Sales Executive).
- Stacked bar chart of departments (Research & Development, Sales, Human Resources) showing side‑by‑side counts for retrenchment and promotion.

### HR Action Dashboard

The **action** page (`HR_Action_Dashboard.jpg`) lists specific employees for decision‑making.

- Two scrollable tables:
  - Employees **Due for promotions** with binary flag.
  - Employees who **Will be retrenched** with corresponding flags.
- Explanatory panel summarizing that these lists represent employees who should be considered for promotion or retirement/retrenchment.
- Left‑side KPI cards repeating core headcount and gender distribution for quick context.
