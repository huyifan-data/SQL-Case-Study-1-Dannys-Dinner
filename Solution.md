# 🍜 Case Study #1: Danny's Diner

# Solutions 
### 1. What is the total amount each customer spent at the restaurant?

```sql
SELECT customer_id, SUM(price) AS total_amount
FROM dannys_diner.sales s
JOIN dannys_diner.menu m ON m.product_id = s.product_id
GROUP BY customer_id
ORDER BY customer_id;
```

| customer_id    | total_amount       |
| ----------------- | ------------------------------------------------------------------ |
| A | 76 |
| B | 74 |
| C | 36 |

### 2. How many days has each customer visited the restaurant?
```sql
SELECT customer_id, COUNT(DISTINCT order_date) AS visit_count
FROM sales
GROUP BY customer_id
ORDER BY customer_id;
```
| customer_id            | visit_count                                                           |
| ----------------- | ------------------------------------------------------------------ |
| A | 4 |
| B | 6 |
| C | 2 |
