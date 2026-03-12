# 📊 Sales Analytics Dashboard — Data Warehouse Project

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-Data_Analysis_Expressions-0078D4?style=for-the-badge)
![Data Modeling](https://img.shields.io/badge/Data_Modeling-Star_Schema-green?style=for-the-badge)

---

## 🌟 Overview

This Power BI Dashboard is the **final analytical layer** of a full end-to-end Data Warehouse project.  
Raw data was ingested, cleaned, and transformed across **Bronze → Silver → Gold** layers using SQL Server, then visualized in this interactive 3-page Power BI report.

> 🔗 Data Source Project: [SQL Data Warehouse — by Mohammed Magdy](https://github.com/muuahmmed/sql_data_warehouse_project)  
> 🎓 Data Warehouse project inspired by [Data With Baraa](https://www.youtube.com/@DataWithBaraa) on YouTube.

---

## 🖼️ Dashboard Preview

### 🏠 Page 1 — Sales Executive Summary
![Page 1](Screens/page1.png)

### 📦 Page 2 — Product Performance
![Page 2](Screens/page2.png)

### 👥 Page 3 — Customer Insights
![Page 3](Screens/page3.png)

---

## 🏗️ Data Architecture

```
CSV Files (CRM + ERP)
        ↓
   Bronze Layer      → Raw Data
        ↓
   Silver Layer      → Cleaned & Transformed Data
        ↓
    Gold Layer       → dim_customers | dim_products | fact_sales
        ↓
  Power BI Dashboard → 3-Page Interactive Report
```

---

## 📐 Data Model — Star Schema

| Table | Type | Description |
|-------|------|-------------|
| `fact_sales` | Fact | Sales transactions (60K rows) |
| `dim_customers` | Dimension | Customer demographics (18K rows) |
| `dim_products` | Dimension | Product catalog (295 rows) |

---

## 📊 Dashboard Pages

### 🏠 Page 1: Sales Executive Summary
| Visual | Description |
|--------|-------------|
| KPI Cards | Total Sales, Total Orders, Total Customers, Total Profit, Profit Margin % |
| Line Chart | Sales Trend by Month |
| Bar Chart | Sales by Country |
| Bar Chart | Sales by Category |
| Donut Chart | Sales by Product Line |

### 📦 Page 2: Product Performance
| Visual | Description |
|--------|-------------|
| Bar Chart | Top 10 Products by Sales |
| Bar Chart | Sales by Subcategory |
| Column Chart | Sales by Category & Subcategory (Top 6) |
| Donut Chart | Sales by Product Line Mix |
| KPI Card | Total Quantity (60K) |

### 👥 Page 3: Customer Insights
| Visual | Description |
|--------|-------------|
| Bar Chart | Top 10 Customers by Sales |
| Bar Chart | Customers by Country |
| Bar Chart | Sales by Age Group |
| Donut Chart | Sales by Gender |
| Donut Chart | Sales by Marital Status |

---

## ⚡ DAX Measures

```dax
Total Sales = SUM(fact_sales[sales_amount])

Total Orders = DISTINCTCOUNT(fact_sales[order_id])

Total Customers = DISTINCTCOUNT(fact_sales[customer_key])

Total Quantity = SUM(fact_sales[quantity])

Total Cost = SUMX(fact_sales, RELATED(products[cost]) * fact_sales[quantity])

Total Profit = [Total Sales] - [Total Cost]

Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0) * 100

Avg Order Value = DIVIDE([Total Sales], [Total Orders], 0)
```

---

## 🎨 Design Theme

| Element | Color |
|---------|-------|
| Background | `#1A1A2E` |
| Cards & Charts | `#16213E` |
| Accent | `#E94560` |
| Text | `#FFFFFF` |

---

## 🛠️ Tools & Technologies

- **SQL Server** — Data Warehouse (Bronze/Silver/Gold)
- **Power BI Desktop** — Dashboard & Visualizations
- **DAX** — Calculated Measures & Columns
- **Power Query** — Data Transformation

---

## 🚀 How to Use

1. Clone this repository
2. Set up the Data Warehouse first → [SQL Data Warehouse Project](https://github.com/muuahmmed/sql_data_warehouse_project)
3. Open `Project/dashboard.pbix` in Power BI Desktop
4. Update the SQL Server connection:
   - Server: `YOUR_SERVER_NAME\SQLEXPRESS`
   - Database: `DataWarehouse`
5. Refresh the data ✅

---

## 📁 Repository Structure

```
📦 PowerBI-Sales-Dashboard-DataWarehouse
 ┣ 📂 Project
 ┃ ┗ 📄 dashboard.pbix
 ┣ 📂 Screens
 ┃ ┣ 🖼️ page1.png  (Sales Executive Summary)
 ┃ ┣ 🖼️ page2.png  (Product Performance)
 ┃ ┗ 🖼️ page3.png  (Customer Insights)
 ┗ 📄 README.md
```

---

## 📬 Connect with Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/mohammed-magdy-b8a37a1a8/)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/muuahmmed)

---

*Created by Mohammed Magdy*
