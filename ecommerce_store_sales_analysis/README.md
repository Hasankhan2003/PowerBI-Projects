This repository contains a Power BI / BI project that analyses **sales performance** using order‑level and line‑item‑level data to create an interactive Sales Dashboard.

## Project overview

The model combines two CSV files:

- `orders.csv` with order‑header information such as customer name, order date, and geographic attributes.
- `details.csv` with financial metrics and product details such as amount, profit, quantity, category, and payment mode.

The **Sales Dashboard** visualizes total sales, orders, profit, delivery performance, and multiple breakdowns by segment, category, region, payment mode, and sub‑category.

## Data model

Tables are joined using the common `Order ID` field to relate each order with its detailed line items.

| Table | Description | Key columns |
| --- | --- | --- |
| `orders` | Order‑level information | `Order ID`, `Order Date`, `CustomerName`, `State`, `City`. |
| `details` | Order item and financials | `Order ID`, `Amount`, `Profit`, `Quantity`, `Category`, `Sub-Category`, `PaymentMode`. |

This structure enables aggregation of revenue and profit across time, geography, customers, and product hierarchy.

## Dashboard features

The main report page is `sales_dashboard.jpg` and includes:

- KPI tiles: total **Sales** (1.57M), **Orders** (22K), **Profit** (175K), and **Avg. Delivery Date** (average shipping/delivery time).
- Segment analysis:
  - Sales by Segment (Consumer, Corporate, Home Office) shown as a donut chart.
  - Sales by Payment Mode (COD, Online, Cards).
- Time series:
  - `Monthly Sales by Year` area chart comparing 2019 vs 2020.
  - `Monthly Profit by Year` area chart with the same yearly comparison.
- Product and region views:
  - Sales by Category (Office Supplies, Technology, Furniture).
  - Sales by Sub‑Category (Phones, Chairs, Binders, etc.).
  - Sales by State displayed on a filled map for geographic performance tracking.
- Region filter buttons for Central, East, South, and West to quickly slice the entire page by region.

