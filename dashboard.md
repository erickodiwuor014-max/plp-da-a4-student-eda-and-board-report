# Duka Electronics H1 2026 Dashboard

**Public Looker Studio link:** https://datastudio.google.com/reporting/5341e0c1-10ff-4fdc-8083-0c14cf2015b0

Anyone with the link can view the dashboard. The data is synthetic course data, so public sharing is safe.

## Screenshots

![Dashboard overview: scorecards, monthly trend and breakdowns](screenshots/dashboard_overview.png)

![Dashboard with the channel filter applied](screenshots/dashboard_filtered.png)

## What the dashboard shows

| Element | What it shows |
|---|---|
| Scorecard: Total revenue (KES) | Sum of revenue: KES 71,792,500 |
| Scorecard: Orders | Count distinct of `order_id`: 1,000 |
| Scorecard: Average order value (KES) | Calculated field `SUM(revenue) / COUNT_DISTINCT(order_id)`: about KES 71,793 |
| Trend | Revenue by month (order date, month granularity), January to June 2026 |
| Breakdown | Revenue by branch (sorted bar chart) |
| Breakdown | Revenue by product (sorted bar chart) |
| Controls | Date-range control and a drop-down filter for channel; every chart responds to both |

## How it was built

1. `board_report.ipynb` exports `duka_dashboard_data.csv` (one row per order, ISO dates).
2. The CSV was imported into Google Sheets and connected to Looker Studio as the data source.
3. Field types were checked: `order_date` is a Date, `revenue` is a Number.
4. The PLP colours are used with purpose: #8E0000 for the highlight and #0BA184 for the accent.

Data source: Duka Electronics sales records, 1 January to 29 June 2026 (1,000 orders).
