## Sales Insights Data Analysis Project

<br>This project is based on a computer hardware business which is facing challenges in dynamically changing market. Sales director decides to invest in data analysis project and he would like to build power BI dashboard that can give him real time sales insights. 

<br> Once sales directory of atliQ hardware has decided to invest in data analysis project he will do a meeting with IT director, data analytics team to come up with a plan. They will use AIMS grid to define purpose and success criteria of this project.

<br> After that, we will look at mysql database that is owned by falcons team. This database has all sales transactions, customers, products and markets information. We will analyse this database and than hook it up with power BI. In power BI we will perform ETL and data cleaning operations to make it ready so that we can build our dashboard.

<br> Then we will plug mysql database with power BI. In power BI we will do data cleaning and ETL (Extract, transform , load). This process is also known as data munging or data wrangling. We will do currency normalization, handling invalid values etc.


### Instructions to setup mysql on your local computer

1. Follow step in this video to install mysql on your local computer
https://www.youtube.com/watch?v=WuBcTJnIuzo

1. SQL database dump is in db_dump.sql file above. Download `db_dump.sql` file to your local computer and import it as per instructions given in the tutorial video

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




