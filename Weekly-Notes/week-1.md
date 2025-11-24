# Week 1: AWS Fundamentals

## What is AWS?

**AWS stands for Amazon Web Services** - Amazon's cloud computing platform that lets you rent computing power, storage, and tools over the internet instead of buying and managing your own physical servers.

### Quick History:
- **2002:** Amazon started experimenting with web services
- **2006:** AWS officially launched with S3, EC2, and SQS  
- **2010s:** Rapid growth - startups and big companies adopted AWS
- **Today:** One of the world's largest cloud providers

---

## Main AWS Services

| Service Type | Examples | What it does |
|-------------|----------|--------------|
| **Compute** | EC2, Lambda | Run apps and websites on Amazon's computers |
| **Storage** | S3, EBS | Keep files, photos, and backups safe online |
| **Database** | RDS, DynamoDB | Store and organize data easily |
| **Networking** | VPC, CloudFront | Connect apps to the internet safely and fast |
| **Security** | IAM, KMS | Keep information safe and control access |

---

## What is Cloud Computing?

**Simple answer:** Using someone else's computers over the internet instead of owning physical servers yourself.

### Key Benefits:
- No upfront costs  
- Pay only for what you use  
- Scale up or down instantly  
- Access from anywhere  
- No hardware maintenance  

### Service Types:
- **IaaS** - Basic building blocks (like EC2)
- **PaaS** - Platform ready to use (like Elastic Beanstalk)  
- **SaaS** - Complete applications (like Gmail)

## Shared Responsibility Model

Think of it like **renting an apartment:**

| AWS Responsibility (Landlord) | Your Responsibility (Tenant) |
|-------------------------------|------------------------------|
| Physical security of data centers | Your data and content |
| Hardware maintenance | User access management |
| Network infrastructure | Operating system updates |
| Building security | Application security |

## AWS Pricing

**Main idea:** Pay-as-you-go, like your electricity bill!

### 3 Pricing Models:
1. **Pay-as-you-go** - Only pay when you use services
2. **Save by reserving** - Commit 1-3 years for discounts  
3. **Volume discounts** - Use more = pay less per unit

**Free Tier:** AWS gives you free usage limits for 12 months - perfect for learning!

## Amazon EC2 (Virtual Servers)

**EC2 = Elastic Compute Cloud** - Think of it as renting a computer in Amazon's data center that you can access over the internet.

### Instance Types (Size Options):
- **t2.micro** - Small (free tier)
- **t2.medium** - Medium power  
- **c5.large** - High CPU
- **r5.large** - High RAM

### Pricing Options:
- **On-Demand** - Pay per hour (flexible)
- **Reserved** - 1-3 year commitment (cheaper)
- **Spot** - Bid on unused capacity (cheapest)

## AWS Global Infrastructure

AWS has data centers all around the world to bring services closer to users.

- **Regions** - Physical locations (like US East, Europe)
- **Availability Zones** - Data centers within a region (for backup)  
- **Edge Locations** - Cache points for faster content delivery

## Week 1 Key Takeaways 

- AWS is Amazon's cloud computing platform  
- Cloud computing = using someone else's computers over internet  
- Pay-as-you-go pricing model  
- EC2 provides virtual servers  
- Shared responsibility model  
- Global infrastructure with regions and AZs  
- Free tier available for learning  
- IaaS, PaaS, SaaS service models  

### Personal Note:
This week was mind-blowing! Coming from an administrative background, learning that you can rent computing power like electricity was a game-changer. The concept of not owning physical servers but still having full control over virtual ones is incredible.

