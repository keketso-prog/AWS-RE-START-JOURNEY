# Database Operations - Study Notes

## 1. Selecting Data

Selecting data means choosing which information you want to see from a database. You use the SELECT statement to do this.

**Basic syntax:**
```
SELECT column_name FROM table_name;
```

**Examples:**
- Get all customer names: SELECT name FROM customers;
- Get multiple columns: SELECT name, email FROM customers;
- Get everything: SELECT * FROM customers;

You can also filter results using WHERE:
```
SELECT name FROM customers WHERE age > 18;
```

---

## 2. Inserting Data into a Database

Inserting means adding new information to your database. You use the INSERT INTO statement.

**Basic syntax:**
```
INSERT INTO table_name (column1, column2) VALUES (value1, value2);
```

**Examples:**
- Add one customer: 
  ```
  INSERT INTO customers (name, email) VALUES ('John', 'john@email.com');
  ```
- Add multiple rows at once:
  ```
  INSERT INTO customers (name, email) 
  VALUES ('Sarah', 'sarah@email.com'), ('Mike', 'mike@email.com');
  ```

---

## 3. Working with Functions

Functions help you perform calculations or modify data. There are two main types:

**Aggregate Functions** (work on multiple rows):
- COUNT() - counts rows
- SUM() - adds numbers together
- AVG() - calculates average
- MAX() - finds highest value
- MIN() - finds lowest value

**Examples:**
- SELECT COUNT(*) FROM customers; (counts all customers)
- SELECT AVG(price) FROM products; (gets average price)

**String Functions:**
- UPPER() - converts to uppercase
- LOWER() - converts to lowercase
- CONCAT() - joins text together

---

## 4. Retrieving Data

Retrieving data means getting information back from the database in useful ways.

**Common techniques:**

**Using WHERE to filter:**
```
SELECT * FROM products WHERE price < 50;
```

**Using LIKE for pattern matching:**
```
SELECT * FROM customers WHERE name LIKE 'A%';
```
(This finds names starting with 'A')

**Using LIMIT to control how many results:**
```
SELECT * FROM products LIMIT 10;
```

**Joining tables together:**
```
SELECT customers.name, orders.total 
FROM customers 
JOIN orders ON customers.id = orders.customer_id;
```

---

## 5. Organizing Data

Organizing helps you present data in a clear, useful order.

**Sorting with ORDER BY:**
```
SELECT * FROM products ORDER BY price ASC;
```
- ASC = ascending (low to high)
- DESC = descending (high to low)

**Grouping with GROUP BY:**
Groups similar data together, often used with aggregate functions.
```
SELECT category, COUNT(*) FROM products GROUP BY category;
```

**Removing duplicates with DISTINCT:**
```
SELECT DISTINCT city FROM customers;
```

**Filtering groups with HAVING:**
Used with GROUP BY to filter grouped results.
```
SELECT category, COUNT(*) FROM products 
GROUP BY category 
HAVING COUNT(*) > 5;
```

---

## Quick Tips:
- Always end SQL statements with a semicolon (;)
- SQL keywords are not case-sensitive, but it's common to write them in UPPERCASE
- Test your queries on small datasets first
- Always back up your database before making changes

---

## AWS Resources for Additional Learning:

**Amazon RDS (Relational Database Service):**
- Getting Started: https://docs.aws.amazon.com/rds/latest/userguide/CHAP_GettingStarted.html
- RDS Database Instances: https://docs.aws.amazon.com/rds/latest/userguide/Overview.DBInstance.html

**Amazon Aurora:**
- Aurora User Guide: https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/

**Amazon DynamoDB (NoSQL):**
- Getting Started: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/GettingStartedDynamoDB.html

**AWS Database Blog:**
- https://aws.amazon.com/blogs/database/

**SQL Basics Tutorial:**
- AWS Training: https://aws.amazon.com/training/
- AWS Skill Builder: https://skillbuilder.aws/

**General AWS Database Documentation:**
- https://docs.aws.amazon.com/index.html#databases
