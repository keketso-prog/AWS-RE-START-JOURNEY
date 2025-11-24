## WEEK 4

## Core Data Security Ideas
Defense in Depth: Think of security like a door with multiple locks. Instead of relying on just one, layer your defenses with things like firewalls, encryption, and access controls to keep your data safe.
Shared Responsibility Model: Remember, this is a team effort.
AWS's Role: They take care of the physical buildings, servers, and networks that form the cloud.
Your Role: It's up to you to secure your data, applications, and manage who gets access within AWS.
Know Your Data: Identify which pieces of your data are sensitive—like customer credit card information—and treat them with extra caution.
Protecting Data with Encryption (Scrambling it):
Encryption is like stashing your data in a locked safe; you need a key to unlock and read it.

At Rest: This means encrypting data that’s just sitting on a disk, like files in S3 or on a virtual hard drive.
In Transit: This involves encrypting data while it’s traveling across the internet, such as when you visit a secure website (look for the https and padlock icon).
Client-Side: Here, you encrypt the data on your own computer before sending it to AWS.

## Key AWS Tools:
AWS KMS (Key Management Service): This AWS service helps you create and manage your encryption keys.
S3/EBS Encryption: You can easily set AWS to automatically encrypt the data you store in these services.

## Controlling Access with IAM (Identity and Access Management)
IAM is your go-to tool for managing who can do what in your AWS account.

Users: These are the individuals who have their own login and password.
Groups: Think of these as collections of users (like a "Developers" group or an "Admins" group) that you can manage together by assigning them the same permissions.
Roles: These act like temporary security badges. You assign a role to an application or AWS service so it can carry out a specific task without needing a permanent user account.
Policies: These are the guidelines (written in code) that clearly outline what actions someone can or cannot take.
Best Practices:

Principle of Least Privilege: Always give people the bare minimum permissions they need to get their job done. For instance, don’t grant a developer access to billing info.
Use MFA (Multi-Factor Authentication): Add an extra layer of security (like a code sent to your phone) to all critical accounts, especially the main "root" account.
Use Roles, Not Keys: Whenever you can, opt for temporary roles instead of long-lasting access keys for applications.

## Compliance & Rules (AWS is Certified)
AWS adheres to numerous industry regulations and standards, making it easier for you to stay compliant as well.

Examples: PCI DSS (for credit card transactions), HIPAA (for healthcare), GDPR (for data protection in Europe).
AWS Artifact: This is your go-to spot for downloading official reports from AWS that demonstrate their compliance with these regulations.

## Tracking Everything with AWS CloudTrail
What it is: Picture CloudTrail as a security camera for your AWS account. It records every action taken by anyone.
Why it's useful:
Security: You can see who did what and when, which is invaluable for investigating security incidents.
Troubleshooting: If something goes wrong, you can trace back to see what happened.
Compliance: It helps you prove that you’re actively monitoring your account.

## Monitoring Your Virtual Server (EC2)
Keeping tabs on your server's health is crucial.

AWS CloudWatch: This is your primary tool for monitoring. It gathers metrics (data points) from your EC2 instance.
Key things to keep an eye on:
CPU Utilization: This shows how hard the processor is working.
Network Traffic: This indicates how much data is being transferred.

## Network Security (Hardening Your VPC)
Your VPC (Virtual Private Cloud) is like your own little corner of the AWS cloud, completely isolated from the rest.

**Security Groups:** Think of these as a firewall specifically for your server, such as an EC2 instance. They determine what traffic can get through. Since they're "stateful," if you let traffic in, they automatically remember to allow the outgoing replies.

**Network ACLs (Access Control Lists):** This acts as a firewall for your entire network subnet, adding an extra layer of security. Unlike security groups, they're "stateless," meaning you need to set up rules for both incoming and outgoing traffic.

**Private Subnets:** It's a good idea to keep your most sensitive resources, like databases, in a private subnet. This way, they can't be accessed directly from the internet.

**VPC Flow Logs:** These logs capture details about the IP traffic going to and from the network interfaces in your VPC. They're incredibly useful for security analysis.

## Choosing the Right Data Type for Numbers
When setting up a database, it's crucial to specify what kind of numbers you'll be working with.

**Integers (INT, BIGINT):** Use these for whole numbers, like 1, 150, or -50. They're ideal for things like user IDs or counters.

**Decimals (DECIMAL, NUMERIC):** These are perfect for precise numbers, such as currency, helping you avoid any rounding errors.

**Floating Point (FLOAT, DOUBLE):** These types are suitable for numbers that include fractions, where a little rounding is acceptable, like in scientific measurements.

**Best Practice:** Always opt for the smallest data type that meets your needs. This not only saves storage space but can also speed up your database performance.
