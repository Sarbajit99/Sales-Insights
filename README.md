Problem Statement- Finding the Sales Performance accross various states in India?
## Sales Insights Data Analysis Project
### Data Analysis Using SQL
Used MySql for checking all the records in respective tables.
1. Show all customer records
    `SELECT * FROM customers;`

2. Show total number of customers
    `SELECT count(*) FROM customers;'
   
3. Show transactions for Chennai market (market code for chennai is Mark001)
   `SELECT * FROM transactions where market_code='Mark001;'

4. Show total revenue in year 2019,
    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2019 and transactions.currency="INR\r" or transactions.currency="USD\r";`

 5. Show total revenue in year 2018, March Month,
    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2018 and and date.month_name="March" and (transactions.currency="INR\r" or transactions.currency="USD\r");

Using Power BI done Data Analysis
In Power Query Editor searched duplicate values, deleted null values, Data Transformed (from usd to inr)
Created Star Schema
Founded total Revenue
Total Sales Quantity
Total number of years (2017, 2018, 2019, 2020) and respected months
Revenue by market, in which state how much was the revenue
Sales Quantity by market, in which state sales was high
Top 10 Customers
Top 10 Products
Generated the Revenue Trend for the years 2017,2018,2019,2020

Then created a Power BI Interactive Dashboard for presenting all the above conditions

Formula to create column (from usd to inr)
`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] ="USD#)" then [sales_amount]*83.36 else [sales_amount], type any)`

