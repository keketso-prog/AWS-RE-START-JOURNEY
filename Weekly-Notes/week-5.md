WEEK 5

AWS Databases

1. Database Basics
   
What is a Database? Think of it as a super-organized digital filing cabinet for your data.

Two Main Types:
Relational (SQL): Like a collection of perfectly organized Excel spreadsheets. Data is strict, structured in tables with rows and columns, and great for things like financial records where relationships are important.
Non-Relational (NoSQL): More like a collection of flexible documents or folders. Each document can have different information. It's great for things like user profiles or social media posts that don't all have the same fields.

Key Concepts:
Schema: The blueprint or rules for how your data is organized.
Primary Key: A unique ID for each record (like a student ID number).
Index: Like the index in the back of a book. It helps the database find information much faster.
3. Amazon Aurora (The "Fancy" Relational Database)
What it is: A high-performance version of popular databases (MySQL, PostgreSQL) that is built by AWS specifically for the cloud.

Key Selling Points:
Super Fast: Up to 5x faster than standard MySQL.
Super Reliable: Automatically backs up your data and can fix itself if something goes wrong.
Grows on its own: The storage space increases automatically as you need it.
Aurora Serverless: A version that automatically turns on/off and scales up/down. You only pay for what you use. Perfect for apps that aren't always busy.

4. Amazon DynamoDB (The "Powerful" NoSQL Database)
What it is: AWS's super-fast, super-scalable NoSQL database.
Key Selling Points:
Blazing Fast: Can handle millions of requests per second with very little delay.
Fully Managed: AWS handles all the technical maintenance. You don't have to worry about servers.
Scales Automatically: Grows to handle almost any amount of traffic or data without you needing to do anything.
How it Works (Simplified):
You store data in Tables (like a filing cabinet), which contain Items (like folders), which are made of Attributes (the individual pieces of data).
Everything is identified by a Primary Key.
Capacity Modes:
On-Demand: Pay-per-request. Great for new apps or apps with unpredictable traffic.
Provisioned: You set the capacity you need. Can be cheaper if your traffic is steady and predictable.
5. How to Choose a Database
Ask yourself these questions:

Is your data structured like tables? → Use a Relational DB (Aurora).
Do you need massive scale and flexibility? → Use a NoSQL DB (DynamoDB).
Need to do complex queries and joins between tables? → Aurora.
Need super-fast lookups for simple data (like a product ID)? → DynamoDB.
Is your workload unpredictable (busy one minute, quiet the next)? → Aurora Serverless or DynamoDB On-Demand.
5. Getting Data In & Out
For Relational (SQL) like Aurora:
Getting Data: Use the SELECT command. Use WHERE to filter (e.g., WHERE country = 'USA') and JOIN to combine data from different tables.
Putting Data In: Use the INSERT command to add new rows to a table.
For NoSQL (DynamoDB):
Getting Data: You typically query by a specific key or look for items with certain attributes. It's simpler than SQL but less flexible for complex relationships.
Putting Data In: Use PutItem to add one item, or BatchWriteItem to add up to 25 items at once for better efficiency.
