# ZUS Coffee — Surge Operations Analytics

> **Can data predict when a cafe is about to crash?**  
> A personal experience turned into a data project.

---

## Background

During Raya 2026, I walked into a ZUS Coffee in Ipoh with barely any customers inside — and waited **45 minutes** for my drink.

The reason: ShopeeFood and GrabFood orders were flooding in silently at the same time as walk-in customers, with no visibility for staff on total queue load. I wanted to quantify this problem.

---

## Key findings

| Finding | Result |
|---|---|
| Crash point | Prep time breaches 20 min once hourly orders exceed **30/hr** |
| Worst occasion | **Raya 2026** — 34.8% of orders exceeded 20 min wait |
| Forecast gap | Holiday MAPE is **14.1%** vs 8.1% on normal days |
| Revenue at risk | **MYR 120,286** from orders with >20 min wait |

---

## Recommendations

1. **Throttle online orders** when hourly volume exceeds 30 — estimated to cut breach rate from 40% → 12%
2. **Add holiday staffing** for Raya, CNY, New Year windows based on pre-holiday demand forecast
3. **Replace rolling average** with a calendar-aware model that flags Malaysian public holidays

---

## Tools & skills

`Python` `SQL (SQLite)` `Pandas` `Matplotlib` `Chart.js` `Google Trends`

---

## Data sources

- [Kaggle — Coffee Shop Sales](https://www.kaggle.com/datasets/ahmedabbas757/coffee-sales) — 149k timestamped transactions
- Google Trends Malaysia — "ZUS Coffee" (5-year monthly search interest)

**Note:** ZUS Coffee does not publish transaction data. The Kaggle dataset was remapped to KL zones, shifted to Oct 2025–Mar 2026, and calibrated to ZUS's published benchmarks (200–400 cups/day, 70% digital orders). This project was built with AI assistance for code generation. All analytical decisions and interpretations are my own.

---

## Project files

| File | Description |
|---|---|
| `02_clean_enrich.py` | Data cleaning, KL zone mapping, holiday flags, prep time simulation |
| `03_sql_analysis.py` | 7 SQL queries — peak hours, crash point, holiday impact, revenue at risk |
| `04_python_analysis.py` | 5 charts + 7-day rolling demand forecast |
| `05_dashboard.py` | Generates `zus_dashboard.html` — open in any browser |
| `zus_dashboard.html` | Interactive dashboard — **start here** |

---

*Adleena Ahmad Nizam · 2026*
