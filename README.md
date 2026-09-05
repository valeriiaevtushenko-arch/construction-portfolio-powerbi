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
- Physical **Completion_Pct** is reported per project by the project manager — it reflects work actually done on site, not money spent, so it's entered as an input rather than derived
---

## 💡 Key Takeaway

*"This project shows I can take raw data, clean it, model it, analyze it, and present it in a format that helps leadership make informed decisions — the full Google Data Analytics cycle in one real-world business case."*
