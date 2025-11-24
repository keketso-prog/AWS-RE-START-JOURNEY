## WEEK 5

## AWS Databases

## Database Basics

- What is a Database? Think of it as a super-organized digital filing cabinet for your data.
  
Two Main Types: Relational (SQL): Like a collection of perfectly organized Excel spreadsheets. Data is strict, structured in tables with rows and columns, and great for things like financial records where relationships are important.

 - Non-Relational (NoSQL): More like a collection of flexible documents or folders. Each document can have different information. It's great for things like user profiles or social media posts that don't all have the same fields.

- Key Concepts: Schema: The blueprint or rules for how your data is organized. -
- Primary Key: A unique ID for each record (like a student ID number).
- Index: Like the index in the back of a book. It helps the database find information much faster.
-  Amazon Aurora (The "Fancy" Relational Database) What it is: A high-performance version of popular databases (MySQL, PostgreSQL) that is built by AWS specifically for the cloud.

Key Selling Points: 
-Super Fast: Up to 5x faster than standard MySQL. 
-Super Reliable: Automatically backs up your data and can fix itself if something goes wrong.
-Grows on its own: The storage space increases automatically as you need it. 
-Aurora Serverless: A version that automatically turns on/off and scales up/down. 
-You only pay for what you use. Perfect for apps that aren't always busy.

Amazon DynamoDB (The "Powerful" NoSQL Database) What it is: AWS's super-fast, super-scalable NoSQL database. Key Selling Points: Blazing Fast: Can handle millions of requests per second with very little delay. Fully Managed: AWS handles all the technical maintenance. You don't have to worry about servers. Scales Automatically: Grows to handle almost any amount of traffic or data without you needing to do anything. How it Works (Simplified): You store data in Tables (like a filing cabinet), which contain Items (like folders), which are made of Attributes (the individual pieces of data). Everything is identified by a Primary Key.

## Capacity Modes:
On-Demand: This is a pay-per-request model, perfect for new applications or those with unpredictable traffic patterns.
Provisioned: Here, you determine the capacity you need. It can be more cost-effective if your traffic is steady and predictable.

##  How to Choose a Database
Consider these questions:

- Is your data organized like tables? → Go for a Relational DB (like Aurora).
- Do you require massive scalability and flexibility? → Opt for a NoSQL DB (like DynamoDB).
- Need to perform complex queries and join tables? → Choose Aurora.
- Looking for lightning-fast lookups for simple data (like a product ID)? → DynamoDB is your best bet.
- Is your workload unpredictable (busy one moment, quiet the next)? → Consider Aurora Serverless or DynamoDB On-Demand.

## Getting Data In & Out
- For Relational (SQL) databases like Aurora:
Getting Data: Use the SELECT command. You can filter results with WHERE (e.g., WHERE country = 'USA') and combine data from different tables using JOIN.
Inserting Data: Use the INSERT command to add new rows to your table.

- For NoSQL (DynamoDB):
Getting Data: You usually query by a specific key or search for items with certain attributes. It’s simpler than SQL but offers less flexibility for complex relationships.
Inserting Data: Use PutItem to add a single item, or BatchWriteItem to add up to 25 items at once for better efficiency.


