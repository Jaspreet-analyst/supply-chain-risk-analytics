# 📦 Case Study: Supply Chain Risk & Cost Analytics

**Author:** Jaspreet Singh | Ocean Import Agent | Supply Chain Analyst — Greater Toronto Area
**Tools:** MySQL · Tableau Public · GitHub
**Dataset:** 5 relational tables | 7,643 rows | 2022–2024
**Live Dashboard:** [View on Tableau Public](https://public.tableau.com/app/profile/jaspreet.singh5400/viz/SupplyChainRiskCostAnalytics/SupplyChainRiskCostAnalytics20222024)
**GitHub Repo:** [supply-chain-risk-analytics](https://github.com/Jaspreet-analyst/supply-chain-risk-analytics)

---

## 🧩 The Problem

Most supply chain teams track delays and costs in silos. The operations team monitors shipment delays. The finance team tracks freight spend. The warehouse team manages inventory. Nobody connects the dots.

The result? A supplier gets flagged as unreliable — but nobody knows it's also causing D&D charges to spike and inventory to run critically low at the same time.

This project was built to answer one core question:

> **What is the true financial cost of supply chain risk — from the moment a supplier fails to the moment a stockout hits the business?**

---

## 🎯 Objective

Build a multi-table relational analytics model that connects supplier reliability, shipment delays, container D&D charges, inventory levels and total landed costs — and quantify the financial exposure at every stage.

---

## 🗄️ The Dataset

Five interconnected tables were designed to mirror a real supply chain operation:

| Table | Rows | Purpose |
|---|---|---|
| `suppliers` | 20 | Supplier reliability scores, risk ratings, lead times |
| `shipments` | 1,000 | Carrier performance, delay days, delay reasons |
| `containers` | 5,573 | Free days, port dwell time, D&D charges per container |
| `inventory` | 50 | SKU stock levels, reorder points, stockout costs |
| `costs` | 1,000 | Full landed cost breakdown per shipment |

**Total: 7,643 rows across 5 tables**

The tables are connected through **Supplier ID** and **Shipment ID** keys — enabling multi-table JOINs that reflect how data actually lives in enterprise systems like SAP, Oracle and CargoWise.

---

## 🔍 Methodology

### Step 1 — Relational Database Design
Designed a 5-table schema in MySQL with primary and foreign key relationships. This mirrors how supply chain data is structured in real ERP systems.

### Step 2 — SQL Analysis (13 Queries across 3 levels)

**Level 1 — Multi-Table JOINs**
Connected suppliers, shipments and costs to get a full picture of each shipment's financial and operational profile. Identified which suppliers drive the most delays and D&D charges using 3-table JOINs with GROUP BY aggregations.

**Level 2 — CTEs and Subqueries**
Used nested CTEs to identify the intersection of high risk suppliers and critical inventory — the most dangerous combination in any supply chain. Used correlated subqueries to find carriers performing worse than the overall average.

**Level 3 — Window Functions**
Applied RANK() OVER to rank carriers by D&D charges and calculate each carrier's percentage contribution to total D&D spend. Used PARTITION BY to analyze D&D breakdown by destination port. Built a stockout exposure score by multiplying stockout cost per day by supplier lead time — giving a single risk number per SKU.

### Step 3 — Tableau Dashboard
Built a 6-chart interactive dashboard across three analytical themes:
- **Cost visibility** — monthly landed cost trend, cost by carrier
- **D&D risk** — D&D charges by carrier
- **Supplier and inventory risk** — supplier risk ratings, stock status, stockout exposure

---

## 📊 Key Findings

### Finding 1 — D&D Charges Are a Hidden Cost Driver
D&D charges represent a significant and often overlooked portion of total landed cost. Carriers with the highest shipment volumes are not always the highest D&D generators — meaning volume and reliability are two separate dimensions that need to be tracked independently.

### Finding 2 — High Risk Suppliers Overlap with Critical Inventory
The most dangerous finding in this analysis — several suppliers rated High risk also supply SKUs currently in Critical or Low stock status. This means a single supplier disruption could simultaneously trigger D&D charges on delayed containers AND stockouts on critical parts.

### Finding 3 — Stockout Exposure is Concentrated in a Few SKUs
The top 10 SKUs by stockout exposure account for a disproportionate share of total financial risk. These SKUs share a common profile — high daily demand, long supplier lead times, and current stock below safety stock levels.

### Finding 4 — Monthly Cost Trend Shows Seasonal Spikes
Landed costs spike in mid-year months, likely driven by peak season surcharges and port congestion. This pattern suggests an opportunity to pull forward purchase orders to Q1 when rates and congestion are lower.

### Finding 5 — Carrier Performance Varies Significantly on D&D
Some carriers consistently generate higher D&D charges regardless of port — suggesting the issue is carrier-side (slow documentation, late pickup notifications) rather than port-side congestion.

---

## 💡 Business Recommendations

| Recommendation | Financial Impact | Based On |
|---|---|---|
| Dual-source top 5 Critical SKUs from High Risk suppliers | Eliminates stockout exposure on highest risk items | Finding 2 |
| Negotiate extended free days with high D&D carriers | Direct reduction in D&D spend | Finding 5 |
| Pull forward Q3 orders to Q1 for high-spend lanes | Avoids peak season surcharges | Finding 4 |
| Set automated reorder alerts for SKUs below safety stock | Prevents stockouts before they happen | Finding 3 |
| Review SLAs with carriers above average D&D rates | Accountability and cost recovery | Finding 1 |

---

## 🛠️ Skills Demonstrated

| Skill | Evidence |
|---|---|
| Relational Database Design | 5-table schema with primary and foreign keys |
| SQL — Multi-Table JOINs | 2 and 3 table JOINs across all 5 tables |
| SQL — CTEs | Single and nested CTEs for risk analysis |
| SQL — Window Functions | RANK(), PARTITION BY, running totals, exposure scoring |
| Data Visualization | 6-chart Tableau dashboard with cross-table data |
| Supply Chain Domain | D&D mechanics, safety stock, landed cost, supplier risk |
| Business Storytelling | Findings translated into actionable recommendations |

---

## 🔗 Project Links

- 📊 **Live Dashboard:** [Tableau Public](https://public.tableau.com/app/profile/jaspreet.singh5400/viz/SupplyChainRiskCostAnalytics/SupplyChainRiskCostAnalytics20222024)
- 💻 **SQL Queries + Dataset:** [GitHub Repository](https://github.com/Jaspreet-analyst/supply-chain-risk-analytics)
- 🔗 **Project 1:** [Ocean Freight SQL Analytics](https://github.com/Jaspreet-analyst/ocean-freight-sql-analytics)

---

*Jaspreet Singh | Ocean Import Agent | Supply Chain Analyst — Greater Toronto Area*
*8+ years across ocean import, air freight, carrier negotiations, D&D cost recovery and cold chain operations*
