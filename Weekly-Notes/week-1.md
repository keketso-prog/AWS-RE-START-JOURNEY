WEEK 1

🌩️ What is AWS?

AWS stands for Amazon Web Services. It is a cloud computing platform made by Amazon.

That means instead of buying and managing your own computers (servers), you can rent computing power, storage, and tools from Amazon over the internet.

🕰️ Here is a Short History of AWS:

2002: Amazon started experimenting with web services.

2006: AWS officially launched with a few basic services:

S3 (for file storage)

EC2 (for virtual computers/servers)

SQS (for message queuing)

2010s: AWS grew fast — many startups and big companies started using it.

Today: AWS is one of the largest cloud providers in the world, along with Google Cloud and Microsoft Azure.

BELOW IS A TABLE AND EXPLANATION OF SOME OF THE SERVICES THEY OFFER:

Type of Service	Examples	Simple Meaning
💻 Compute	EC2, Lambda	Lets you run apps or websites on Amazon’s computers.
📦 Storage	S3, EBS	Keeps your files, photos, and backups safe online.
🗂️ Databases	RDS, DynamoDB	Stores your data so you can find and use it easily.
🌍 Networking	VPC, CloudFront, Route 53	Connects your apps to the internet safely and fast.
🧠 AI & Machine Learning	SageMaker, Rekognition	Helps make smart apps that can learn or see things (like face recognition).
🧰 Developer Tools	CodeBuild, CodeDeploy	Helps programmers build and update apps quickly.
🔐 Security & Identity	IAM, KMS	Keeps your information safe and controls who can access it.
📊 Analytics	Athena, Redshift	Helps you understand and study your data.
WHAT IS CLOUD COMPUTING?

Cloud computing is the delivery of computing services over the internet rather than using local servers or personal devices. Instead of owning and maintaining physical hardware, you rent computing resources from a provider on an as-needed basis.

THIS ARE THE CHARACTERISTICS OF CLOUD COMPUTING:

Resources accessed via the internet

Pay-as-you-go pricing model

Scalable (increase or decrease resources as needed)

No physical hardware maintenance required

THIS ARE SOME EXAMPLES OF AWS CLOUD COMPUTING SERVICES THEY OFFER:

EC2 (Elastic Compute Cloud) - Virtual servers in the cloud. You can launch different sized virtual machines with various operating systems to run your applications.

S3 (Simple Storage Service) - Object storage for files and data. You can store and retrieve any amount of data at any time.

RDS (Relational Database Service) - Managed database service that handles setup, patching, and backups automatically.

Lambda - Serverless computing where you run code without provisioning servers.

CloudFront - Content delivery network (CDN) that distributes your content globally.

VPC (Virtual Private Cloud) - Lets you create isolated virtual networks within AWS where you control IP addresses, subnets, and security settings.

AWS SHARED RESPONSIBILITY MODEL:

This defines who's responsible for what between AWS and you (the customer). A simple day-to-day example is like renting an apartment:

AWS is responsible for "Security OF the Cloud":

Physical security of data centers (guards, cameras, locks) Hardware and infrastructure (servers, storage, networking equipment) Virtualization layer that separates customers Maintaining the underlying services

You are responsible for "Security IN the Cloud":

Your data and content User access management (who can access what) Operating system patches and updates (for EC2 instances) Application security Firewall configurations Encryption settings

Simple analogy: AWS builds and maintains the building, elevators, and utilities. You're responsible for locking your apartment door, managing who has keys, and securing your belongings inside.

AWS PRICING MODEL IS AS FOLLOWS:

AWS uses a pay-as-you-go model. You only pay for what you use, with no upfront costs or long-term contracts (though you can get discounts with commitments).

Compute (EC2): Charged per second/hour the instance runs. Larger, more powerful instances cost more.

Storage (S3): Pay per GB stored per month, plus charges for data retrieval and transfers.

Data Transfer: Moving data OUT of AWS to the internet costs money. Data transferred IN is usually free. Data between AWS services in the same region is often free or cheap

📝 AWS Notes - Cloud Fundamentals 💰 Fundamentals of AWS Pricing Model What is AWS Pricing?

AWS = Amazon Web Services (cloud computing platform) Pay-as-you-go → Only pay for what you use (like electricity bill) No upfront costs or long-term contracts required

💵 3 Main Pricing Models:

Pay-as-you-go 💳

Pay only when you use services No minimum fees Stop paying when you stop using

Save when you reserve 🎟️

Commit to 1 or 3 years Get big discounts (up to 75%) Good for steady, predictable usage

Pay less by using more 📊

Volume discounts Use more = cheaper per unit Like buying in bulk at a store

🆓 Free Tier:

AWS gives free usage limits for 12 months Great for learning and testing Examples: 750 hours of EC2, 5GB storage

💡 What You Pay For:

Compute → Processing power (running programs) Storage → Saving data (like hard drive) Data Transfer → Moving data in/out of AWS Network → Internet bandwidth used

🎯 Cost Optimization Tips:

