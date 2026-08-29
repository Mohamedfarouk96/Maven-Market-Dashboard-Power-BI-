# 🍃 Maven Market Sales Dashboard (Power BI)

A single-page Power BI executive dashboard analyzing sales, profit, and returns for Maven Market — a multi-country grocery retail dataset (USA, Canada, Mexico).

![Maven Market Dashboard Preview](./screenshot-maven-dashboard.png)

## 📊 Overview

This report gives a quick, interactive snapshot of retail performance across brands, stores, and time:

- How are current-month orders, profit, and returns trending vs. the previous month?
- Which product brands generate the most transactions, profit, and have the best/worst return rates?
- How do orders break down by store state and country?
- Is revenue tracking on or off target?
- How is weekly revenue trending over the two-year period?

## 🗂️ Data Model

Built on a **star schema** with the following tables:

- `Calendar` — date table for time intelligence (with a `Start of Month` / `Start of Week` hierarchy)
- `Products` — product/brand lookup (`product_brand`)
- `Stores` — store lookup (`store_city`, `store_state`, `store_country`)
- `_Meaures` — a dedicated disconnected table holding all DAX measures

## 🧮 Key DAX Measures

| Category | Examples |
|---|---|
| Core KPIs | Total Revenue (After Discount), Total profit, Total Transactions, Total Returns, Return rate, Profit Margin |
| Time Intelligence | Last Month Returns, Last month Transaction, last month profit |
| Targets | Monthly revenue target |

## 🛠️ Steps I Used to Build This Project

1. **Imported the Maven Market dataset** (Calendar, Products, Stores, and Transactions tables) into Power BI Desktop.
2. **Cleaned and shaped the data in Power Query** — set correct data types, checked for nulls/duplicates, and confirmed key columns (product brand, store location, dates) were consistent for joining.
3. **Built a star-schema data model**, relating the transactions fact data to `Calendar`, `Products`, and `Stores`, with `Calendar` marked as the official date table for time-intelligence functions.
4. **Created a dedicated measures table** (`_Meaures`) to keep all DAX measures organized separately from the data tables.
5. **Wrote DAX measures** for the core KPIs (Total Revenue After Discount, Total Profit, Total Transactions, Total Returns, Return Rate, Profit Margin), previous-month comparisons, and the monthly revenue target.
6. **Designed a single-page executive dashboard** with:
   - A **date range slider** to filter the whole report by period.
   - **KPI cards** for current-month orders, profit, and returns (each with a prev-month delta indicator).
   - A **sortable matrix/table** of brands showing Total Transactions, Total Profit, Profit Margin, and Return Rate, with data bars and conditional color formatting.
   - A **column chart** of orders by store state and country.
   - A **treemap slicer** for drilling into store country → state.
   - A **line chart** of weekly revenue trending over the full date range.
   - A **gauge chart** comparing Revenue vs. Target.
7. **Applied conditional formatting** (data bars on the transactions column, red/green shading on return rate) to make the brand comparison table scannable at a glance.
8. **Styled the report** with the Maven Market logo, a dark header bar, and a clean teal/white color theme.
9. **Tested cross-filtering and drill-down** (treemap drill-down by country/state, date slider, brand table sorting) before finalizing.

## 📄 Dashboard Highlights

| Visual | Purpose |
|---|---|
| KPI cards | Current-month Orders, Profit, and Return vs. previous month |
| Brand table | Total Transactions, Total Profit, Profit Margin, Return Rate per brand |
| Orders by store state/country | Regional performance comparison |
| Store treemap | Drill down orders by country → state |
| Weekly Revenue Trending | Revenue trend line across the full period |
| Revenue vs Target | Gauge showing progress against the monthly revenue target |

## 🧰 Tools & Skills Used

- **Power BI Desktop** — data modeling, DAX, report design
- **Power Query** — data cleaning and transformation
- **DAX** — measures, time intelligence
- **Conditional formatting** — data bars, color scales

## 🚀 How to Use

1. Download `Maven.pbix`.
2. Open it in **Power BI Desktop** (free download from Microsoft).
3. Use the date slider, treemap, and table sorting to explore performance by period, brand, and location.

## 📁 Files in This Repo

```
├── Maven.pbix                       # Full Power BI report
├── screenshot-maven-dashboard.png   # Preview image of the dashboard
└── README.md                        # This file
```

## 👤 Author

**Mohamed Farouk**
Data Quality Reviewer & Analyst | Building a portfolio in Power BI, Excel, and data analytics
[GitHub: Mohamedfarouk96](https://github.com/Mohamedfarouk96)

---

> ⚠️ Note: The build steps above summarize the general workflow based on the report's structure (tables, measures, and visuals). If any detail doesn't match exactly how you built it, feel free to tweak the wording before publishing.
