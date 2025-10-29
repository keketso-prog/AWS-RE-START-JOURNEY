
WEEK 1

🌩️ What is AWS?

AWS stands for Amazon Web Services.
It is a cloud computing platform made by Amazon.

That means instead of buying and managing your own computers (servers),
you can rent computing power, storage, and tools from Amazon over the internet.

🕰️ Here is a Short History of AWS

2002: Amazon started experimenting with web services.

2006: AWS officially launched with a few basic services:

S3 (for file storage)

EC2 (for virtual computers/servers)

SQS (for message queuing)

2010s: AWS grew fast — many startups and big companies started using it.

Today: AWS is one of the largest cloud providers in the world, along with Google Cloud and Microsoft Azure.
BELOW IS A TABLE AND EXPLANATION OF SOME OF THE SERVICES THEY OFFER
| **Type of Service**          | **Examples**              | **Simple Meaning**                                                          |
| ---------------------------- | ------------------------- | --------------------------------------------------------------------------- |
| 💻 **Compute**               | EC2, Lambda               | Lets you run apps or websites on Amazon’s computers.                        |
| 📦 **Storage**               | S3, EBS                   | Keeps your files, photos, and backups safe online.                          |
| 🗂️ **Databases**            | RDS, DynamoDB             | Stores your data so you can find and use it easily.                         |
| 🌍 **Networking**            | VPC, CloudFront, Route 53 | Connects your apps to the internet safely and fast.                         |
| 🧠 **AI & Machine Learning** | SageMaker, Rekognition    | Helps make smart apps that can learn or see things (like face recognition). |
| 🧰 **Developer Tools**       | CodeBuild, CodeDeploy     | Helps programmers build and update apps quickly.                            |
| 🔐 **Security & Identity**   | IAM, KMS                  | Keeps your information safe and controls who can access it.                 |
| 📊 **Analytics**             | Athena, Redshift          | Helps you understand and study your data.                                   |

WHAT IS CLOUD COMPUTING?

Cloud computing is the delivery of computing services over the internet rather than using local servers or personal devices. Instead of owning and maintaining physical hardware, you rent computing resources from a provider on an as-needed basis.

THIS ARE THE CHARACTERISTICS OF CLOUD COMPUTING
- Resources accessed via the internet
- Pay-as-you-go pricing model
- Scalable (increase or decrease resources as needed)
- No physical hardware maintenance required

    THIS ARE SOME EXAMPLES OF AWS CLOUD COMPUTING SERVICES THEY OFFER
  
- EC2 (Elastic Compute Cloud) - Virtual servers in the cloud. You can launch different sized virtual machines with various operating systems to run your applications. 
- S3 (Simple Storage Service) - Object storage for files and data. You can store and retrieve any amount of data at any time.
- RDS (Relational Database Service) - Managed database service that handles setup, patching, and backups automatically.
- Lambda - Serverless computing where you run code without provisioning servers. 
- CloudFront - Content delivery network (CDN) that distributes your content globally. 
- VPC (Virtual Private Cloud) - Lets you create isolated virtual networks within AWS where you control IP addresses, subnets, and security settings.

  AWS SHARED RESPONSIBILITY MODEL
  
This defines who's responsible for what between AWS and you (the customer). A simple day-to-day example is like renting an apartment:

AWS is responsible for "Security OF the Cloud":

Physical security of data centers (guards, cameras, locks)
Hardware and infrastructure (servers, storage, networking equipment)
Virtualization layer that separates customers
Maintaining the underlying services

You are responsible for "Security IN the Cloud":

Your data and content
User access management (who can access what)
Operating system patches and updates (for EC2 instances)
Application security
Firewall configurations
Encryption settings

Simple analogy: AWS builds and maintains the building, elevators, and utilities. You're responsible for locking your apartment door, managing who has keys, and securing your belongings inside.

AWS PRICING MODEL IS AS FOLLOWS

AWS uses a pay-as-you-go model. You only pay for what you use, with no upfront costs or long-term contracts (though you can get discounts with commitments).
Compute (EC2): Charged per second/hour the instance runs. Larger, more powerful instances cost more.
Storage (S3): Pay per GB stored per month, plus charges for data retrieval and transfers.
Data Transfer: Moving data OUT of AWS to the internet costs money. Data transferred IN is usually free. Data between AWS services in the same region is often free or cheap

