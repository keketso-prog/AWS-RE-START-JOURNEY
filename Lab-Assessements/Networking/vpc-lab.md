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

Hello Jess,

Thank you for reaching out to AWS Cloud Support. I reviewed your architecture and the details you provided, and I’m happy to share what we found along with guidance on your CIDR question.

Findings: Why Instance A Cannot Reach the Internet

Although instance A and instance B are in the same VPC and subnet, there is one key difference at the EC2 instance level:

Instance B has a public IPv4 address

Instance A has only a private IPv4 address

Even with a correctly configured VPC, subnet, route table, and Internet Gateway, an EC2 instance must have a public IPv4 address (or an Elastic IP) to directly access the internet.

What this means:

Instance B can reach the internet because it has:

A private IP (for internal VPC communication)

A public IP (for external internet access)

Instance A cannot reach the internet because:

It only has a private IP, which is not routable outside the VPC

This also explains why SSH access works for instance B from outside the VPC but not for instance A.

How to resolve this:

You have two common options:

Assign a public IPv4 address or Elastic IP to instance A, or

Place instance A in a private subnet and route outbound traffic through a NAT Gateway if you want outbound-only internet access without exposing the instance publicly.

Guidance on Using a Public CIDR Range (e.g., 12.0.0.0/16) for a VPC

I strongly do not recommend using a public IP address range (such as 12.0.0.0/16) when creating a VPC.

Reasons:

Public IP ranges are owned and routable on the internet

Using them privately can cause routing conflicts with real internet destinations.

Hybrid connectivity issues

If you ever connect your VPC to on-premises networks or other VPCs (VPN, Direct Connect, peering), overlapping with public ranges can break routing.

AWS best practice

AWS VPCs are designed to use RFC 1918 private address ranges, such as:

10.0.0.0/8

172.16.0.0/12

192.168.0.0/16

Using private CIDRs ensures predictable routing, scalability, and compatibility with future networking designs.

Summary

The internet connectivity issue is due to instance A lacking a public IP, not a VPC or subnet misconfiguration.

Assigning a public IP or using a NAT-based design will resolve the issue.

For new VPCs, always use private RFC 1918 CIDR ranges to avoid routing conflicts and future limitations.

Please let me know if you’d like assistance assigning a public IP, setting up a NAT Gateway, or designing a secure subnet strategy. Happy to help!

Best regards,
Keketso
Cloud Support Engineer
Amazon Web Services (AWS)



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


