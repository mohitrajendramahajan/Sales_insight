## Sales Insights Data Analysis Project

### Instructions to setup mysql on your local computer

1. Download `db_dump.sql` file to your local computer and import it to the Power BI application.

### Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`


Data Analysis Using Power BI
============================

1. Formula to create norm_amount column

`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`

HERE ARE SOME REVIEW PHOTOS FOR THE DASHBOARD:
1. Total sales qty and amount Sumary<br><br>

![image](https://github.com/mohitrajendramahajan/Sales_insight/assets/103811474/876d6835-b96a-4126-90d4-574fd6bcc2c2)
2. Sales by market<br>

![image](https://github.com/mohitrajendramahajan/Hotel-Management-System/assets/103811474/7b0fa2d6-c74d-4038-acae-7c5861d9d492)
3. Zones by market<br>

![image](https://github.com/mohitrajendramahajan/Hotel-Management-System/assets/103811474/968acc11-aa71-4ec9-bb23-a18ed12640af)
