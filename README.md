# 🛒 RetailMart Enterprise Analytics Platform

[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-blue?logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Status](https://img.shields.io/badge/Status-Completed-success)](#)
[![Domain](https://img.shields.io/badge/Domain-Data%20Analytics-blueviolet)](#)

> An enterprise-grade analytics platform built using **PostgreSQL**, delivering executive, sales, customer, product, operations, and marketing insights through optimized SQL, materialized views, and an interactive dashboard.

---

## 📸 Dashboard Preview

> A fully interactive, 7-module analytics dashboard powered entirely by PostgreSQL views and JSON exports.

### Executive Overview

![Executive Dashboard](06_dashboard/src/executive_dashboard.png)

---

## 🎯 Project Overview

RetailMart Enterprise Analytics Platform simulates a **real-world retail BI system**, transforming raw transactional data into **actionable business insights**.

This project was built as a **capstone SQL analytics project**, inspired by analytics systems used at companies like **Flipkart, Amazon, and Swiggy**, and focuses on **performance, scalability, and business decision-making**.

---

## ✨ Key Highlights

* 📊 **25+ SQL Views** covering 6 major business domains
* ⚡ **10 Materialized Views** for fast, dashboard-ready KPIs
* 🔄 **32 JSON Export Functions** for frontend/API consumption
* 🧩 **7 Analytics Modules** (Executive → Marketing)
* 🚨 **Automated Business Alerts** for anomalies & risks
* 📈 **End-to-End ETL Flow** with refresh & export automation

---

## 🏗️ Project Architecture

```
retailmart_analytics_project/
│
├── 01_setup/                # Schema, metadata & indexes
├── 02_data_quality/         # Data validation checks
├── 03_kpi_queries/          # Analytics modules (views & MVs)
├── 04_alerts/               # Business alert logic
├── 05_refresh/              # Refresh & export automation
├── 06_dashboard/            # HTML/CSS/JS dashboard
└── 07_documentation/        # Data dictionary & KPI definitions
```

---

## 🚀 Quick Start

### Prerequisites

* PostgreSQL 16+
* pgAdmin / psql
* Web browser
* Bash shell (for automation)

### Setup Steps

```bash
git clone https://github.com/Mayank230604/retailmart-enterprise-analytics.git
cd retailmart-enterprise-analytics
```

```sql
CREATE DATABASE retailmart_22;
```

```bash
psql -d retailmart_22 -U postgres -f 01_setup/01_create_analytics_schema.sql
psql -d retailmart_22 -U postgres -f 01_setup/02_create_metadata_tables.sql
psql -d retailmart_22 -U postgres -f 01_setup/03_create_indexes.sql
```

```bash
psql -d retailmart_22 -U postgres -f 02_data_quality/data_quality_checks.sql
```

```bash
psql -d retailmart_22 -U postgres -f 03_kpi_queries/01_sales_analytics.sql
psql -d retailmart_22 -U postgres -f 03_kpi_queries/02_customer_analytics.sql
psql -d retailmart_22 -U postgres -f 03_kpi_queries/03_product_analytics.sql
psql -d retailmart_22 -U postgres -f 03_kpi_queries/04_store_analytics.sql
psql -d retailmart_22 -U postgres -f 03_kpi_queries/05_operations_analytics.sql
psql -d retailmart_22 -U postgres -f 03_kpi_queries/06_marketing_analytics.sql
```

```bash
psql -d retailmart_22 -U postgres -f 04_alerts/business_alerts.sql
psql -d retailmart_22 -U postgres -f 05_refresh/refresh_all_analytics.sql
```

```bash
chmod +x 05_refresh/export_all_json.sh
./05_refresh/export_all_json.sh ./06_dashboard/data
```

```bash
cd 06_dashboard
python -m http.server 8000
```

Open 👉 **[http://localhost:8000](http://localhost:8000)**

---

## 📊 Analytics Modules

### 💰 Sales Analytics

* Daily & monthly sales trends
* Payment method analysis
* Quarter-on-quarter performance

### 👥 Customer Analytics

* RFM segmentation
* CLV tiering (Platinum → Bronze)
* Churn risk analysis
* Demographics

### 📦 Product Analytics

* Top products by revenue
* ABC (Pareto) classification
* Category performance
* Inventory health

### 🏬 Store Analytics

* Store rankings & scorecards
* Regional revenue vs profit
* Store tiering

### 🚚 Operations Analytics

* Delivery SLA tracking
* Courier benchmarking
* Returns & refund analysis

### 📢 Marketing Analytics

* Campaign ROI
* Channel performance
* Conversion efficiency

---

## 🚨 Business Alerts

* Critical stock levels
* High-value customer churn risk
* Revenue anomaly detection
* Delayed shipments
* High return rate categories
* Payment mode concentration risk

---

## ⚙️ Performance Optimizations

* 53+ indexes on high-frequency columns
* Materialized views for heavy aggregations
* ANALYZE & optimized query planning
* Modular refresh architecture

---

## 🎓 Skills Demonstrated

* Advanced SQL (CTEs, window functions, analytics)
* Materialized view optimization
* Data modeling & schema design
* ETL automation
* Business KPI design
* Dashboard integration using JSON
* Real-world analytics problem solving

---

## 👨‍💻 Author

**Mayank Adeva**
📍 Aspiring Data Analyst / Analytics Engineer
🔗 GitHub: [https://github.com/Mayank230604](https://github.com/Mayank230604)

---

⭐ If you found this project insightful, feel free to **star the repository**!

