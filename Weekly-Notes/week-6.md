WEEK 6

 Getting Data from Your Database (SELECT)
This is how you ask the database to show you information.

To get specific columns: Tell it exactly what you want to see.
SELECT name FROM customers;
Translation: "Show me just the name column from the customers table."
To get multiple columns: Just list them out.
SELECT name, email FROM customers;
Translation: "Show me the name and email for all customers."
To get everything: Use the * wildcard.
SELECT * FROM customers;
Translation: "Show me all columns for all customers."
To filter your results: Use WHERE to add rules.
SELECT name FROM customers WHERE age > 18;
Translation: "Show me the names of customers who are older than 18."
2. Adding New Information (INSERT)
This is how you add a new row of data to a table.

To add one new row:
INSERT INTO customers (name, email) VALUES ('John', 'john@email.com');
Translation: "Add a new customer with the name 'John' and email 'john@email.com'."
To add multiple rows at once (more efficient):
INSERT INTO customers (name, email) VALUES ('Sarah', 'sarah@email.com'), ('Mike', 'mike@email.com');
Translation: "Add two new customers, Sarah and Mike, in one go."
3. Doing Calculations & Changing Text (Functions)
Functions are built-in tools that perform actions on your data.

Math Functions (work on many rows at once):
COUNT() - Counts how many rows there are.
SUM() - Adds up all the numbers in a column.
AVG() - Calculates the average.
MAX() - Finds the highest value.
MIN() - Finds the lowest value.
Text Functions (change how text looks):
UPPER() - Converts text to ALL CAPS.
LOWER() - Converts text to all lowercase.
CONCAT() - Joins text together.
4. Sorting and Grouping Your Results
This is how you organize the data you get back to make it more useful.

Sorting (ORDER BY): Arrange your results in a specific order.
SELECT * FROM products ORDER BY price ASC;
Translation: "Show me all products, sorted by price from lowest to highest."
(Use DESC for highest to lowest).
Grouping (GROUP BY): Puts similar data into buckets.
SELECT category, COUNT(*) FROM products GROUP BY category;
Translation: "Show me each product category and count how many products are in each one."
Removing Duplicates (DISTINCT): Shows only unique values.

SELECT DISTINCT city FROM customers;
Translation: "Show me a list of all the unique cities where my customers live."
Filtering Groups (HAVING): Like WHERE, but for groups created by GROUP BY.
SELECT category, COUNT(*) FROM products GROUP BY category HAVING COUNT(*) > 5;
Translation: "Show me only the product categories that have more than 5 items in them."

Quick Tips
Always end your SQL commands with a semicolon (;).
You don't have to type SQL keywords in all caps (SELECT, WHERE), but it's a common tradition that makes your code easier to read.
Test your commands on a small amount of data first if you can.
Always back up your database before making big changes!
AWS Resources for Learning More
Amazon RDS: AWS's service for traditional SQL databases.
Getting Started Guide
Amazon Aurora: A high-performance, AWS-built database compatible with MySQL and PostgreSQL.

User Guide
Amazon DynamoDB: AWS's popular fast and flexible NoSQL database.
Getting Started Guide
AWS Database Blog: For news, tips, and stories from AWS experts.
Visit the Blog
AWS Training & Tutorials: Official places to learn more.
AWS Training Portal
AWS Skill Builder
