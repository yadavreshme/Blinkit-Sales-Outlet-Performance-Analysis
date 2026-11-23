# Blinkit Sales & Outlet Performance Analysis

![SQL](https://img.shields.io/badge/SQL-PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=plotly&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)

An end-to-end business intelligence project analysing **Blinkit's grocery sales and outlet data**. The same set of business questions is answered with **SQL**, **Python**, **Excel** and **Power BI**: from cleaning and KPI calculation through to an interactive dashboard for stakeholders.

---

## Table of Contents

- [Overview](#overview)
- [Key Metrics](#key-metrics)
- [Tech Stack](#tech-stack)
- [Dataset](#dataset)
- [Business Requirements](#business-requirements)
- [Project Workflow](#project-workflow)
- [Repository Structure](#repository-structure)
- [Getting Started](#getting-started)
- [Dashboard](#dashboard)
- [Key Insights](#key-insights)

---

## Overview

**Objective:** analyse Blinkit's sales performance, customer satisfaction and inventory distribution to find:

- Patterns in customer purchasing behaviour
- Under-performing product categories and outlets
- Opportunities to improve revenue and operational efficiency

The project mirrors a real analyst workflow: raw data → cleaning → KPI calculation → visual analysis → dashboard and recommendations.

---

## Key Metrics

| KPI | Value |
|-----|-------|
| **Total Sales** | $1.20M |
| **Average Sales** | $141 |
| **Number of Items** | 8,523 |
| **Average Rating** | 4.0 |

---

## Tech Stack

| Category | Tools | Used For |
|----------|-------|----------|
| **Database / Query** | PostgreSQL (SQL) | Table creation, CSV import, data cleaning (`UPDATE … CASE`), KPI and aggregate queries |
| **Programming** | Python 3 | Data cleaning and exploratory data analysis |
| **Python Libraries** | Pandas, NumPy | Data loading, transformation and grouped aggregations |
| **Visualisation (Python)** | Matplotlib, Seaborn | Pie, bar, stacked-bar, line and funnel-style charts |
| **Notebook** | Jupyter Notebook | Reproducible analysis (`Blinkit Analysis.ipynb`) |
| **Spreadsheet** | Microsoft Excel | Raw data, validation, pivot tables and an Excel dashboard |
| **BI / Dashboard** | Microsoft Power BI (DAX, Power Query) | Interactive dashboard with KPI cards, slicers and a filter panel |
| **Reporting** | PowerPoint → PDF | Insights report and dashboard export |

---

## Dataset

- **File:** `BlinkIT Grocery Data.xlsx`
- **Size:** 8,523 records

| Column | Description |
|--------|-------------|
| `Item_Identifier` | Unique product ID |
| `Item_Fat_Content` | Low Fat / Regular (cleaned from `LF`, `low fat`, `reg`) |
| `Item_Type` | Product category (e.g. Dairy, Snacks, Fruits & Vegetables) |
| `Item_Visibility` | Share of display area allocated to the item |
| `Item_Weight` | Product weight |
| `Outlet_Identifier` | Unique outlet ID |
| `Outlet_Establishment_Year` | Year the outlet opened |
| `Outlet_Size` | Small / Medium / High |
| `Outlet_Location_Type` | Tier 1 / Tier 2 / Tier 3 |
| `Outlet_Type` | Grocery Store / Supermarket Type 1–3 |
| `Sales` | Sales value of the item |
| `Rating` | Customer rating |

---

## Business Requirements

### KPIs

Total Sales · Average Sales · Number of Items · Average Rating

### Analysis & Charts

| # | Requirement | Goal | Chart |
|---|-------------|------|-------|
| 1 | Total Sales by Fat Content | Impact of fat content on revenue | Donut chart |
| 2 | Total Sales by Item Type | Best and worst performing categories | Bar chart |
| 3 | Fat Content by Outlet Tier | Sales by fat content across outlet tiers | Stacked column chart |
| 4 | Sales by Outlet Establishment Year | Effect of outlet age on sales | Line chart |
| 5 | Sales by Outlet Size | Revenue contribution by outlet size | Donut / pie chart |
| 6 | Sales by Outlet Location | Geographic distribution of sales | Funnel chart |
| 7 | All KPIs by Outlet Type | Compare every KPI across outlet types | Matrix table |

---

## Project Workflow

```text
Raw data (Excel)
   │
   ├─► SQL (PostgreSQL) ── cleaning + KPI / aggregate queries
   ├─► Python (Jupyter)  ── cleaning, EDA, charts
   ├─► Excel             ── validation, pivots, dashboard
   └─► Power BI          ── interactive dashboard
                               │
                               └─► Insights report (PDF)
```

1. **Data cleaning:** standardise `Item_Fat_Content` labels and check data types and missing values.
2. **KPI calculation:** total and average sales, item count and average rating.
3. **Granular analysis:** group by item type, fat content, outlet size, location, type and establishment year.
4. **Visualisation:** build the charts in Python and the interactive dashboard in Power BI.
5. **Reporting:** summarise findings and recommendations in the insights report.

---

## Repository Structure

```text
Blinkit-Sales-Outlet-Performance-Analysis/
├── BlinkIT Grocery Data.xlsx   # Raw dataset + Excel dashboard
├── BlinkIt_SQL.sql             # PostgreSQL scripts: schema, cleaning, KPIs, analysis
├── Blinkit Analysis.ipynb      # Python EDA and visualisations
├── BlinkIt.pbix                # Power BI dashboard
├── BlinkIt Dashboard.pdf       # Dashboard export
├── Blinkit Insights.pdf        # Insights and recommendations report
├── requirements.txt            # Python dependencies
└── README.md
```

---

## Getting Started

### Prerequisites

- Python 3.8+ and Jupyter Notebook
- PostgreSQL (or any SQL client, with minor syntax changes)
- Microsoft Power BI Desktop
- Microsoft Excel

### Run the Python analysis

```bash
git clone https://github.com/yadavreshme/Blinkit-Sales-Outlet-Performance-Analysis.git
cd Blinkit-Sales-Outlet-Performance-Analysis
pip install -r requirements.txt
jupyter notebook "Blinkit Analysis.ipynb"
```

### Run the SQL analysis

1. Export the `BlinkIT Grocery Data` sheet to CSV.
2. Update the file path in the `COPY` statement in `BlinkIt_SQL.sql`.
3. Run the script in PostgreSQL (psql or pgAdmin).

### Open the dashboard


---

## Dashboard

The Power BI dashboard includes:

- **KPI cards** for Total Sales, Average Sales, Number of Items and Average Rating
- A **filter panel** with slicers for Outlet Location, Outlet Size and Item Type
- Charts for fat content, item type, outlet tier, establishment year, outlet size and location
- A **matrix** comparing all KPIs by outlet type


