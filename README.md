# Tableau_dashboard
Dealing with Atliq's hardware data insights.....

Hey connections....
The purpose of this project to unlock the sales insights that are not visible before sales team.
As we know a "Picture is far better than thousands of word" so making of dashboards came into exist.

As we got a raw data that contained tables like customers,date,market,products,transactions.
We performed SQL queries to review data and make links amoung those table and export it to 'Tableau'.

Sql queries:

# date column
select * from sales.date; 
# transactions column
select * from sales.transactions;
# market column
select * from sales.market; 
# products column
select * from sales.products;
# customers column
select * from sales.customers;
# Inner join on transaction and date table
SELECT sales.transactions.* , sales.date.* FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date = sales.date.date where sales.date.year=2020;
# total revenue in year 2020
select sum(sales.transactions.sales_amount) from sales.transactions inner join sales.date on sales.transactions.order_date = sales.date.date where sales.date.year=2020;
# total revenue generated in chennai and for chennai market code is 'Mark001'
select sum(sales.transactions.sales_amount) from sales.transactions inner join sales.date 
on sales.transactions.order_date = sales.date.date 
where sales.date.year=2020 and sales.transactions.market_code="Mark001";   # Answer is 2463024

Insights:
1). Total quantity sold across the county: 10.25k
2). Total revenue generated across the country:10.85M (Rs)
3). Top customer of firm -> Electricalsara stores: 2.36M (Rs)
4). Top market region on the basis of revenue generated : Mumbai (6.55M (Rs)
5). Peak days for firm : July 2018

