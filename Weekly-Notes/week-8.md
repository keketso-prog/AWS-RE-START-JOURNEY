# WEEK 8

## Amazon EC2 Scaling

Think of scaling like adjusting the number of workers in a restaurant based on how busy it is.

**Vertical Scaling (Scaling Up/Down)**
- Making your server bigger or smaller
- Like upgrading from a small computer to a more powerful one
- Simple but requires stopping your instance
- Example: Going from t2.micro to t2.large

**Horizontal Scaling (Scaling Out/In)**
- Adding or removing more servers
- Like hiring more workers during rush hour
- Better for handling traffic spikes
- Uses Auto Scaling Groups to do this automatically

**Auto Scaling**
- AWS automatically adds or removes EC2 instances based on demand
- You set rules like "if CPU usage goes above 80%, add another server"
- Helps save money because you only pay for what you need
- Ensures your app stays responsive during high traffic

## Amazon Elastic Beanstalk Workflow

Elastic Beanstalk is like having an assistant who handles all the technical setup for you.

**What It Does:**
- You upload your code, and Beanstalk handles everything else
- It automatically creates EC2 instances, load balancers, and databases
- You don't need to manually configure infrastructure

**Basic Workflow:**
1. **Upload your application** - Just your code (Python, Java, Node.js, etc.)
2. **Beanstalk configures everything** - Creates servers, networking, monitoring
3. **Your app runs** - Users can access it immediately
4. **Update easily** - Upload new code, and Beanstalk handles the deployment
5. **Monitor & scale** - Beanstalk automatically adjusts based on traffic

**Why It's Useful:**
- Great for developers who want to focus on code, not infrastructure
- Faster deployment
- Still gives you control if you need to customize things

## Amazon API Gateway

API Gateway is like a receptionist for your backend services - it manages all incoming requests.

**What It Does:**
- Creates, publishes, and manages APIs (ways for apps to talk to each other)
- Acts as the "front door" for your applications
- Handles thousands of requests at the same time

**How It Works:**
1. Client (app or website) sends a request
2. API Gateway receives it and checks if it's allowed
3. Gateway forwards request to your backend (Lambda, EC2, etc.)
4. Backend processes and sends response back through Gateway
5. Gateway returns response to the client

**Key Features:**
- Security - Controls who can access your APIs
- Throttling - Limits requests to prevent overload
- Monitoring - Tracks all API calls
- Works great with Lambda for serverless apps

## Containers on AWS

Containers are like shipping containers for your code - they package everything your app needs to run.

**What Are Containers?**
- Lightweight packages that include your code and all dependencies
- Run consistently anywhere (your laptop, AWS, anywhere)
- Faster and more efficient than virtual machines

**AWS Container Services:**

**Amazon ECS (Elastic Container Service)**
- AWS's own container management service
- You tell it what containers to run, and it handles the rest
- Good integration with other AWS services

**Amazon EKS (Elastic Kubernetes Service)**
- Managed Kubernetes (popular container orchestration tool)
- Good if you're already using Kubernetes or need advanced features
- More complex but very powerful

**AWS Fargate**
- Serverless container service
- You don't manage any servers at all
- Just run containers without worrying about infrastructure
- Pay only for what you use

**When to Use Containers:**
- Running microservices (small, independent services)
- Easy deployment and scaling
- Consistent environments (dev, test, production)

## Elastic Load Balancing (ELB)

A load balancer is like a traffic cop directing cars to different lanes - it distributes incoming traffic across multiple servers.

**Why You Need It:**
- Prevents one server from getting overwhelmed
- If one server fails, traffic goes to healthy servers
- Improves application availability and reliability

**Types of Load Balancers:**

**Application Load Balancer (ALB)**
- Best for web applications (HTTP/HTTPS)
- Can route based on URL path
- Example: Send /api requests to one server, /images to another

**Network Load Balancer (NLB)**
- Handles millions of requests per second
- Best for high-performance applications
- Works at the network level (TCP/UDP)

**Classic Load Balancer**
- Older version, still works but less features
- Being phased out in favor of ALB and NLB

**How It Works:**
1. User sends request to load balancer
2. Load balancer checks which servers are healthy
3. Distributes traffic evenly across healthy servers
4. Returns response to user

## CloudFront

CloudFront is AWS's Content Delivery Network (CDN) - it stores copies of your content around the world for faster access.

**What It Does:**
- Caches your content at edge locations globally
- Users get content from the nearest location
- Makes websites load much faster

**How It Works:**
1. User requests a file (image, video, webpage)
2. CloudFront checks if it has a cached copy nearby
3. If yes, serves it immediately (fast!)
4. If no, gets it from your origin (S3, EC2) and caches it for next time

**Benefits:**
- Faster load times for users worldwide
- Reduces load on your origin servers
- Built-in DDoS protection
- Works great with S3 for static websites

**Common Uses:**
- Delivering websites and web applications
- Streaming video content
- Serving images and static files
- API acceleration

## Route 53

Route 53 is AWS's DNS service - it translates domain names (like www.example.com) into IP addresses that computers understand.

**What It Does:**
- Manages your domain names
- Routes users to your application
- Like a phone book for the internet

**Key Features:**

**Domain Registration**
- Buy and manage domain names directly through AWS
- Handles all the technical DNS stuff for you

**Routing Policies**
- **Simple:** Send all traffic to one place
- **Weighted:** Split traffic (80% to server A, 20% to server B)
- **Failover:** If primary server fails, route to backup
- **Geolocation:** Route users based on their location
- **Latency-based:** Send users to the fastest server for them

**Health Checks**
- Monitors if your servers are working
- Automatically stops sending traffic to failed servers

**How It Works:**
1. User types www.yoursite.com
2. Route 53 looks up where that site is hosted
3. Returns the IP address
4. User's browser connects to that IP

**Why It's Important:**
- Fast and reliable DNS resolution
- Integrates perfectly with other AWS services
- 99.99% availability
- Essential for making your website accessible

**Quick Tip:** These services often work together! For example:
- Route 53 → CloudFront → S3 (for a static website)
- Route 53 → ELB → EC2 Auto Scaling (for a web application)
- API Gateway → Lambda → Containers on ECS (for microservices)
