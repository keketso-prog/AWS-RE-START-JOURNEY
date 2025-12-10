# The Problem
What We Saw: 

Walking into Marble Bistro, we immediately noticed the chaos. The owner was juggling phone calls, writing bookings in an old notepad, and tracking orders on sticky notes everywhere. It was honestly stressful just watching.
# Main Issues
- Mixed-Up Orders
  
Nearly every day, someone's order got confused—imagine ordering pasta and getting someone else's burger instead.
- Double Bookings
  
This happened so often that the owner started saying "no" to customers just to play it safe, which meant losing business.
- Slow Responses
  
Customers waited hours for callbacks because the owner was too busy to keep up with the phone.
- Forgotten Regulars
  
There was no way to remember loyal customers or what they liked, so they missed that special personal touch.
- Can't Grow
  
To handle more customers, they'd need to hire people just to answer phones and track bookings—not a smart use of money.
- Exhausted Owner
  
The owner was burnt out, frustrated, and desperately needed help.
- Our Goal
  
We wanted to fix these problems with a simple digital solution, so the team could focus on what they love—great food and happy customers.

# What We Built:
- A clean, straightforward website where customers can book tables and place orders without picking up the phone. Nothing fancy or overcomplicated—just a solid solution that works.

<img width="1600" height="900" alt="Screenshot (1622)" src="https://github.com/user-attachments/assets/7d56e334-724b-4278-a595-33f27bce1708" />

# Technical Implementation:


<img width="1600" height="855" alt="Screenshot (1821)" src="https://github.com/user-attachments/assets/750feab8-b3a7-4441-91ea-ad14bebc4fc6" />

<img width="1600" height="868" alt="Screenshot (1822)" src="https://github.com/user-attachments/assets/4545609a-76ab-4d33-87d1-1253a2e26a4d" />

<img width="1600" height="861" alt="Screenshot (1823)" src="https://github.com/user-attachments/assets/192a4a58-3e45-4781-8194-a1709cf1f0c6" />

<img width="1600" height="861" alt="Screenshot (1824)" src="https://github.com/user-attachments/assets/ce62f5f0-0180-4352-b524-998d943e3f76" />

<img width="1590" height="858" alt="Screenshot (1825)" src="https://github.com/user-attachments/assets/6eb2c4bb-ea4d-40d2-a201-6129629dc09d" />

# Amazon S3 - Static Website Hosting:

- Chose S3 for simple yet powerful content storage and serving
- Created S3 bucket housing all website files: HTML pages, CSS stylesheets, JavaScript functionality, image assets (menu photos, branding materials)
- Enabled static website hosting in bucket configuration
- Set appropriate public access permissions
- Benefits: Reliable hosting at fraction of traditional server costs

<img width="1917" height="854" alt="Objects-hosted-on-S3" src="https://github.com/user-attachments/assets/6a2f498d-7b36-45c0-aadc-2aba15644ddc" />

# Amazon CloudFront - Content Delivery Network:

- Integrated to ensure fast loading times for all users globally
- Caches website content across multiple edge locations worldwide
- Customers receive data from server closest to their physical location
- Configured CloudFront distribution with S3 bucket as origin source
- Result: Dramatically reduced page load times, improved browsing experience especially during peak traffic hours

<img width="1907" height="835" alt="Cloudfront" src="https://github.com/user-attachments/assets/41c662eb-7b77-482f-9a02-72297e95750c" />

# Route 53 - DNS Management:

- Registered custom domain name for professional presentation
- Route 53 translates easy-to-remember domain into technical addresses locating CloudFront distribution
- Created hosted zone and configured necessary DNS records
- Routes traffic from domain to website properly
- Gave restaurant professional web presence with clean, memorable, trustworthy URL

# AWS Certificate Manager - SSL/TLS Encryption:

- Security non-negotiable since customers provide personal information for reservations/orders
- Provisioned free SSL/TLS certificate for domain
- Certificate attached to CloudFront distribution
- Encrypts all communication between customers' browsers and website
- Result: Secure HTTPS connection with padlock icon in browser, protecting customer data and building trust

# Amazon DynamoDB - Centralized Data Storage:

- Eliminates lost bookings and order mix-ups
- Checks availability in real-time before confirming bookings
- Prevents double-booking problems that frustrated customers
- Serves as trigger for notification system
- When new bookings saved to database: automatically sends SMS alerts to owner via SNS and confirmation emails to customers via SES

<img width="1906" height="859" alt="DynamoDB-Tables" src="https://github.com/user-attachments/assets/fa3e21aa-8a44-49f1-bb75-6a277906d76f" />

# AWS Lambda - Serverless Computing:

- Handles behind-the-scenes work static websites can't do alone
- Runs code without managing servers—only executes when triggered (e.g., customer submits booking)
  
#  Lambda functions created to:
-  Validate form data
- Check DynamoDB for available time slots
- Save confirmed bookings to database
- Fire off SNS and SES notifications

# Benefits: 
- Only pay for split seconds when code actually runs, automatically handles whether one person or hundred people book simultaneously

