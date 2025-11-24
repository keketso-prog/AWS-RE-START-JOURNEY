
## Week 6 Notes – SQL Basics

## Retrieving Data (SELECT)

The SELECT statement is your go-to for asking your database for information.

- Selecting specific columns:
sql
- SELECT name FROM customers;

This will show you just the name column from the customers table.

- Selecting multiple columns:
sql
- SELECT name, email FROM customers;

This retrieves both the name and email of every customer.

- Selecting everything:
sql
- SELECT * FROM customers;

This command displays all columns for all rows in the table.

- Filtering your results (WHERE):
sql
- SELECT name FROM customers WHERE age > 18;

This will give you the names of customers who are older than 18.

Extra examples:
sql
WHERE city = 'London';
WHERE age BETWEEN 18 AND 30;
WHERE email LIKE '%gmail.com';

These examples help you narrow down your results even further.

## Adding New Rows (INSERT)

INSERT is the command you use to add new data into a table.

Inserting a single row:
sql
INSERT INTO customers (name, email)
VALUES ('John', 'john@email.com');

This adds John to the customers table.

Inserting multiple rows at once:
sql
INSERT INTO customers (name, email)
VALUES 
('Sarah', 'sarah@email.com'),
('Mike', 'mike@email.com');

This adds both Sarah and Mike in one go, which is usually faster and tidier.

Tip:
Always include the column names when inserting data — it helps prevent errors if the table structure changes down the line.

## Using Functions (Math & Text)

SQL has built-in functions that allow you to calculate or format data easily.

Math / Aggregate Functions:
These functions work across multiple rows:
- COUNT() → gives you the number of rows
- SUM() → totals up a numeric column
- AVG() → calculates the average
- MAX() → finds the highest value
- MIN() → finds the lowest value

Example:
sql
SELECT COUNT(*) FROM orders;


Text Functions:
These are handy for cleaning or formatting text:
- UPPER(text) → converts to ALL CAPS
- LOWER(text) → converts to all lowercase
- CONCAT(a, b) → joins text together

Example:
sql
SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM users;

## Sorting & Grouping Results

Sorting lets you arrange your query results in a specific order, making it easier to analyze or read the data.

SELECT * FROM products
ORDER BY price ASC;
