# Project Overview:

- Brief: Static website for Marble Bistro - a busy local restaurant transitioning from manual paper-based bookings to automated online reservations and ordering system
- Team: 5 members
- Primary Goal: Eliminate paperwork chaos, prevent double bookings, enable online reservations/orders without phone calls

# Technical Stack:

- Frontend: HTML, CSS, JavaScript (static website)
- Hosting: Amazon S3 (static website hosting)
- CDN: Amazon CloudFront (global content delivery)
- DNS: Route 53 (domain management)
- Security: AWS Certificate Manager (SSL/TLS certificates)
- Database: Amazon DynamoDB (reservations & orders storage)
- Backend: AWS Lambda (serverless functions)
- API: Amazon API Gateway (REST endpoints)

# Notifications:

- Amazon SNS (SMS alerts to owner)
- Amazon SES (email confirmations to customers)



# System Architecture Flow:

- Customer → Custom Domain → Route 53 → CloudFront → S3 (website delivery)
- Form Submission → API Gateway → Lambda Function → DynamoDB (data processing)
-  Trigger → SNS (owner SMS notification) + SES (customer email confirmation)


# Deployment Setup:

- S3 bucket configured with static website hosting enabled
- Public access permissions set for website content
- CloudFront distribution configured with S3 as origin source
- Route 53 hosted zone managing custom domain DNS records
- SSL/TLS certificate from Certificate Manager attached to CloudFront
- Lambda functions with IAM roles for DynamoDB, SNS, and SES access
- API Gateway endpoints connected to Lambda functions

# Key Technical Features:

- Real-time booking availability validation via DynamoDB queries
- Automated dual notification system (SMS + Email)
- HTTPS encryption for all customer data
- Auto-scaling to handle traffic spikes
- 99.99% uptime SLA
- Serverless architecture (pay-per-use, no servers to manage)

# Performance Metrics:

- CloudFront edge caching for fast global load times
- Lambda cold start optimization
- DynamoDB single-digit millisecond latency
- Complete booking workflow executes in seconds