Turn off resources when not using Use right-sized instances (don't pay for more than you need) Monitor usage with AWS Cost Explorer Set billing alerts to avoid surprises

🖥️ Amazon EC2 (Elastic Compute Cloud) What is EC2?

Virtual computers in the cloud ☁️ Like renting a computer you can access from anywhere Can start/stop anytime Elastic = Can grow or shrink based on needs

🔑 Key Concepts: Instance → Your virtual server (like a computer)

Choose size (CPU, RAM, storage) Choose operating system (Linux, Windows, etc.)

Instance Types:

t2.micro → Small (free tier eligible) t2.medium → Medium power c5.large → High CPU for calculations r5.large → High RAM for memory-heavy tasks

📦 Components:

AMI (Amazon Machine Image) 📸

Template for your instance Pre-configured OS and software Like a blueprint for building a house

Instance Types 🎛️

Different sizes and capabilities General Purpose: Balanced (t2, t3) Compute Optimized: Fast processing (c5, c6) Memory Optimized: Lots of RAM (r5, r6) Storage Optimized: Fast disk access (i3, d2)

Security Groups 🔒

Virtual firewall Controls who can access your instance Set rules for incoming/outgoing traffic

Key Pairs 🔑

Used to login securely (SSH) Public key (AWS keeps) + Private key (you keep)

🚀 Launching an EC2 Instance:

Choose AMI (operating system) Choose instance type (size) Configure network settings Add storage Configure security group Create/select key pair Launch! 🎉

💰 EC2 Pricing Options:

On-Demand 💳

Pay by the hour/second No commitment Most flexible but most expensive

Reserved Instances 🎟️

1 or 3 year commitment Save up to 75% Good for steady workloads

Spot Instances 🎰

Bid on unused capacity Save up to 90% Can be interrupted (AWS takes it back) Good for flexible jobs

Savings Plans 💼

Commit to spending amount per hour Flexible on instance types Save up to 72%

⚙️ Important Features:

Elastic IP → Fixed IP address (doesn't change) Auto Scaling → Automatically add/remove instances based on demand Load Balancer → Distribute traffic across multiple instances EBS (Elastic Block Store) → Hard drive for your instance

📊 EC2 States:

Running 🟢 → Active (you pay) Stopped 🟡 → Turned off (only pay for storage) Terminated 🔴 → Deleted forever

☁️ Cloud Foundations What is Cloud Computing?

Using someone else's computers over the internet No need to buy physical servers Access from anywhere with internet

🌟 Benefits of Cloud:

No upfront costs 💰

Don't buy expensive hardware Pay only for what you use

Stop guessing capacity 🎯

Scale up when busy Scale down when quiet No wasted resources

Massive economies of scale 📈

AWS buys in bulk → passes savings to you Cheaper than doing it yourself

Speed and agility ⚡

Deploy in minutes, not months Experiment quickly Fail fast, learn fast

Global in minutes 🌍

Deploy apps worldwide Multiple regions (US, Europe, Asia, etc.) Low latency for users everywhere

Focus on business 🎯

AWS handles hardware/infrastructure You focus on building your app

☁️ Types of Cloud Services:

IaaS (Infrastructure as a Service) 🏗️

Basic building blocks You control OS, network, storage Example: EC2 Like renting land to build your house

PaaS (Platform as a Service) 🛠️

AWS manages OS, runtime You just deploy your code Example: Elastic Beanstalk Like renting a house, you just add furniture

SaaS (Software as a Service) 📱

Fully managed application You just use it Example: Gmail, Dropbox Like staying at a hotel with everything included

🌍 AWS Global Infrastructure: Regions 🗺️

Physical locations around the world Examples: us-east-1 (Virginia), eu-west-1 (Ireland) Choose region closest to your users

Availability Zones (AZ) 🏢

Data centers within a region Each region has multiple AZs (usually 3-6) Isolated from each other (for backup) Connected with high-speed networks

Edge Locations 📡

Cache content closer to users Faster delivery (CDN) Used by CloudFront

🔐 AWS Shared Responsibility Model: AWS Responsibility → Security OF the cloud

Physical security Hardware maintenance Network infrastructure Virtualization layer

Your Responsibility → Security IN the cloud

Data encryption Firewall rules User access Application security Operating system updates

Think of it like an apartment: 🏢

Landlord (AWS) secures building You secure your apartment

💡 Core AWS Services (Quick Overview): Compute 💻

EC2: Virtual servers Lambda: Run code without servers

Storage 💾

S3: Object storage (files, images) EBS: Hard drives for EC2

Database 🗄️

RDS: Managed databases (MySQL, PostgreSQL) DynamoDB: NoSQL database

Network 🌐

VPC: Private network Route 53: DNS service CloudFront: Content delivery (CDN)

Security 🔒

IAM: User access management Security Groups: Firewalls

📊 Well-Architected Framework (5 Pillars):

Operational Excellence ⚙️ → Run and monitor systems Security 🔐 → Protect data and systems Reliability 💪 → Recover from failures Performance Efficiency ⚡ → Use resources efficiently Cost Optimization 💰 → Avoid unnecessary costs

🎓 Quick Tips & Best Practices ✅ Start small → Use free tier to learn ✅ Set billing alarms → Avoid surprise costs ✅ Stop instances when not needed → Save money ✅ Use multiple AZs → High availability ✅ Tag everything → Organize and track costs ✅ Security first → Never share keys, use IAM roles ✅ Backup regularly → Use snapshots for EC2/EBS

🔥 Common Beginner Mistakes to Avoid ❌ Leaving instances running 24/7 (when you only need them 8 hours) ❌ Using wrong instance size (too big = waste money) ❌ Not setting billing alerts ❌ Storing access keys in code ❌ Not backing up data ❌ Using default security settings

🚀 Remember: Cloud is about flexibility and paying only for what you use. Start experimenting and learning! Practice makes perfect! About AWS: https://aws.amazon.com/about-aws/ What is AWS: https://aws.amazon.com/what-is-aws/ What is Cloud Computing: https://aws.amazon.com/what-is-cloud-computing/ AWS Global Infrastructure: https://aws.amazon.com/about-aws/global-infrastructure/ AWS History and Timeline: https://aws.amazon.com/about-aws/whats-new/
