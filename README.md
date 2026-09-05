# Construction Portfolio Financial Tracker — Power BI Dashboard

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
|-------|-------------|
| **Projects** | Project-level data: budget, actual costs, committed costs, status, completion % |
| **Monthly_Costs** | Monthly budget vs actual breakdown for trend analysis |

**Data Quality Check:**
- ✅ No missing values in key columns (Budget, Actual, Status, Completion)
- ✅ Consistent data types (Currency, Percentage, Text)
- ✅ Unique project identifiers (Project_Name)
- ✅ Clear column headers for Power BI import

---

## 🛠️ Process

**Data Cleaning & Preparation (Excel):**
- Removed merged cells — converted to flat table format
- Verified all currency values in CAD
- Added helper columns: Budget Used %, Variance Amount, Variance %
- Structured data for Power BI import

**Data Modeling (Power BI):**
- Connected Excel tables as data sources
- Created relationship between Project table and Monthly_Costs table
- Added calculated columns where needed

**DAX Measures Created:**

| Measure | Purpose |
|---------|---------|
| **Budget Utilization %** | Measures cost burn rate across the portfolio |
| **Remaining Budget** | True remaining budget (net of committed costs) |
| **Cost Overrun Flag** | Flags projects exceeding their budget |

---

## 🔍 Analyze

**Key Metrics Calculated:**

| Metric | Value |
|--------|-------|
| Total Portfolio Value | $9.3M CAD |
| Total Costs to Date | ~$6.9M CAD |
| Budget Utilization | ~73% across the portfolio |
| Variance Range | -$23,600 to +$536,000 |
| Active Projects | 4 (1 completed) |

**Key Findings:**
- **Budget Utilization:** 73% average burn rate — healthy overall
- **Cost Overruns:** 1 project over budget (Lakeview Retail Plaza)
- **Risk Flags:** Projects with variance > $200K require management attention
- **Completed Project:** 1 project completed, on budget

**Variance Analysis by Project:**

| Project | Status | Variance | Risk Level |
|---------|--------|----------|------------|
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
- **KPI Cards:** Portfolio-level metrics (Total Value, Costs, Remaining Budget, Avg Completion)

**Dashboard Preview:**

![Dashboard Screenshot](!Atlantic_Build_Dashboard.png)

**Live Dashboard Features:**
- Interactive filters by province, status, and completion %
- Drill-through capability to monthly cost trends
- Color-coded risk flags (red = over budget, green = on track)

---

## ✅ Act

**Recommendations:**

1. **Immediate:** Review Harbour District Apartments (largest variance)
2. **Action Plan:** Investigate cost drivers for Eastside Medical Clinic Fitup
3. **Process Improvement:** Automate data refresh from accounting system
4. **Dashboard Enhancement:** Add monthly trend analysis for early warning signals

**What This Project Demonstrates:**

| Skill | Evidence |
|-------|----------|
| **Power BI** | Built interactive dashboard with 4 visual types |
| **DAX** | Created 3 custom measures (Utilization, Remaining, Overrun Flag) |
| **Financial Analysis** | Budget vs actual, variance analysis, committed cost tracking |
| **Data Modeling** | Connected Excel tables, built relationships |
| **Construction Industry** | Project-based cost management, multi-province portfolio |
| **Executive Reporting** | KPI cards for leadership visibility |

**Next Steps:**
- Connect to live data source (SAP / QuickBooks)
- Add monthly trend analysis
- Share via Power BI Service for stakeholder access

---

**📊 "Turn data into decisions — one dashboard at a time."**

**Author:** Valeriia Evtushenko  
**Role:** Financial Analyst | FP&A | Budget & Cost Analyst  
**Date:** September 2026  
**Purpose:** Portfolio demonstration — financial analytics, data visualization, DAX

**GitHub:** [https://github.com/ваш_аккаунт/construction-portfolio-powerbi](https://github.com/ваш_аккаунт/construction-portfolio-powerbi)

---

## 💡 Key Takeaway

*"This project shows I can take raw data, clean it, model it, analyze it, and present it in a format that helps leadership make informed decisions — the full Google Data Analytics cycle in one real-world business case."*

