# 🛒 RetailMart Enterprise Analytics Platform

[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-blue?logo=postgresql\&logoColor=white)](https://www.postgresql.org/)
[![Status](https://img.shields.io/badge/Status-Completed-success)](#)
[![Domain](https://img.shields.io/badge/Domain-Data%20Analytics-blueviolet)](#)

> A comprehensive, production-ready analytics platform built with PostgreSQL, featuring **25+ views**, **10 materialized views**, **32 JSON export functions**, and a **7-tab interactive dashboard**.

![Dashboard Preview](06_dashboard/src/executive_dashboard.png)

---

## 🎯 Project Overview

This project demonstrates **enterprise-grade SQL analytics capabilities**, transforming raw retail data into **actionable business insights**.

The platform is inspired by **real-world analytics systems** used at companies like **Flipkart, Amazon, and Swiggy**, and focuses on **performance optimization, scalability, and business-driven decision making**.

---

## ✨ Key Features

* **📊 25+ Regular Views** – Real-time analytics across 6 business domains
* **⚡ 10 Materialized Views** – Pre-computed KPIs for instant dashboard loading
* **🔄 32 JSON Export Functions** – API-ready data for frontend consumption
* **📱 7-Tab Dashboard** – Professional, responsive visualization
* **🚨 6 Alert Types** – Proactive business monitoring
* **📈 Complete ETL Pipeline** – Automated refresh and export scripts

---

## 🏗️ Architecture

```
Retailmart_Enterprise_Analytics/
│
├── 01_setup/                          # Foundation scripts
│   ├── 01_create_analytics_schema.sql
│   ├── 02_create_metadata_tables.sql
│   └── 03_create_indexes.sql
│
├── 02_data_quality/                   # Data validation
│   └── data_quality_checks.sql
│
├── 03_kpi_queries/                    # Analytics modules
│   ├── 01_sales_analytics.sql         # 8 views, 2 MVs
│   ├── 02_customer_analytics.sql      # 4 views, 3 MVs
│   ├── 03_product_analytics.sql       # 3 views, 2 MVs
│   ├── 04_store_analytics.sql         # 3 views, 1 MV
│   ├── 05_operations_analytics.sql    # 5 views, 1 MV
│   └── 06_marketing_analytics.sql     # 4 views, 1 MV
│
├── 04_alerts/                         # Business alerts
│   └── business_alerts.sql
│
├── 05_refresh/                        # Automation
│   ├── refresh_all_analytics.sql
│   └── export_all_json.sh
│
├── 06_dashboard/                      # Frontend
│   ├── index.html
│   ├── css/                           # Stylesheets
│   │   └── styles.css
│   ├── js/                            # Dashboard logic
│   │   └── dashboard.js
│   ├── data/                          # Generated JSON data
│   └── src/                           # Static assets (images, previews)
│       └── executive_dashboard.png
│
└── 07_documentation/
    ├── README.md
    ├── data_dictionary.md
    └── kpi_definitions.md
```

---

## 🚀 Quick Start

### Prerequisites

* PostgreSQL 16+
* pgAdmin 4 or any PostgreSQL client
* Web browser (for dashboard)
* Bash shell (for export script)

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/Mayank230604/Retailmart_Enterprise_Analytics.git
   cd Retailmart_Enterprise_Analytics
   ```

2. **Create the RetailMart database**(if not exists)

   ```sql
   CREATE DATABASE retailmart_22;
   ```

3. **Run setup scripts in order**

   ```bash
   psql -d retailmart_22 -U postgres -f 01_setup/01_create_analytics_schema.sql
   psql -d retailmart_22 -U postgres -f 01_setup/02_create_metadata_tables.sql
   psql -d retailmart_22 -U postgres -f 01_setup/03_create_indexes.sql
   ```

4. **Run data quality checks**

   ```bash
   psql -d retailmart_22 -U postgres -f 02_data_quality/data_quality_checks.sql
   ```

5. **Create analytics views**

   ```bash
   psql -d retailmart_22 -U postgres -f 03_kpi_queries/01_sales_analytics.sql
   psql -d retailmart_22 -U postgres -f 03_kpi_queries/02_customer_analytics.sql
   psql -d retailmart_22 -U postgres -f 03_kpi_queries/03_product_analytics.sql
   psql -d retailmart_22 -U postgres -f 03_kpi_queries/04_store_analytics.sql
   psql -d retailmart_22 -U postgres -f 03_kpi_queries/05_operations_analytics.sql
   psql -d retailmart_22 -U postgres -f 03_kpi_queries/06_marketing_analytics.sql
   ```

6. **Create alerts**

   ```bash
   psql -d retailmart_22 -U postgres -f 04_alerts/business_alerts.sql
   ```

7. **Set up refresh functions**

   ```bash
   psql -d retailmart_22 -U postgres -f 05_refresh/refresh_all_analytics.sql
   ```

8. **Export JSON data**

   ```bash
   chmod +x 05_refresh/export_all_json.sh
   ./05_refresh/export_all_json.sh ./06_dashboard/data
   ```

9. **Open dashboard**

   ```bash
   cd 06_dashboard
   python -m http.server 8000
   ```

   Open **[http://localhost:8000](http://localhost:8000)**

---

## 📊 Analytics Modules

### 1. Sales Analytics

| KPI                     | Type | Description                       |
| ----------------------- | ---- | --------------------------------- |
| Monthly Sales Dashboard | MV   | MoM, YoY growth, moving averages  |
| Executive Summary       | MV   | Top-level KPIs                    |
| Daily Sales Summary     | View | Day-level metrics with DoD growth |
| Payment Mode Analysis   | View | Revenue by payment method         |

### 2. Customer Analytics

| KPI                     | Type | Description                                |
| ----------------------- | ---- | ------------------------------------------ |
| Customer Lifetime Value | MV   | CLV with Platinum/Gold/Silver/Bronze tiers |
| RFM Analysis            | MV   | Recency-Frequency-Monetary segmentation    |
| Cohort Retention        | MV   | Monthly cohort retention rates             |
| Churn Risk              | View | High-value customers at risk               |

### 3. Product Analytics

| KPI                  | Type | Description                          |
| -------------------- | ---- | ------------------------------------ |
| Top Products         | MV   | Products ranked by revenue and units |
| ABC Analysis         | MV   | Pareto classification (80/20 rule)   |
| Category Performance | View | Category-level metrics               |
| Inventory Turnover   | View | Stock velocity and health            |

### 4. Store Analytics

| KPI                    | Type | Description                          |
| ---------------------- | ---- | ------------------------------------ |
| Store Performance      | MV   | Revenue, profit, efficiency by store |
| Regional Performance   | View | Regional aggregation                 |
| Store Inventory Status | View | Inventory health by location         |

### 5. Operations Analytics

| KPI                  | Type | Description                  |
| -------------------- | ---- | ---------------------------- |
| Delivery Performance | View | SLA tracking, on-time %      |
| Courier Comparison   | View | Courier partner benchmarking |
| Return Analysis      | View | Return rates by category     |
| Payment Success Rate | View | Payment gateway metrics      |

### 6. Marketing Analytics

| KPI                     | Type | Description                    |
| ----------------------- | ---- | ------------------------------ |
| Campaign Performance    | View | ROI, CPA, conversion rates     |
| Channel Performance     | View | Ad spend efficiency by channel |
| Promotion Effectiveness | View | Promotion impact analysis      |

---

## 🚨 Business Alerts

The platform includes **6 proactive alert types**:

1. **Critical Stock** – Top products with stock < 10 units
2. **High-Value Churn** – Platinum/Gold customers inactive 60+ days
3. **Revenue Anomaly** – Daily revenue < 75% of 7-day average
4. **Delayed Shipments** – Orders not shipped within 3 days
5. **High Return Rate** – Categories with return rate > 15%
6. **Payment Concentration** – Single payment mode > 70%

---

## 🔄 Refresh & Automation

### Manual Refresh

```sql
SELECT * FROM analytics.fn_refresh_all_analytics();
SELECT * FROM analytics.fn_refresh_module('sales');
SELECT * FROM analytics.fn_get_refresh_status();
```

### Scheduled Refresh (cron)

```bash
5 * * * * /path/to/export_all_json.sh --refresh >> /var/log/analytics.log 2>&1
```

---

## 🖥️ Dashboard Features

* **7 Tabs**: Executive, Sales, Customers, Products, Stores, Operations, Marketing
* **Client-side caching** (5 minutes)
* **Graceful error handling**
* **Responsive design**
* **Optional auto-refresh**

---

## 📈 Performance Optimizations

* 53+ indexes on frequently queried columns
* Materialized views for expensive aggregations
* Composite indexes for common query patterns
* ANALYZE-based query planner optimization

---

## 🎓 Learning Outcomes

* Advanced SQL (CTEs, window functions, analytics)
* Materialized view optimization
* Database schema design & normalization
* Data quality validation
* ETL pipeline development
* JSON export for dashboards
* Production-style analytics engineering

---

## 👨‍💻 Author

**Mayank Adeva**
Aspiring Data Analyst / Analytics Engineer
🔗 GitHub: [https://github.com/Mayank230604](https://github.com/Mayank230604)

---

⭐ If you found this project useful, feel free to **star the repository**!

