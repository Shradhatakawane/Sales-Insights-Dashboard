# Sales Insights Data Analysis Project

## Project Overview
The *Sales Insights Data Analysis Project* aims to analyze customer and transaction data using SQL queries. This project involves querying a database to retrieve specific insights such as total customers, market-specific transactions, revenue calculations, and sales trends. 

### Objectives:
- Perform SQL queries to retrieve useful insights.
- Analyze customer records, market-specific transactions, and sales trends.
- Join tables to gain more meaningful data insights.
  
## SQL Queries Used

### 1. Show all customer records:
```sql
SELECT * FROM customers;

-- Sales Insights Data Analysis Queries

-- 1. Show all customer records
SELECT * FROM customers;

-- 2. Show total number of customers
SELECT count(*) FROM customers;

-- 3. Show transactions for Chennai market (market code for Chennai is Mark001)
SELECT * FROM transactions WHERE market_code='Mark001';

-- 4. Show distinct product codes that were sold in Chennai
SELECT DISTINCT product_code FROM transactions WHERE market_code='Mark001';

-- 5. Show transactions where currency is US dollars
SELECT * FROM transactions WHERE currency='USD';

-- 6. Show transactions in 2020 joined by the date table
SELECT transactions., date. 
FROM transactions 
INNER JOIN date 
ON transactions.order_date = date.date 
WHERE date.year = 2020;

-- 7. Show total revenue in the year 2020
SELECT SUM(transactions.sales_amount) 
FROM transactions 
INNER JOIN date 
ON transactions.order_date = date.date 
WHERE date.year = 2020 
  AND (transactions.currency = 'INR' OR transactions.currency = 'USD');

-- 8. Show total revenue in January 2020
SELECT SUM(transactions.sales_amount) 
FROM transactions 
INNER JOIN date 
ON transactions.order_date = date.date 
WHERE date.year = 2020 
  AND date.month_name = 'January' 
  AND (transactions.currency = 'INR' OR transactions.currency = 'USD');

-- 9. Show total revenue in 2020 for Chennai
SELECT SUM(transactions.sales_amount) 
FROM transactions 
INNER JOIN date 
ON transactions.order_date = date.date 
WHERE date.year = 2020 
  AND transactions.market_code = 'Mark001';
