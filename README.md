# 📊 Sales Analytics & Dashboard Project

A end-to-end sales data pipeline — from raw CSV cleaning to interactive visualizations and a Power BI-style dashboard — built entirely with Python and vanilla HTML/JS.

---

## 📁 Project Structure

```
├── Sales_Dataset.csv               # Original raw dataset
├── Sales_Dataset_Cleaned.csv       # Cleaned & processed dataset
├── Sales_Dashboard.html            # Interactive Power BI-style dashboard
├── Sales_Visualizations.html       # Standalone visualization suite
└── README.md                       # This file
```

---

## 🧹 Data Cleaning (`Sales_Dataset_Cleaned.csv`)

**Source:** `Sales_Dataset.csv` — 1,194 rows × 12 columns

### Issues Found & Fixed

| Issue | Action | Rows Affected |
|---|---|---|
| Customer names with honorific titles (Mr., Ms., Mrs., Dr.) and suffixes (PhD, MD, DDS, Jr.) | Stripped using regex | 52 rows |
| `Order Date` stored as plain text string | Converted to proper `datetime` format | All rows |
| `Year-Month` column fully redundant (derivable from Order Date) | Dropped | — |

### Verified Clean
- ✅ No missing values in any column
- ✅ No duplicate rows
- ✅ No negative or zero values in Amount, Profit, or Quantity
- ✅ All Year-Month values matched their Order Date
- ✅ City/State pairings consistent across dataset

### Final Schema

| Column | Type | Description |
|---|---|---|
| `Order ID` | string | Unique order identifier |
| `Amount` | int | Order revenue in USD |
| `Profit` | int | Order profit in USD |
| `Quantity` | int | Units ordered |
| `Category` | string | Electronics / Furniture / Office Supplies |
| `Sub-Category` | string | 12 product sub-categories |
| `PaymentMode` | string | UPI / Credit Card / Debit Card / COD / EMI |
| `Order Date` | datetime | Date of order (parsed from string) |
| `CustomerName` | string | Customer full name (cleaned) |
| `State` | string | US state |
| `City` | string | City of delivery |

---

## 📈 Analysis Summary

### Dataset Overview
- **Period:** March 2020 – March 2025
- **Total Revenue:** $6.18M
- **Total Profit:** $1.61M (26% margin)
- **Total Orders:** 1,194
- **Regions:** 6 US states
- **Categories:** 3 (Electronics, Furniture, Office Supplies)
- **Sub-Categories:** 12

### Top Selling Products (by Revenue)

| Rank | Sub-Category | Revenue | Profit |
|---|---|---|---|
| 1 | Markers | $627,875 | $174,749 |
| 2 | Tables | $625,177 | $156,796 |
| 3 | Sofas | $568,367 | $142,854 |
| 4 | Printers | $566,359 | $146,259 |
| 5 | Electronic Games | $565,092 | $148,454 |

### Monthly Revenue
- **Peak month:** May 2024 — $140,745
- **Lowest month:** Jan 2024 — $47,645
- Revenue shows a clear seasonal cycle with spikes in Mar–Jun and Oct–Dec, and dips in Jan and Aug.

### Region Performance

| State | Revenue | Profit | Orders |
|---|---|---|---|
| New York | $1,130,048 | $308,506 | 226 |
| Florida | $1,091,174 | $308,706 | 200 |
| California | $1,086,436 | $278,814 | 218 |
| Texas | $1,011,475 | $257,780 | 189 |
| Illinois | $978,738 | $240,372 | 181 |
| Ohio | $884,768 | $216,519 | 180 |

> Florida edges New York on total profit ($308.7K vs $308.5K) despite lower revenue — slightly better margin efficiency.

---

## 🖥️ Deliverables

### 1. `Sales_Dashboard.html` — Power BI-Style Dashboard
An interactive dark-themed dashboard styled to match Microsoft Power BI.

**Features:**
- 4 KPI cards (Revenue, Profit, Orders, Top Category)
- Monthly Revenue & Profit trend line chart
- Revenue by Category donut chart
- Revenue by Sub-Category horizontal bar chart
- Region-wise performance bar chart
- Payment Mode split donut chart
- Quarterly Revenue bar chart
- **Live slicers** — filter all charts by Category and Year

**To use in actual Power BI:**
Open Power BI Desktop → *Get Data → Text/CSV* → import `Sales_Dataset_Cleaned.csv`. The date column is pre-parsed and all fields are clean for native drag-and-drop visuals.

---

### 2. `Sales_Visualizations.html` — Standalone Visualization Suite
A premium dark editorial-style visualization page with animated entry effects.

**Includes:**
- **KPI Cards** — Animated counting numbers (Revenue, Profit, Orders, Customers)
- **Revenue Trend** — 60-month dual area line chart with gradient fills and crosshair tooltip
- **Product Performance** — Grouped horizontal bar chart (Revenue vs Profit per sub-category)
- **Region Sales Map** — Stylized US map with bubble overlays sized by revenue volume; hover for state details
- **Category & Payment donuts** — Supporting breakdown panels

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python / pandas | Data cleaning & analysis |
| Chart.js 4.4.1 | Interactive charts |
| Vanilla HTML/CSS/JS | Dashboard & visualization UI |
| Google Fonts (DM Mono, DM Sans, Playfair Display) | Typography |

---

## 🚀 How to Run

1. Open either HTML file directly in any modern browser — no server or dependencies needed.
2. For the dashboard, use the **Category** and **Year** slicer buttons at the top to filter all charts interactively.
3. On the visualization page, hover map bubbles to see state-level revenue tooltips.

---

*Generated from Sales_Dataset.csv · 1,194 orders · March 2020 – March 2025*
