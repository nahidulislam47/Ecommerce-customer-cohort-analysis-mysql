![MySQL](https://img.shields.io/badge/MySQL-8.0-blue?logo=mysql)
![Status](https://img.shields.io/badge/Status-Completed-green)
![Records](https://img.shields.io/badge/Records-1.6M+-orange)

## 📌 Project Overview

End-to-end SQL analysis of **Maven Fuzzy Factory** — a fictional online retail store selling teddy bears. This project analyzes **1.6M+ rows** of raw transactional and web session data to uncover actionable business insights across traffic, revenue, customer behavior, and marketing performance.

---

## 🗄️ Database Schema

```
website_sessions ──┐
                   ├──► orders ──► order_items ──► order_item_refunds
website_pageviews ─┘                    │
                                        └──► products
```

| Table | Rows | Description |
|---|---|---|
| website_sessions | 472,871 | User sessions with UTM & device data |
| website_pageviews | 1,188,124 | Page-level clickstream data |
| orders | 32,313 | Customer orders |
| order_items | 40,025 | Individual items per order |
| products | 4 | Product catalog |
| order_item_refunds | 1,731 | Refund transactions |

---

## 📊 Analysis Sections

### 1. Traffic & Session Trends
**Business Question:** How has website traffic grown over time?

- Monthly session & order volume trend
- Traffic breakdown by UTM source & campaign
- Device-type split (mobile vs desktop)

**Key Findings:**
- Website traffic grew **15x** over 3 years (1,879 → 29,722 monthly sessions)
- Orders grew **38x** (60 → 2,314/month) — faster than traffic
- Conversion rate improved from **2.65% to 8.69%**
- **gsearch nonbrand** dominates with **59.79%** of all traffic
- Desktop CVR **(8.50%)** is **3x higher** than mobile **(3.09%)**

---

### 2. Conversion Funnel Analysis
**Business Question:** Where do users drop off on the purchase path?

```
Homepage → Products → Product Detail → Cart → Shipping → Billing → Order
472,871     261,231      210,214        94,953   64,484    52,058   32,313
  100%       55.2%        80.5%         45.2%    67.9%     80.7%    62.1%
```

**Key Findings:**
- Biggest drop-off: **Product Detail → Cart (54.8% drop)**
- Only **55.2%** of homepage visitors proceed to products page
- Once users reach billing, **62.1%** complete the purchase
- **Opportunity:** Improving product pages could significantly boost revenue

---

### 3. Revenue & Product Performance
**Business Question:** Which products drive the most revenue & margin?

**Key Findings:**
- The Original Mr. Fuzzy is the **primary revenue driver**
- Cross-sell analysis revealed product bundling opportunities
- Monthly revenue shows consistent **upward MoM growth**

---

### 4. Customer Behavior & Repeat Analysis
**Business Question:** How loyal are our customers?

**Key Findings:**
- **Top 5 customers** all made exactly **3 purchases**
- Top customer avg order value **$73–$84** vs overall avg ~$50
- Most repeat purchases happen within **80 days** of first order
- Cohort retention drops sharply after Month 0 — **<2% return in Month 1**

---

### 5. Refund & Quality Analysis
**Business Question:** Which products have the highest refund rates?

- Refund rate by product
- Total refund amount per product
- Quality flag identification

---

### 6. Marketing Channel ROI
**Business Question:** Which acquisition channels give the best ROI?

**Key Findings:**
- gsearch nonbrand desktop: highest revenue per session
- Mobile traffic high but converts poorly — budget reallocation recommended
- Brand campaigns only **8.72%** of traffic — brand awareness still growing

---

### 7. Cohort Retention Analysis *(Advanced)*
**Business Question:** Do early customers come back?

**Key Findings:**
- Sharp retention drop from Month 0 → Month 1 across all cohorts
- Indicates significant **re-engagement opportunity** via email campaigns
- Earlier cohorts show slightly better long-term retention

---

## 🛠️ SQL Skills Demonstrated

| Skill | Used In |
|---|---|
| `CTEs (WITH clause)` | Funnel, Cohort, Bounce Rate |
| `Window Functions (LAG, ROW_NUMBER)` | MoM Growth, Repurchase Lag |
| `Conditional Aggregation (CASE WHEN)` | Funnel, Device Split |
| `Multi-table JOINs` | All sections |
| `Subqueries` | Bounce Rate |
| `Date Functions` | Cohort, Monthly Trends |
| `PERIOD_DIFF` | Cohort Retention |
| `Views` | Session-Order enriched view |

---

## 📁 Project Structure

```
ecommerce-customer-cohort-analysis-mysql/
├── README.md
├── maven_fuzzy_factory_portfolio.sql   ← All queries
└── screenshots/                        ← Query result screenshots
```

---

## 🚀 How to Run

```sql
-- 1. Create database
CREATE DATABASE maven_fuzzy_factory;
USE maven_fuzzy_factory;

-- 2. Import CSV files via MySQL Workbench or LOAD DATA LOCAL INFILE
-- 3. Run maven_fuzzy_factory_portfolio.sql section by section
```

**Dataset:** [Maven Analytics — Toy Store E-Commerce Database](https://mavenanalytics.io/data-playground)

---

## 👤 Author

**[Md.Nahidul islam]**
[LinkedIn](https://linkedin.com/in/md-nahidul-islam-30b75b396) | [GitHub](https://github.com/nahidulislam47)
