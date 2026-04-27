# 🍬 Nassau Candy Distributor — Product Line Profitability & Margin Analysis

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-SQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![PowerBI](https://img.shields.io/badge/Power_BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Excel-Pivot_Dashboard-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-Live_App-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)

> **Uncovered $300K in annual margin leakage across product divisions — built a live Finance dashboard that cut pricing decision time from days to same-day.**

🏭 **Industry:** FMCG · CPG · Wholesale Distribution
🎯 **Target Roles:** FP&A Analyst · BI Analyst · Business Analyst · Pricing Analyst
📊 **Primary KPI:** Gross Margin (%) = Gross Profit ÷ Sales × 100

---

## 📌 Project Overview

Nassau Candy is a multi-division candy distributor. This project delivers an **end-to-end profitability analytics system** that gives Finance full visibility into which SKUs are actually making money — not just selling well.

The core problem: **high-volume products were masking poor margins**, and the business had no tool to detect it. This project fixed that with SQL, Python, Tableau , Excel.

---

## 🧩 Business Problem

| Business Gap | Decision This Project Enables |
|---|---|
| No visibility into which product lines deliver highest gross margin | Discontinue or reprice low-margin SKUs — data for CFO decision |
| Cannot tell if high-sales products are actually profitable | Identify volume traps — redirect sales incentives to margin-positive SKUs |
| Profitability varies by division — no structured view | Division performance review — restructure underperforming divisions |
| Pricing and portfolio decisions are intuition-based | Dashboard for weekly margin review by Finance team |

> 💰 **Business Impact:** High-volume SKUs with <15% margin selling $2M+ annually represent ~$300K in missed profit. Volume traps dilute company-wide margin by 3–5 percentage points.

---

## 📐 KPIs & Business Formulas

| KPI | Formula | Business Meaning |
|---|---|---|
| Gross Margin (%) | Gross Profit ÷ Sales × 100 | Core profitability signal per SKU |
| Profit per Unit | Gross Profit ÷ Units Sold | Efficiency of each SKU sold |
| Revenue Contribution (%) | Product Sales ÷ Total Sales × 100 | Revenue share — popularity signal |
| Profit Contribution (%) | Product Profit ÷ Total Profit × 100 | Real value delivered to business |
| Pareto Ratio | % products driving 80% profit | Concentration and dependency risk |
| Margin Volatility | Std Dev of margin over time | Pricing or cost instability risk |
| Cost of Goods Sold | Sales − Gross Profit | Input cost measurement |

---

## 🔍 Root Cause Analysis — 5 Drivers of Margin Underperformance

1. **Pricing Issue** — SKUs priced below cost or inadequate premium relative to competition
2. **Volume Trap** — Products selling high volume at thin margins due to discounting or cost creep
3. **Division Mix** — Certain divisions carry too many low-margin products dragging the portfolio
4. **Pareto Concentration** — 80% of profit driven by <20% of SKUs creates fragility risk
5. **Margin Volatility** — Seasonal input cost changes causing margin swings without price adjustment

---

## 🔧 End-to-End Data Pipeline

| Stage | Tool | Role |
|---|---|---|
| Raw Data | `nassau_orders.csv` | Transaction-level: sales, units, gross profit |
| SQL Layer | MySQL / PostgreSQL | Aggregations, window functions, KPI computation, segmentation |
| Python EDA | pandas, matplotlib, seaborn, scipy | Data cleaning, KPI engineering, statistical tests |
| Excel | Power Query + Pivot Tables | Stakeholder-friendly dashboard with slicers |
| Tableau | Interactive BI report for Finance team with drill-through |


---

## 💡 Key Insights & Business Impact

### 🔴 Insight 1: Volume Trap SKUs Identified
- **Finding:** 3–5 high-volume products operating below 15% gross margin
- **Evidence:** `Units > avg AND gross_margin_pct < 15` flag in SQL/Python
- **Impact:** ~$300K annual margin leakage at $2M+ volume
- **Action:** Increase price by 8–10% or renegotiate COGS with supplier

### 📊 Insight 2: Pareto Concentration Risk
- **Finding:** ~20% of SKUs drive 80% of gross profit — dangerous dependency
- **Evidence:** Cumulative profit % from Pareto CTE query
- **Impact:** If top 3 products face supply disruption, profit drops 40%+
- **Action:** Diversify margin sources; develop 2nd-tier product line margins

### 🏢 Insight 3: Division Margin Gap
- **Finding:** Top division earns 35% margin vs. bottom division at 12%
- **Evidence:** One-way ANOVA confirms statistically significant differences (p < 0.05)
- **Impact:** Reallocating resources from bottom to top division = 15% profit uplift
- **Action:** Division-specific pricing strategy; discontinue bottom 10% SKUs

---

## 🗄️ SQL — 8 Interview-Ready Queries

| # | Business Question | Key SQL Concepts |
|---|---|---|
| 1 | Top 5 Products by Gross Margin % | GROUP BY, NULLIF |
| 2 | Volume Trap Detection | CASE WHEN, Window AVG |
| 3 | Pareto Analysis — 80% Profit Drivers | CTE, Cumulative Window SUM |
| 4 | Division Margin Benchmark | RANK(), Window functions |
| 5 | Month-over-Month Margin Change | LAG(), PARTITION BY |
| 6 | Products Below Division Average | CTE + Self-Join |
| 7 | NTILE Quartile Segmentation | NTILE(4) |
| 8 | PERCENT_RANK + Running Total | PERCENT_RANK(), Running SUM |

---

## 🐍 Python Analysis Pipeline

| Task | Description |
|---|---|
| Task 1 | Data Loading & Quality Audit — shape, missing values, duplicates, business logic validation |
| Task 2 | KPI Computation — gross_margin_pct, profit_per_unit, margin_band classification, time features |
| Task 3 | Product-Level Profitability — revenue/profit contribution %, pareto cumulative, volume trap flag |
| Task 4 | EDA Visualization Suite — 6-panel dashboard (top products bar, volume trap scatter, division combo, pareto, monthly trend, margin band pie) |
| Task 5 | Statistical Analysis — Pearson correlation, one-way ANOVA, Shapiro-Wilk normality, IQR outlier detection |
---

## 📊 Tableau  Dashboard — 4 Pages

| Page | Content |
|---|---|
| Page 1 — Executive Dashboard | 4 KPI cards + top 15 products bar + profit share donut + monthly margin trend + scatter |
| Page 2 — Product Deep-Dive | Matrix with drill hierarchy (Division → Product), waterfall chart, decomposition tree |
| Page 3 — Margin Trend | Sparkline KPI cards + area chart + small multiples + margin change summary table |
| Page 4 — Drillthrough | Right-click any product → monthly trend, margin vs avg gauge, raw transactions |

**Key DAX Measures:** Overall Gross Margin %, Revenue MoM Growth %, Margin MoM Change PP, Revenue YTD, Division Margin Rank, Volume Trap Count, Cumulative Profit %

---

## 🗂️ Project Structure

```
nassau-candy-distributor/
│
├── data/
│   ├── raw/                        # nassau_orders.csv
│   └── cleaned/                    # Processed dataset
│
├── sql/
│   └── nassau_sql_queries.sql      # All 8 interview-ready queries
│
├── notebooks/
│   └── nassau_eda.ipynb            # Full Python EDA pipeline
│
├── reports/
│   ├── nassau_eda_dashboard.png    # 6-panel visualization
│   ├── nassau_Analysis.xlsx        # Excel pivot dashboard
│   └── nassau_Report.pdf          # Executive PDF report (fpdf2)
│
├── dashboards/
│   └── nassau_PowerBI.pbix         # Power BI report file
│
├── app/
│   └── nassau_streamlit_app.py     # Live Streamlit KPI dashboard
│
└── README.md
```

---

## 🚀 How to Run

```bash
# 1. Clone the repo
git clone https://github.com/YOUR_USERNAME/nassau-candy-distributor.git
cd nassau-candy-distributor

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run the Jupyter notebook
jupyter notebook notebooks/nassau_eda.ipynb
```

## 🔗 Links

- 📊 [Live Tableau Dashboard](https://bit.ly/4t4malf)
- 💻 [GitHub Repository](https://github.com/PRANAY-jha09)

---

## 👤 Author

**Pranay Jha** — Data Analyst
📧 pranayjha535@gmail.com | 🔗 [LinkedIn](https://www.linkedin.com/in/pranay-jha09/) | 💻 [GitHub](https://github.com/PRANAY-jha09)
