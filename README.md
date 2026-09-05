# Construction Portfolio Financial Tracker — Power BI Dashboard

> **Note:** All data in this project is synthetic and created for portfolio demonstration purposes only.

## 📌 Ask

**Business Problem:** A construction company manages 5 concurrent projects across 4 provinces (BC, AB, ON, NS, NB) with a total portfolio value of $9.3M CAD. The finance team lacks a centralized tool to track:

- Which projects are exceeding their budgets?
- How much budget remains after committed costs?
- Which projects are at risk of cost overrun?

**Questions to answer:**

1. What is the budget utilization rate across the portfolio?
2. Which projects are over budget and by how much?
3. How much remaining budget is available (net of committed costs)?
4. What is the completion status of each project?

---

## 🗂️ Prepare

**Data Sources:** Excel flat tables (structured for Power BI import)

| Sheet | Description |
|---|---|
| **Projects** | Project-level data: contracted budget, actual costs, committed costs, budget used %, variance, status, and physical completion % |
| **Monthly_Costs** | Monthly budget vs actual breakdown per project, for trend analysis |

**Data Quality Check:**

- ✅ No missing values in key columns (Budget, Actual, Status, Completion)
- ✅ Consistent data types (Currency, Percentage, Text)
- ✅ Unique project identifiers (Project_Name)
- ✅ Clear column headers for Power BI import

---

## 🛠️ Process

**Data Cleaning & Preparation (Excel):**

- Structured both tables as flat, Power BI-ready sources (no merged cells)
- Verified all currency values in CAD
- Row-level **Budget_Used_Pct** and **Variance_Amount** pre-calculated per project in the Projects table
- Physical **Completion_Pct** is reported per project by the project manager — it reflects work actually done on site, not money spent, so it's entered as an input rather than derived from cost data

**Data Modeling (Power BI):**

- Connected both Excel tables as data sources
- Created a relationship between the Projects table and the Monthly_Costs table (via Project_Name)
- Added calculated measures at the portfolio level

**DAX Measures Created:**

| Measure | Purpose |
|---|---|
| **Budget Utilization %** | `SUM(Projects[Actual_Costs]) / SUM(Projects[Contracted_Budget])` — portfolio-wide cost burn rate (the Excel column Budget_Used_Pct gives this per project; the measure aggregates it across the whole portfolio) |
| **Remaining Budget** | True remaining budget, net of committed costs |
| **Cost Overrun Flag** | Flags projects where Actual + Committed Costs exceed Contracted Budget |

---

## 🔍 Analyze

**Key Metrics Calculated:**

| Metric | Value |
|---|---|
| Total Portfolio Value | $9.3M CAD |
| Total Costs to Date | ~$7.4M CAD |
| Budget Utilization | ~80% of contracted budget spent to date |
| Average Physical Completion | ~74% |
| Variance Range | -$23,600 to +$536,000 |
| Active Projects | 4 (1 completed) |

**Key Findings:**

- **Budget Utilization vs. Completion:** the portfolio has spent ~80% of its contracted budget but is only ~74% physically complete on average — a gap worth monitoring, since it means cost is running slightly ahead of progress overall.
- **Cost Overruns:** 1 project over budget (Lakeview Retail Plaza Reno), already completed.
- **Risk Flags:** projects with variance > $200K require management attention.
- **Best Cost-to-Progress Match:** Harbour District Apartments and Riverside Office Tower Fitup show budget usage closely tracking physical completion, despite Harbour carrying the largest dollar variance in the portfolio.
- **Monthly trend:** Lakeview Retail Plaza Reno is the only project running over its monthly budget in every month tracked (Jan–Jun 2025), consistent with its overall over-budget completion.

**Variance Analysis by Project:**

| Project | Status | Variance | Risk Level |
|---|---|---|---|
| Harbour District Apartments | In Progress | +$536,000 | 🔴 High Risk |
| Eastside Medical Clinic Fitup | In Progress | +$232,000 | 🟡 Medium Risk |
| Northgate Community Centre | In Progress | +$221,500 | 🟡 Medium Risk |
| Riverside Office Tower Fitup | In Progress | +$16,800 | 🟢 Low Risk |
| Lakeview Retail Plaza Reno | Completed | -$23,600 | 🟢 Completed (Over budget) |

---

## 📤 Share

**Dashboard Created:**

An interactive Power BI dashboard with:

- **Clustered Column Chart:** Budget vs Actual by project
- **Donut Chart:** Completion distribution across projects
- **Table:** Project status, variance, and completion %
- **KPI Cards:** Portfolio-level metrics (Total Value, Costs, Remaining Budget, Avg Completion, Budget Utilization %)

**Dashboard Preview:**

[![Dashboard Screenshot](https://github.com/valeriiaevtushenko-arch/construction-portfolio-powerbi/raw/main/!Atlantic_Build_Dashboard.png)](/valeriiaevtushenko-arch/construction-portfolio-powerbi/blob/main/!Atlantic_Build_Dashboard.png)

**Live Dashboard Features:**

- Interactive filters by province, status, and completion %
- Drill-through capability to monthly cost trends
- Color-coded risk flags (red = over budget, green = on track)

---

## ✅ Act

**Recommendations:**

1. **Immediate:** Review Harbour District Apartments (largest dollar variance).
2. **Action Plan:** Investigate cost drivers for Eastside Medical Clinic Fitup.
3. **Process Improvement:** Automate data refresh from the accounting system.
4. **Dashboard Enhancement:** Add early-warning alerts when monthly burn rate consistently exceeds monthly budget.

**What This Project Demonstrates:**

| Skill | Evidence |
|---|---|
| **Power BI** | Built an interactive dashboard with 4 visual types |
| **DAX** | Created 3 custom measures (Utilization, Remaining Budget, Overrun Flag) |
| **Financial Analysis** | Budget vs actual, variance analysis, committed cost tracking |
| **Data Modeling** | Connected two Excel tables, built a relationship, enabled drill-through |
| **Construction Industry** | Project-based cost management, multi-province portfolio |
| **Executive Reporting** | KPI cards for leadership visibility |

**Next Steps:**

- Connect to a live data source (SAP / QuickBooks)
- Extend monthly trend data beyond June 2025
- Share via Power BI Service for stakeholder access

---

**📊 "Turn data into decisions — one dashboard at a time."**

**Author:** Valeriia Evtushenko
**Role:** Financial Analyst | FP&A | Budget & Cost Analyst
**Date:** September 2026
**Purpose:** Portfolio demonstration — financial analytics, data visualization, DAX

**GitHub:** [https://github.com/valeriiaevtushenko-arch/construction-portfolio-powerbi](https://github.com/valeriiaevtushenko-arch/construction-portfolio-powerbi)

---

## 💡 Key Takeaway

*"This project shows I can take raw data, clean it, model it, analyze it, and present it in a format that helps leadership make informed decisions — the full Google Data Analytics cycle in one real-world business case."*
---

## 💡 Key Takeaway

*"This project shows I can take raw data, clean it, model it, analyze it, and present it in a format that helps leadership make informed decisions — the full Google Data Analytics cycle in one real-world business case."*
