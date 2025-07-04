# music-store-sql-analysis
# 🎵 Music Store Data Analysis (SQL + MySQL)

This project explores a fictional music store database using **MySQL**. It demonstrates real-world data analysis with complex joins, subqueries, filtering, and aggregation.

---

## 📂 Project Contents

- ✅ **CSV Data Import**: Automated using Python
- ✅ **Relational Database Setup**: Tables like `track`, `artist`, `genre`, `invoice`, `customer`, etc.
- ✅ **SQL Queries**: Answering business questions with joins, GROUP BY, and filters

---

## 📌 Key SQL Queries

### 🎸 Top Rock Listeners
```sql
SELECT DISTINCT email, first_name, last_name
FROM customer
JOIN invoice ON invoice.customer_id = customer.customer_id
JOIN invoice_line ON invoice_line.invoice_id = invoice.invoice_id
JOIN track ON track.track_id = invoice_line.track_id
JOIN genre ON genre.genre_id = track.genre_id
WHERE genre.name = 'Rock';
