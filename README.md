# Supply Chain Optimization for Uniquexcel

A data-driven end-to-end supply chain optimization project built with Microsoft Excel. This project analyzes operational data for **Uniquexcel**, a U.S.-based fashion and beauty brand, to address stockout risks, identify logistics bottlenecks, evaluate supplier reliability, and enhance overall profitability.

---

## Table of Contents
- [Executive Summary](#executive-summary)
- [Key Business Questions](#key-business-questions)
- [Data Analysis Framework](#data-analysis-framework)
- [Key Performance Indicators (KPIs)](#key-performance-indicators-kpis)
- [Insights & Recommendations](#insights--recommendations)
- [Dashboard Overview](#dashboard-overview)
- [Project Setup & Folder Structure](#project-setup--folder-structure)
- [How to Use This Repository](#how-to-use-this-repository)

---

## Executive Summary

Uniquexcel, a fast-growing fashion and beauty startup specializing in skincare and haircare, experienced operational challenges due to rapid nationwide expansion. Issues included frequent product stockouts, elevated shipping and manufacturing costs, defect-related returns, and delivery delays.

This project delivers an interactive Excel dashboard along with dynamic Pivot Tables, conditional formatting rules, and key calculated metrics to provide leadership with actionable recommendations for cost reduction and operational efficiency.

---

## Key Business Questions

1. **Stockout Risk:** Which SKUs are at risk of stockouts based on low availability vs. high order quantity?
2. **Bottlenecks:** Which suppliers or routes cause the most delivery delays or high shipping costs?
3. **Quality & Lead Time:** Are high defect rates linked to specific suppliers or manufacturing lead times?
4. **Product Profitability:** What is the net profitability per SKU after considering revenue, manufacturing, and shipping costs?
5. **Logistics Correlation:** How do transportation modes (Air, Road, Rail) affect overall shipping costs?

---

## Data Analysis Framework

The analysis follows the standard 6-phase data analysis framework:

1. **Ask:** Clarify stakeholder requirements, identify business bottlenecks, and define key performance criteria.
2. **Prepare:** Structure internal company datasets, verify fields (SKUs, inventory levels, order quantities, shipping carriers, and manufacturing times), and assess completeness.
3. **Process (Data Cleaning):**
   - Deduplicated data records (removed 19 duplicate rows).
   - Cleaned null/blank values and standardized categorical entries (`N/A` transformed to `Unknown`).
   - Imputed mode values where applicable for categorical variables.
   - Built custom calculated columns:
     - **Profit:** `Revenue - (Manufacturing Cost + Shipping Cost)`
     - **Stockout Risk Category:** Evaluated using multi-condition `IF` logic comparing `Order Quantity` against `Availability`.
4. **Analyze:** Utilized Excel Pivot Tables and calculated fields to aggregate lead times, defect rates, unit margins, and transport overheads.
5. **Share:** Visualized findings through customized pie charts, clustered column charts, combo charts, and interactive slicers.
6. **Act:** Formulated actionable strategies to improve supplier SLAs and re-route inventory pathways.

---

## Key Performance Indicators (KPIs)

| Metric | Value | Description |
| :--- | :--- | :--- |
| **Total Products (SKUs)** | 488 | Total unique product entries evaluated |
| **Avg. Shipping Cost** | $5.48 | Average shipping expenditure per item unit |
| **Avg. Manufacturing Lead Time** | 14.7 days | Mean duration required to complete product manufacturing |
| **Stockout High-Risk Rate** | ~46% | Proportion of SKUs where order demand exceeds current stock availability |

---

## Insights & Recommendations

### 1. Stockout Risk Management
- **Insight:** Roughly 46% of items are marked as high stockout risk due to order volume outpacing stored inventory.
- **Recommendation:** Implement automated inventory reordering triggers when stock drops below baseline safety levels, and prioritize restocking high-demand SKUs.

### 2. Supplier Performance & Defect Rates
- **Insight:** Supplier 1 exhibits the highest average product defect rate despite lower manufacturing lead times. Supplier 4 has the lowest defect rate but the longest lead times.
- **Recommendation:** Conduct quality assurance audits for Supplier 1 and adjust product allocation toward reliable suppliers to balance speed and quality.

### 3. Transportation & Route Efficiency
- **Insight:** **Route B** delivers the lowest shipping costs and shortest lead times. **Route A** incurs the highest shipping costs, while **Route C** leads to the longest delivery delays.
- **Recommendation:** Route default inventory shipments through **Route B** where possible. Re-evaluate contracts for Route A and C carriers.

### 4. Logistics Mode Cost Optimization
- **Insight:** Air transport is the most expensive logistics mode, while Road transport provides the lowest cost per unit.
- **Recommendation:** Reserve Air freight strictly for high-margin or urgent restocking orders, transitioning standard shipments to Road transport.

### 5. Product Profitability
- **Insight:** SKU 198 emerged as the single most profitable item in the product portfolio.
- **Recommendation:** Protect supply availability for SKU 198 and model marketing and replenishment strategies on top-performing items.

---

## Dashboard Overview

The interactive Excel dashboard incorporates:
- **KPI Summary Cards:** Displays total SKUs, average shipping costs, and lead times.
- **Interactive Slicers:** Allows dynamic filtering by **Location** and **Stockout Risk Status**.
- **Charts & Visualizations:**
  - 3D Pie Charts for Route Costs, Lead Times, and Transport Modes.
  - Combo Chart combining Bar and Line elements for Supplier Defect Rates vs. Lead Times.
  - Clustered Bar Charts showing Top 10 Profitable SKUs.
- **Navigation Links:** Embedded hyperlinked buttons for seamless tab navigation between the Dashboard, Pivot Tables, and Raw Data.

---

## Project Setup & Folder Structure

```text
├── data/
│   └── raw_supply_chain_data.xlsx      # Raw input dataset
├── spreadsheets/
│   └── supply_chain_optimization.xlsx  # Cleaned dataset, Pivot Tables, & Dashboard
├── docs/
│   └── Supply_Chain_Report.pdf         # Full analysis report & executive summary
└── README.md                           # Project documentation