<img width="1902" height="856" alt="Lambda" src="https://github.com/user-attachments/assets/1cba5ab0-04d4-4e66-a3a0-9219321d9803" />

<img width="1899" height="856" alt="IAM-Configuration" src="https://github.com/user-attachments/assets/b77ac084-f904-4c4c-82ce-89926a43b3bc" />

# Amazon API Gateway:

- Creates secure endpoints connecting static website to Lambda functions
- When someone clicks "Confirm Reservation": form sends data to API Gateway → triggers appropriate Lambda function
- Built-in security features: rate limiting to prevent spam, validates incoming data before passing along
- Acts as secure bridge between customer-facing website and background processing

<img width="1897" height="856" alt="API-Gateway" src="https://github.com/user-attachments/assets/c9536b52-4c89-40c1-ba77-87e0e86b9a91" />

# Amazon SNS - Instant SMS Notifications:

- Real-time notifications for restaurant staff - most valuable feature implemented
- Created SNS topic dedicated to restaurant notifications
- Subscribed owner's phone number to topic
- When customer completes booking form: triggers SNS topic sending SMS to owner's phone
- SMS contains: customer name, date/time, number of guests, special requests
- Eliminates risk of missed bookings, allows quick response to customer needs

# Amazon SES - Automated Email Confirmations:

- Enhances customer experience with automated confirmations
- After booking/order submission: SES immediately sends confirmation email
- Email includes: complete transaction summary, reservation details, unique confirmation number, estimated preparation times, restaurant contact information for changes
- Provides customers immediate peace of mind and reference record
- Reduces confirmation calls to restaurant

<img width="1267" height="543" alt="Screenshot (1634)" src="https://github.com/user-attachments/assets/f7e18b79-d905-42f9-95ba-5f7508066cf2" />

# Complete System Workflow:
# Customer Access Flow:

- Customer navigates to Marble Bistro's website using custom domain name
- Route 53 resolves domain and directs request to CloudFront distribution
- CloudFront serves website content from nearest edge location, pulling from S3 as needed
- All data exchanged between customer and website encrypted via SSL/TLS certificate

# Booking/Order Submission Flow:

- Customer submits booking or order form
- Form data sent to API Gateway endpoint
- API Gateway triggers Lambda function
- Lambda validates data and checks DynamoDB availability
- Lambda saves confirmed booking to DynamoDB
- DynamoDB triggers notification system:

- SNS immediately sends SMS alert to restaurant owner with details
- SES simultaneously sends confirmation email to customer

<img width="1287" height="600" alt="Screenshot (1635)" src="https://github.com/user-attachments/assets/d9c0d5e7-f0a4-4ab3-8a07-319d5f4390b1" />

# Execution Speed: 
- Entire sequence executes in matter of seconds, providing both parties instant confirmation.

# Why We Chose AWS
- Cost-Effective Solution
The owner was understandably concerned about costs. AWS's pay-as-you-go model was the perfect fit—charges are based only on actual usage, not expensive servers sitting idle. For a site like this, monthly costs are less than what they spent on paper and ink for their manual system.
- Reliable Performance
We promised 99.99% uptime, but explained it practically: "Your website works 24/7, even at 2 AM when someone wants to order for tomorrow." That clicked immediately—no missed opportunities due to downtime.
- Handles Peak Traffic
Restaurants face huge traffic spikes during Valentine's Day or Mother's Day. The AWS infrastructure seamlessly handles these surges without crashes or slowdowns, ensuring no customers are turned away due to technical issues.
- Strong Security
Without getting too technical, we emphasized that AWS protects customer data far better than paper files or outdated computers. In today's world, this security builds essential customer trust.
- Zero Maintenance
This was the biggest selling point. The owner admitted having limited tech knowledge and no interest in learning. With AWS managing everything—updates, servers, security—they don't have to. The system just runs while they focus on food and service.
- Fast Loading
CloudFront ensures quick loading whether customers browse from home or while commuting. Better performance means happier customers and more completed orders.
- Room to Grow
When they're ready for loyalty programs, mobile apps, or expansion, AWS makes it straightforward without rebuilding from scratch.

# Operational Benefits
- Self-Sustaining System
- Once deployed, the platform runs autonomously—handling traffic spikes, maintaining security, processing notifications—all without manual intervention. The restaurant can - focus entirely on their craft while the technology works reliably in the background.
- Built for Growth
- The architecture handles current operations and future expansion seamlessly, protecting their investment long-term.

# Real-World Impact
- Results After Launch
- Our follow-up visit weeks later revealed a remarkable transformation:

- No more double bookings thanks to real-time availability checking
- Zero order mix-ups with the streamlined digital system
- Relieved staff working with clear, organized information
- Present owner now engaging with guests instead of being glued to the phone


# Team Collaboration
- Our Approach
Coordinating five people could have been chaotic, but we divided work based on strengths: some handled design and coding, others managed AWS setup, and the rest focused on content and presentation. We had our disagreements—especially about color schemes—but ultimately we're proud of the solution we delivered and its positive impact on Marble Bistro.
