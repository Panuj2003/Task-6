# Task 6 – Sales Trend Analysis Using SQL (Monthly Revenue + Order Volume)

##  Objective  
Analyze monthly sales performance using SQL by calculating:
- Monthly Revenue  
- Order Volume  
- Top 3 highest-revenue months  
##  Tools Used  
- SQLite / MySQL / PostgreSQL  
- Any SQL editor (DB Browser, MySQL Workbench, PostgreSQL GUI)
##  Dataset  
Table: **online_sales**  
Columns:
- `order_id`  
- `product_id`  
- `amount`  
- `order_date`  

Sample data was inserted for analysis.
## SQL Query Summary

###  1) Monthly Revenue + Order Volume
```sql
SELECT
    STRFTIME('%Y', order_date) AS year,
    STRFTIME('%m', order_date) AS month,
    SUM(amount) AS monthly_revenue,
    COUNT(DISTINCT order_id) AS order_volume
FROM online_sales
GROUP BY year, month
ORDER BY year, month;
