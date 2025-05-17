
# 🎵 SQL Data Analysis: Chinook Music Store

**Goal:** Demonstrate basic SQL querying skills by exploring a sample music store database using SQLite.

**Tools Used:**  
- SQLite  
- DB Browser for SQLite (Free GUI tool)

---

## 📘 Project Overview

This beginner-friendly SQL project analyzes data from the [Chinook](https://github.com/lerocha/chinook-database) database, which simulates a digital music store. The database includes tables for customers, invoices, tracks, artists, albums, and more.

The goal is to write and interpret simple SQL queries to extract insights about customer demographics and purchasing patterns.

---

## 📦 Dataset

- **Source:** [Chinook SQLite DB](https://github.com/lerocha/chinook-database/raw/master/ChinookDatabase/DataSources/Chinook_Sqlite.sqlite)
- **Schema Includes:**
  - Customers
  - Invoices
  - InvoiceLines
  - Tracks
  - Albums
  - Artists
  - Employees

---

## 🔍 SQL Queries & Outputs

### 1. 🧑 First 5 Customers

```sql
SELECT * FROM Customer LIMIT 5;;
```

This query previews a few customer records to understand the available columns.

---

### 2. 🌍 Unique Countries with Customers

```sql
SELECT DISTINCT country FROM customer;
```

Identifies the countries from which the company has customers.

---

### 3. 🧾 Total Number of Invoices

```sql
SELECT COUNT(*) AS total_invoices FROM invoice;
```

Returns the total number of purchases recorded.

---

### 4. 💰 Total Sales by Country

```sql
SELECT billingcountry, SUM(total) AS total_sales
FROM invoice
GROUP BY billingcountry
ORDER BY total_sales DESC;
```

This aggregates total revenue per billing country.

---

### 5. 🏆 Top 5 Customers by Revenue

```sql
SELECT customerid, SUM(total) AS amount_spent
FROM invoice
GROUP BY customerid
ORDER BY amount_spent DESC
LIMIT 5;
```

Ranks the customers who spent the most.

---

## 📊 Key Insights

- **Top revenue-generating countries** include the USA, Canada, and France.
- Customers are distributed across **more than a dozen countries**.
- **A small number of customers** contribute to a large portion of the revenue.

---

## 🧰 What I Practiced

- Connecting to and browsing an SQLite database.
- Writing simple SQL queries using:
  - `SELECT`, `GROUP BY`, `ORDER BY`, `COUNT`, `SUM`, `LIMIT`, `DISTINCT`
- Using a graphical SQL tool (DB Browser) to explore and query a database.

---

## 🖼️ Screenshots

📁 Stored in: [`assets/sql-project/`](assets/sql-project/)  
📌 
---

## 📁 Files in this Project

| File | Description |
|------|-------------|
| [`Chinook_Sqlite.sqlite`](../Chinook_Sqlite.sqlite) | The SQLite database file |
| [`sql-chinook-analysis.md`](sql-chinook-analysis.md) | This markdown report |
| [`assets/sql-project/`](assets/sql-project/) | Folder with screenshots of query results |

---


## 🔗 References

- 🔹 [Chinook Database GitHub Repo](https://github.com/lerocha/chinook-database)
- 🔹 [Download DB Browser for SQLite](https://sqlitebrowser.org/dl/)
