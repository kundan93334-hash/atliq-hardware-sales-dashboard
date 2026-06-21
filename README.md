# AtliQ Hardware — Sales Performance Dashboard (Power BI + PostgreSQL)

An end-to-end data analytics project where I connected **PostgreSQL** to **Power BI**, cleaned and modeled the data, built an interactive sales dashboard, and verified the final numbers using **SQL queries**.

---

## Project Overview

AtliQ Hardware is a hardware sales company operating across India. This project analyzes their sales data to answer:

- What is the total revenue and sales quantity?
- Which customers and products bring in the most revenue?
- How does revenue trend over time?
- Which regions perform best?

---

## Tools Used

- **PostgreSQL** — source database
- **Power BI Desktop** — data modeling, ETL, dashboard
- **Power Query** — data cleaning
- **DAX** — measures
- **SQL** — verifying dashboard numbers independently

---

## Data Model (Star Schema)

Connected 5 tables (1 fact table + 4 dimension tables: customers, products, markets, date) and built relationships between them to enable cross-filtering across the dashboard.

---

## Data Cleaning (ETL)

The raw data had a few real-world issues that needed fixing using Power Query:

- Removed non-India markets (New York, Paris) that were outside business scope
- Removed invalid transactions (sales_amount = 0 or -1)
- Converted USD transactions to INR using a calculated column (normalized_sales_amount)

---

## Dashboard

Built using DAX measures (Revenue, Sales Quantity) and multiple visuals:

- KPI cards for Total Revenue and Sales Quantity
- Interactive year slicer
- Revenue trend line chart (month-wise)
- Revenue and Sales Quantity by Customer
- Revenue by Market (region)
- Top 5 Customers by Revenue
- Top 5 Products by Revenue

---

## Verifying the Numbers with SQL

Instead of just trusting the Power BI output, I wrote SQL queries in pgAdmin to independently double-check the key numbers (total revenue, year-wise revenue, top customers) against the dashboard.

Example: Total revenue calculated in SQL (986,676,768) matched the Power BI card (987M). Year 2020 revenue in SQL (142,235,559) matched the Power BI slicer result (142M). Top 5 customers by revenue also matched exactly between SQL and the dashboard.

All numbers matched between SQL and Power BI.

---

## What I Learned

- Connecting Power BI to a PostgreSQL database
- Cleaning real-world messy data using Power Query
- Building a star schema data model
- Writing DAX measures
- Writing SQL to validate dashboard accuracy

---

## Files in this Repo

- sales_dashboard.pbix — Power BI project file
- README.md — this file
- 
