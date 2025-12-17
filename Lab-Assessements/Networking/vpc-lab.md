# Create Subnets and Allocate IP addresses in an Amazon Virtual Private Cloud (Amazon VPC)

<img width="951" height="621" alt="Screenshot (1535)" src="https://github.com/user-attachments/assets/48d29e21-7ff9-4b83-b6b0-42c48703af10" />

I worked through a hands-on lab with Amazon VPC, learning how to design and create a virtual private cloud to meet a customer's networking requirements. 

- Here's what I did.

# Task 1: Investigating the Customer's Needs
I started by understanding the customer scenario and their specific networking requirements. Then I navigated to the AWS Management Console, searched for "VPC," and launched the VPC Wizard to begin creating the network infrastructure.
# Configuring the VPC
I configured the VPC with the following settings:

- IPv6 CIDR block: Left as "No IPv6 CIDR Block" since IPv6 wasn't required for this lab
- VPC name: Entered "First VPC"
- Public subnet's IPv4 CIDR: Configured the CIDR block to be smaller than the VPC CIDR while ensuring it could accommodate at least 50 IP addresses
- Availability Zone: Selected "No Preference"
- Subnet name: Left as "Public subnet"
- Left all remaining options at their default settings

I then clicked "Create VPC" to build the network infrastructure.

<img width="1581" height="748" alt="Screenshot (1537)" src="https://github.com/user-attachments/assets/997b15d2-3e2d-4795-a4ad-07ed25d5136b" />
<img width="1552" height="754" alt="Screenshot (1538)" src="https://github.com/user-attachments/assets/020f46f3-df4e-476e-97b9-43bef8c4ea25" />
<img width="1556" height="754" alt="Screenshot (1539)" src="https://github.com/user-attachments/assets/d587a0d5-e2ea-427e-9a23-667723035a5b" />
<img width="1524" height="754" alt="Screenshot (1540)" src="https://github.com/user-attachments/assets/fcf1b5fa-c4fd-484e-923a-18b32eb754f3" />
<img width="1568" height="752" alt="Screenshot (1541)" src="https://github.com/user-attachments/assets/58674793-fde1-45dc-bece-5a51016e3365" />
<img width="1576" height="752" alt="Screenshot (1542)" src="https://github.com/user-attachments/assets/8f815cd7-eef8-4ef7-a3ef-9b8ea944b972" />
<img width="1578" height="755" alt="Screenshot (1543)" src="https://github.com/user-attachments/assets/57177b40-fc00-4c27-b423-f97ce85aa652" />

# Task 2

<img width="1590" height="819" alt="Screenshot (1974)" src="https://github.com/user-attachments/assets/7138ec73-12ee-492c-a922-6289ccdfd692" />

<img width="1600" height="816" alt="Screenshot (1975)" src="https://github.com/user-attachments/assets/462c0962-4565-4ebd-8175-e01790284f91" />

<img width="1600" height="810" alt="Screenshot (1976)" src="https://github.com/user-attachments/assets/24f6412b-4efe-40d4-9d3b-49777063e664" />

<img width="1597" height="810" alt="Screenshot (1977)" src="https://github.com/user-attachments/assets/f3cd8dda-073e-4122-b572-2a29d79e35d8" />


# Task 3: Send the response to the customer

- Person 1: Cloud Support Engineer
- Person 2: Jess (Customer)

# Conversation
Engineer: "Hi Jess, I looked into your questions. Let me explain what I found."
# Part 1: Why SSH Didn't Work on Instance A
Engineer: "You couldn't connect to Instance A because it only has a private IP address. Private IPs only work inside your VPC - they can't be reached from the internet.
Instance B worked because it has a public IP address, which allows connections from outside the VPC."

# Part 2: Should You Use Public CIDR for Your VPC?
Engineer: "You asked about using public IP addresses for your new VPC. I don't recommend it. Here's why:
The Problem:

If you use public IPs like 8.8.0.0/16 for your VPC, your instances won't be able to reach the real internet addresses
Example: You couldn't reach Google DNS at 8.8.8.8 because AWS would look for it inside your VPC instead
This breaks everything - DNS, updates, API calls

# The Solution:
Use private IP ranges instead:

10.0.0.0/8
172.16.0.0/12
192.168.0.0/16

# How it should work:
Your VPC: 10.0.0.0/16

Public Subnet (10.0.1.0/24)
- Has Internet Gateway
- Resources can get public IPs
- Example: Bastion host

Private Subnet (10.0.2.0/24)  
- Uses NAT Gateway for internet
- More secure
- Example: Your app servers
# Benefits:

- No routing problems
- Can reach any internet service
- More secure
- AWS best practice"


# Part 3: Wrap Up
Engineer: "So my recommendation is: use a private CIDR block like 10.0.0.0/16 for your VPC. Put only necessary resources in public subnets with public IPs. Keep everything else in private subnets.
Any questions?"

Quick Answers to Common Questions
- "Don't I need public IPs for everything?"

No, only for resources that need internet connections coming IN. Most resources only need to go OUT to the internet, which NAT Gateway handles.

- "How do I manage private instances?"

Use a bastion host (jump server) in the public subnet to connect to private instances.

- "What if I already used public CIDR?"

You'd need to create a new VPC with private CIDR and move your resources.


# Key Point
Use private IP ranges (10.0.0.0/8, 172.16.0.0/12, or 192.168.0.0/16) for your VPC. Only give public IPs to resources that really need them.






# CHALLENGES
I initially struggled with understanding CIDR block notation and calculating the correct subnet size. I had to figure out how to ensure my public subnet CIDR was smaller than the VPC CIDR while still providing enough IP addresses (at least 50
# WHAT I LEARNED
Here’s what I learned from this lab:
- I reviewed the customer’s problem to understand their networking needs and what kind of cloud environment they required
- I built an Amazon VPC and learned how to set up subnets and assign IP addresses, which is like designing separate network sections for different resources.
- I became familiar with navigating the AWS Console to manage networking, resources, and configurations more efficiently
- Using what I learned, I created a practical solution that addressed the customer’s requirements within the VPC
# OVERALL
I learned how to analyze a customer scenario, design a VPC, configure its network components, and present a clear solution — core skills for cloud architecture and troubleshooting in AWS.
 # Lab complete 🎓


