# SyntaxGirls — Business Overview Dashboard
### International Business Datathon 2025 | Universiti Utara Malaysia (UUM)

A Power BI dashboard and analysis project built for the International Business Datathon, examining three years (2023–2025) of sales, inventory, supplier, and employee data for a hardware retail business.

**Team: Syntax Girls** 

Siti Ain Athiqah Binti Sahrun · Hana Syakirah Binti Hassan Khairullah · Muna 'Ilyani Binti Mua'ad

**Course:** 

Bachelor of Computer Science with Honours, UUM

**Submission date:** 20 October 2025

🔗 ** Public Dashboard Link: https://app.powerbi.com/view?r=eyJrIjoiYTI0MzRiYzUtYWNjOC00ODRiLTgyMjktNDY0ZmJkN2ViYmE2IiwidCI6ImQ0OTRlMTEzLTUyOGUtNDBhYi05MGQ5LTE2MmRlMmZjYTNmMyIsImMiOjEwfQ%3D%3D) **

---

## Overview

The dashboard analyses transactional data across 8 relational tables (employee, customer, supplier, product, order, order_product, sale, sale_product) to surface insights on sales performance, inventory health, supplier risk, and employee/customer trends, then translates those insights into actionable business recommendations.

**Headline findings:**
- Total sales overall (2023–2025): **RM380.37K**, across **14.7K transactions**
- Sales are essentially flat year-on-year (no sustained growth) despite market demand
- Top revenue products (Power Drill, Ladder, Hammer) run a thin ~33% profit margin
- **61.46%** of total supply comes from a single supplier (Perlis Mega Supply) — a
  concentration risk
- Employee turnover sits at **41.18%**, with heavy reliance on a small pool of top sellers
- Only **3.33%** of customers are registered, limiting loyalty/retention initiatives

## Repository Contents

| File | Description |
|---|---|
| `international_business_datathon_case_study.xlsx` | Original raw dataset (8 sheets: employee, customer, supplier, product, order, order_product, sale, sale_product) |
| `SyntaxGirls_Dashboard.pbix` | Power BI dashboard file — data model, DAX measures, and visualisations |
| `SyntaxGirls_Business_Report.pdf` | Business report — executive summary, key findings, and recommendations |
| `SyntaxGirls_Technical_Report.pdf` | Technical report — data cleaning, Power Query transformations, data model, and DAX documentation |

## Methodology

1. **Data quality check** — Python (pandas, Jupyter Notebook) used to audit all 8
   sheets for missing values, duplicates, and invalid numeric types before import.
2. **Power Query transformation** — Missing values handled via derived columns
   rather than deletion (e.g. `employee_status` = Available/Resigned based on
   `date_left`; `customer_status` = Registered/Unregistered based on `customer_id`).
3. **Data modelling** — Star-schema-style relationships built across all tables in
   Power BI, cross-checked and corrected from the auto-detected model.
4. **DAX measures** — Custom measures for Revenue, Profit, Profit Margin %, Total
   Cost, Average Sales Made, Total Transactions, and more (see Technical Report §3.4
   for full formulas).
5. **Dashboard build** — Four linked report pages: Business Overview, Sales
   Analysis, Supplies/Products/Inventory, and Employee & Customer Insights.

## Dashboard Pages

- **Business Overview Dashboard** — total sales, stock on hand, orders processed,
  customers, payment method distribution, top products, top employees (filterable
  by year/month)
- **Sales Analysis** — profit, revenue, profit margin by product; market share by
  product; sales breakdown by employee (filterable by gender/race)
- **Supplies, Products & Inventory** — product profitability, supplier order
  volumes, low-stock alerts, stock vs. sales quantity
- **Employee & Customer Insights** — employee status/role distribution, sales
  trend by employee, customer registration and demographic breakdown

## Key Recommendations

- **Sales:** minimum-purchase promotions, bundling high/low sellers, push online
  payment methods (FPX, DuitNow)
- **Inventory:** diversify away from single-supplier dependency, monitor low-stock
  high-demand items, apply inventory turnover ratio tracking
- **Employees:** rebalance workforce toward sales roles, reward top performers,
  mentor underperforming staff, set realistic KPIs
- **Customers:** loyalty programmes, targeted promotions by demographic, first-party
  data collection via surveys

## Limitations

- Incomplete employee records (null `date_left` values may affect turnover rate accuracy)
- Minor sales/revenue discrepancy (~RM3,729.10), likely rounding or transaction timing
- Static dataset — no modelling of inflation, price changes, or market shifts
- Insights are purely quantitative; no qualitative customer feedback was available
