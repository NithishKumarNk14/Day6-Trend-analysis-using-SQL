# Day6-Trend-analysis-using-SQL

Task 6: Sales Trend Analysis Using SQL
🎯 Objective
Analyze monthly revenue and order volume trends from the online_sales dataset using SQL aggregation functions.

🛠️ Tools Used
Database: SQLite (can also be used with PostgreSQL or MySQL)

Language: SQL

Platform: Google Colab (Python + sqlite3)

Dataset: online_retail.csv (treated as online_sales table)

🔍 Task Requirements
Extract month and year from the order_date.

Group data by year/month.

Use SUM() to calculate monthly revenue.

Use COUNT(DISTINCT order_id) to calculate monthly volume.

Use ORDER BY to sort results by time.

Filter results for a specific time period (2010-01-01 to 2011-12-31).

🧠 Key SQL Concepts Used
EXTRACT(YEAR FROM ...), EXTRACT(MONTH FROM ...)

SUM(amount) for total revenue

COUNT(DISTINCT order_id) for unique order count

GROUP BY and ORDER BY

WHERE clause for time filtering

📈 Sample SQL Query (PostgreSQL/MySQL)
sql
Copy
Edit
SELECT 
    EXTRACT(YEAR FROM order_date) AS year,
    EXTRACT(MONTH FROM order_date) AS month,
    SUM(amount) AS total_revenue,
    COUNT(DISTINCT order_id) AS total_volume
FROM online_sales
WHERE order_date BETWEEN '2010-01-01' AND '2011-12-31'
GROUP BY year, month
ORDER BY year, month;
🔄 SQLite Version (used in Colab)
sql
Copy
Edit
SELECT 
    STRFTIME('%Y', order_date) AS year,
    STRFTIME('%m', order_date) AS month,
    SUM(amount) AS total_revenue,
    COUNT(DISTINCT order_id) AS total_volume
FROM online_sales
WHERE order_date BETWEEN '2010-01-01' AND '2011-12-31'
GROUP BY year, month
ORDER BY year, month;
