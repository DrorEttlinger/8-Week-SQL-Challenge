# 8-Week-SQL-Challenge

🍜 Case Study #1: Danny's Diner

Entity Relationship Diagram
![image](https://github.com/DrorEttlinger/8-Week-SQL-Challenge/assets/82260552/c3c5d0d3-2d44-4ff2-a103-004de5f8edf9)

1. What is the total amount each customer spent at the restaurant?
```sql
SELECT sales.customer_id,sum(menu.price) AS Total_amount
FROM dannys_diner.sales
JOIN dannys_diner.menu
ON sales.product_id = menu.product_id
GROUP BY sales.customer_id
ORDER BY sales.customer_id ASC;
```
2. How many days has each customer visited the restaurant?
```sql
SELECT customer_id,count(DISTINCT order_date) AS days_visited
FROM dannys_diner.sales
GROUP BY customer_id
```
