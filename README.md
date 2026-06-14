<div align="center">

# 🔗 Supply Chain Risk & Cost Analytics

**End-to-end supply chain cost and risk analysis — connecting supplier reliability, shipment delays, D&D charges and inventory exposure across global trade lanes**

</div>

---

## 📌 Project Overview

Most supply chain analytics projects stop at shipment tracking. This project goes deeper — modeling the **financial ripple effect** of operational failures across the entire supply chain.

When a supplier is unreliable → shipments are delayed → containers sit at port → D&D charges accumulate → inventory runs low → stockouts cost the business money.

This project quantifies every step of that chain using **5 relational tables, 13 SQL queries, and real freight forwarding domain knowledge.**

---

## ❓ Business Questions Answered

| # | Business Question | SQL Concept |
|---|---|---|
| 1 | Which shipments have the highest total landed cost? | 3-table JOIN |
| 2 | Which suppliers cause the most delays and D&D charges? | JOIN + GROUP BY |
| 3 | Which carrier and port combinations generate the most D&D? | JOIN + Aggregation |
| 4 | Which inventory items are at critical risk due to supplier issues? | JOIN + WHERE |
| 5 | Which shipments have D&D charges above 10% of total cost? | CTE + Filter |
| 6 | Which high risk suppliers also have critical inventory? | Nested CTEs |
| 7 | Which carriers have above average D&D charges? | Subquery + HAVING |
| 8 | How do landed costs trend month over month? | Window Running Total |
| 9 | How do carriers rank by total D&D charges? | RANK() + Percentile |
| 10 | What is the D&D breakdown by port and carrier? | PARTITION BY |
| 11 | Which SKUs have the highest total stockout exposure? | JOIN + RANK() |
| 12 | Which carrier drives the highest cost per destination port? | CTE + PARTITION BY |
| 13 | What is the full supply chain risk summary per supplier? | Multi-CTE + RANK() |

---

## 🗄️ Database Schema

```
suppliers (20 rows)
    │
    ├──→ shipments (1,000 rows)
    │         │
    │         ├──→ containers (5,573 rows)
    │         │
    │         └──→ costs (1,000 rows)
    │
    └──→ inventory (50 rows)
```

| Table | Rows | Key Fields |
|---|---|---|
| `suppliers` | 20 | Risk Rating, Reliability Score, Lead Time, Annual Spend |
| `shipments` | 1,000 | Carrier, POL, POD, Delay Days, Delay Reason |
| `containers` | 5,573 | Free Days, Port Dwell Days, D&D Rate, D&D Charges |
| `inventory` | 50 | Stock Status, Reorder Point, Safety Stock, Stockout Cost |
| `costs` | 1,000 | Freight Cost, D&D Charges, Landed Cost, D&D % of Total |

---

## 🧠 SQL Skills Demonstrated

| Level | Concepts |
|---|---|
| Level 1 — Multi-Table JOINs | 2-table & 3-table JOINs, LEFT JOIN, Filtered JOINs with WHERE |
| Level 2 — CTEs & Subqueries | Single CTEs, Nested CTEs, Correlated Subqueries with HAVING |
| Level 3 — Window Functions | RANK() OVER, PARTITION BY, Running Totals, Risk Exposure Scoring |

---

## 📁 File Structure

| Folder | File | Description |
|---|---|---|
| `data/` | `suppliers.csv` | 20 supplier records with risk ratings |
| `data/` | `shipments.csv` | 1,000 shipment records across global lanes |
| `data/` | `containers.csv` | 5,573 container records with D&D charges |
| `data/` | `inventory.csv` | 50 SKU records with stock levels |
| `data/` | `costs.csv` | 1,000 landed cost breakdowns |
| `queries/` | `supply_chain_analysis.sql` | All 13 SQL queries L1 to L3 |

---

## 🛠️ Tools Used

| Tool | Purpose |
|---|---|
| MySQL 8.0 | Relational database design and all SQL queries |
| Tableau Public | Interactive dashboard *(in progress)* |
| GitHub | Version control and portfolio hosting |

---

## 🗺️ Roadmap

- [x] Design 5-table relational database schema
- [x] Generate interconnected datasets — 7,643 total rows
- [x] Load all tables into MySQL
- [x] Write Level 1 queries — Multi-table JOINs
- [x] Write Level 2 queries — CTEs and Subqueries
- [x] Write Level 3 queries — Window Functions
- [x] Build Tableau dashboard
- [ ] Write case study

---

## 👤 About Me

**Jaspreet Singh** | Ocean Import Agent | Supply Chain Analyst — Greater Toronto Area

8+ years across ocean import, air freight and supply chain operations with hands-on experience in carrier negotiations, D&D cost recovery, cold chain management and key account operations.

[![Tableau](https://img.shields.io/badge/Tableau-Live_Dashboard-E97627?style=for-the-badge&logo=tableau&logoColor=white)](https://public.tableau.com/app/profile/jaspreet.singh5400/viz/SupplyChainRiskCostAnalytics/SupplyChainRiskCostAnalytics20222024)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/YOUR-LINKEDIN-URL)
[![Project 1](https://img.shields.io/badge/Project_1-Ocean_Freight_SQL-4479A1?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Jaspreet-analyst/ocean-freight-sql-analytics)
