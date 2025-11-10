AWS and Cloud Computing 

What is Cloud Computing?

Think of cloud computing like renting instead of buying. Instead of buying your own computer servers and keeping them in your office, you rent computing power from someone else over the internet.
Real-life example: It's like using Netflix instead of buying DVDs. You don't own the movies, but you can watch whatever you want, whenever you want, and only pay for what you use.

Why people use it:

No need to buy expensive equipment
Pay only for what you use
Access your stuff from anywhere
Someone else handles maintenance and updates

What is AWS?
AWS stands for Amazon Web Services. It's Amazon's cloud computing platform - basically, Amazon renting out their massive computer infrastructure to businesses and individuals.
Think of it like this: Amazon built huge data centers for their own online store. Then they realized, "Hey, we have extra space and power. Why not rent it out?" Now AWS is one of the biggest cloud providers in the world.
AWS Infrastructure
AWS infrastructure is how Amazon organizes all their computers and data centers around the world.
Key Parts:
Regions - Geographic locations around the world where AWS has data centers

Example: US East (Virginia), Europe (Ireland), Asia Pacific (Singapore)
Why it matters: You can choose to store your data close to your customers for faster access

Availability Zones (AZs) - Multiple data centers within each region

Each region has 2-6 availability zones
If one goes down, your app keeps running on another
Think of it like having backup generators

Edge Locations - Smaller sites that deliver content faster

Like having mini-warehouses closer to customers
Makes websites and apps load quicker

AWS Services and How They're Used
Here are the main services explained simply:
1. EC2 (Elastic Compute Cloud)
What it is: Virtual computers you can rent
How it's used:

Running a website or app
Processing large amounts of data
Testing new software

Real example: A startup rents an EC2 server to host their new mobile app instead of buying their own server.
2. S3 (Simple Storage Service)
What it is: Online storage for files
How it's used:

Storing photos, videos, backups
Hosting website images
Archiving old documents

Real example: A photographer stores all their client photos on S3 instead of external hard drives.
3. RDS (Relational Database Service)
What it is: Managed databases for storing organized data
How it's used:

Storing customer information
Managing product catalogs
Keeping track of orders

Real example: An online store uses RDS to keep track of all their products, prices, and customer orders.
4. Lambda
What it is: Run code without managing servers
How it's used:

Automatically resizing images when uploaded
Processing payments
Sending automated emails

Real example: When you upload a profile picture, Lambda automatically creates thumbnail versions without needing a full server.
5. CloudFront
What it is: Content delivery network (makes websites faster)
How it's used:

Speeding up website loading
Delivering videos smoothly
Reducing server load

Real example: A news website uses CloudFront so readers in Japan load pages as fast as readers in New York.
6. IAM (Identity and Access Management)
What it is: Controls who can access what
How it's used:

Creating user accounts
Setting permissions (who can see/edit what)
Security management

Real example: A company gives developers access to test servers but not production servers.
7. VPC (Virtual Private Cloud)
What it is: Your own private section of AWS
How it's used:

Creating secure, isolated networks
Connecting to your office network
Controlling traffic flow

Real example: A hospital creates a VPC to keep patient data completely separate and secure from other AWS users.
8. Route 53
What it is: Domain name service (connects website names to servers)
How it's used:

Managing domain names
Routing traffic to the right servers
Health checking websites

Real example: When someone types "mywebsite.com," Route 53 directs them to the right server.
9. EBS (Elastic Block Store)
What it is: Hard drives for your virtual computers
How it's used:

Adding storage to EC2 instances
Creating backups
Running databases

Real example: Like adding an external hard drive to your computer, but in the cloud.
10. CloudWatch
What it is: Monitoring and alerts
How it's used:

Tracking server performance
Setting up alerts when things go wrong
Viewing logs and metrics

Real example: Get an email alert if your website goes down or starts running slowly.
Quick Summary
Cloud Computing = Renting computing power instead of buying it
AWS = Amazon's cloud platform (one of the biggest)
Infrastructure = How AWS organizes data centers globally (Regions, Availability Zones, Edge Locations)
Services = Different tools for different jobs:

EC2 = Virtual computers
S3 = File storage

LINKS FOR MORE INFOMATION

https://aws.amazon.com/education/awseducate
https://workshops.aws
 https://docs.aws.amazon.com
RDS = Databases
Lambda = Run code automatically
