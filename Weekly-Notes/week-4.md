WEEK 4

AWS Security & Networking: Simple Notes

1. Core Data Security Ideas
Defense in Depth: Don't just have one lock on your door. Use multiple layers of security (like a firewall, encryption, and access control) to protect your data.
Shared Responsibility Model: This is a team effort.
AWS's Job: Protects the physical buildings, servers, and network that make up the cloud.
Your Job: Secure your own data, applications, and who you give access to, within AWS.
Know Your Data: Figure out which of your data is sensitive (like customer credit cards) and handle it with extra care.
2. Protecting Data with Encryption (Scrambling it)
Encryption is like putting your data in a locked safe. You need a key to unlock and read it.

At Rest: Encrypting data that is just sitting on a disk (like files in S3 or on a virtual hard drive).
In Transit: Encrypting data as it's moving across the internet (like when you visit a secure website - the https and padlock icon).
Client-Side: You encrypt the data on your own computer before sending it to AWS.
Key AWS Tools:

AWS KMS (Key Management Service): A service from AWS that helps you create and manage the encryption keys.
S3/EBS Encryption: You can easily tell AWS to automatically encrypt the data you store in these services.
3. Controlling Access with IAM (Identity and Access Management)
IAM is how you control who can do what in your AWS account.

Users: A person who has a login and password.
Groups: A way to organize users (e.g., a "Developers" group or an "Admins" group) to give them all the same permissions at once.
Roles: Like a temporary security pass. You give a role to an application or AWS service so it can perform a specific task, without giving it a permanent user account.
Policies: These are the rulebooks (written in code) that define exactly what someone is or isn't allowed to do.
Best Practices:

Principle of Least Privilege: Only give people the minimum permissions they need to do their job. Don't give a developer access to billing information.
Use MFA (Multi-Factor Authentication): Add a second layer of security (like a code from your phone) to all important accounts, especially the main "root" account.
Use Roles, Not Keys: Whenever possible, use temporary roles instead of long-lasting access keys for applications.
4. Compliance & Rules (AWS is Certified)
AWS follows a lot of industry rules and standards, which makes it easier for you to comply too.

Examples: PCI DSS (for credit cards), HIPAA (for healthcare), GDPR (for European data).
AWS Artifact: A place where you can download official reports from AWS to prove they are following these rules.
5. Tracking Everything with AWS CloudTrail
What it is: Think of CloudTrail as a security camera for your AWS account. It logs every single action that anyone takes.
Why it's useful:
Security: See who did what and when. Perfect for investigating security incidents.
Troubleshooting: Figure out why something broke by looking at the past actions.
Compliance: Prove you are monitoring your account.
6. Monitoring Your Virtual Server (EC2)
You need to keep an eye on your server's health.

AWS CloudWatch: The main tool for this. It collects metrics (data points) from your EC2 instance.
Key things to watch:
CPU Utilization: How hard the processor is working.
Network Traffic: How much data is flowing in and out.
Disk Activity: How much your hard drive is being read from or written to.
Alarms: You can set up CloudWatch to automatically notify you if something goes wrong (e.g., "alert me if the CPU is over 90% for 5 minutes").
7. Network Security (Hardening Your VPC)
Your VPC (Virtual Private Cloud) is your own isolated section of the AWS cloud.

Security Groups: A firewall for your specific server (like an EC2 instance). It controls what traffic is allowed to reach it. It's "stateful," meaning if you allow traffic in, it automatically remembers to allow the reply traffic out.
Network ACLs (Access Control Lists): A firewall for your entire network subnet. It's an extra layer of security. It's "stateless," meaning you have to explicitly create rules for traffic in and traffic out.
Private Subnets: Keep your most important resources (like databases) in a private subnet, so they cannot be accessed directly from the internet.
VPC Flow Logs: Capture information about the IP traffic going to and from network interfaces in your VPC. Great for security analysis.
8. Choosing the Right Data Type for Numbers
When you create a database, you need to tell it what kind of numbers to expect.

Integers (INT, BIGINT): For whole numbers (like 1, 150, -50). Perfect for user IDs or counters.
Decimals (DECIMAL, NUMERIC): For exact numbers, like money. Use this to avoid rounding errors.
Floating Point (FLOAT, DOUBLE): For numbers with fractions where a tiny bit of rounding is okay (like scientific measurements).
Best Practice: Always use the smallest data type that will fit your needs. It saves storage space and can make your database faster.
