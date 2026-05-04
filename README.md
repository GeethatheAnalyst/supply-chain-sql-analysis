# Supply Chain Data Analysis — SQL

This project was part of my SQL training. I was given a relational supply chain database and a set of business questions to answer using pure SQL — no Python, no Excel, just queries. It pushed me to get comfortable with joins across multiple tables, window functions, and writing queries that actually answer real business questions.

---

## The database

The supply chain database has 5 tables:
- `Customer` — customer details including city and country
- `Orders` — order dates and total amounts
- `OrderItem` — individual products within each order
- `Product` — product names, prices, and supplier info
- `Supplier` — supplier company details and locations

---

## Questions I answered

1. What is the earliest and latest order date in the system?
2. Month-wise and year-wise count of orders placed
3. Which customers never placed an order? *(LEFT JOIN + NULL filter)*
4. Top products by demand in 2021
5. Which customer placed the single largest order? *(solved two ways — subquery and GROUP BY)*
6. Top 5 customers by total spend
7. Top 3 suppliers by revenue generated *(solved two ways — LIMIT and RANK() window function)*
8. Combined customer and supplier contact list using UNION ALL
9. Customers who ordered more than 10 different products in a single order
10. Total discount savings per order — ordered highest to lowest
11. Suppliers with no customers in their country
12. Products that UK customers buy but are supplied by other countries

---

## A few things I learned from this

Writing Q7 two different ways (once with `LIMIT` and once with `RANK()`) was useful — the window function approach is more flexible if you need to handle ties. Q12 was the trickiest one conceptually: figuring out which products UK customers depend on from foreign suppliers needed 5-table joins.

---

## Tools used

- MySQL
- Joins (INNER, LEFT)
- Aggregate functions (SUM, COUNT, MAX, MIN)
- GROUP BY, HAVING, ORDER BY
- Subqueries
- RANK() window function
- UNION ALL

---

## Files in this repo

- <a href="https://github.com/GeethatheAnalyst/supply-chain-sql-analysis/blob/main/Supply%20chain%20SQL%20Project.sql">Main project file</a> — all 12 queries with answers and comments
- <a href="https://github.com/GeethatheAnalyst/supply-chain-sql-analysis/blob/main/Supply%20chain.sql">DDL file</a> — creates all 5 tables (Customer, Orders, OrderItem, Product, Supplier) with indexes 
- <a href="https://github.com/GeethatheAnalyst/supply-chain-sql-analysis/blob/main/Supply%20chain%20Data%20Constraints%20.sql">Foreign key constraints</a> — defines relationships between all tables 
- <a href="https://github.com/GeethatheAnalyst/supply-chain-sql-analysis/blob/main/Supply%20chain%20data.sql">Data file</a> — inserts all records into the database

> To run this project locally: execute `Supply chain.sql` first to create the schema, then `Supply chain Data Constraints.sql` to set up relationships, then `Supply chain data.sql` to load the data. Once that's done, open `Supply chain SQL Project.sql` to run the queries.
---

## Dataset

Supply chain relational database provided as part of coursework at RRC Technologies, Thanjavur.
