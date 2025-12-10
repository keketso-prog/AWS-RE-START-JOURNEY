# Business Problem :
# The Situation We Found:
- Walking into Marble Bistro revealed complete operational chaos:

- Owner juggling phone calls while scribbling bookings on worn-out notepad
- Takeout orders tracked on scattered sticky notes
- Watching the operation was genuinely stressful

# Critical Problems Identified:

- Order Mix-ups: Happening almost daily - customers ordering pasta receiving someone else's burger
- Double Bookings: So frequent the owner started turning away customers preemptively to be safe
- Communication Delays: Customers waiting hours for reservation callbacks because owner was too swamped
- Lost Personalization: No system to remember regular customers or their preferences - missing the personal touch that makes small restaurants special
- Zero Scalability: Would need to hire additional staff just to manage phones and paperwork to handle growth
- Owner Burnout: Frustrated and exhausted, desperately needed help

# What We Built:
- A clean, straightforward website where customers can book tables and place orders without picking up the phone. Nothing fancy or overcomplicated—just a solid solution that works.

<img width="1600" height="900" alt="Screenshot (1622)" src="https://github.com/user-attachments/assets/7d56e334-724b-4278-a595-33f27bce1708" />

# Technical Implementation:


<img width="1600" height="855" alt="Screenshot (1821)" src="https://github.com/user-attachments/assets/750feab8-b3a7-4441-91ea-ad14bebc4fc6" />

<img width="1600" height="868" alt="Screenshot (1822)" src="https://github.com/user-attachments/assets/4545609a-76ab-4d33-87d1-1253a2e26a4d" />

<img width="1600" height="861" alt="Screenshot (1823)" src="https://github.com/user-attachments/assets/192a4a58-3e45-4781-8194-a1709cf1f0c6" />

<img width="1600" height="861" alt="Screenshot (1824)" src="https://github.com/user-attachments/assets/ce62f5f0-0180-4352-b524-998d943e3f76" />

<img width="1590" height="858" alt="Screenshot (1825)" src="https://github.com/user-attachments/assets/6eb2c4bb-ea4d-40d2-a201-6129629dc09d" /

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

# AWS Lambda - Serverless Computing:

- Handles behind-the-scenes work static websites can't do alone
- Runs code without managing servers—only executes when triggered (e.g., customer submits booking)
- Lambda functions created to:

# Validate form data
- Check DynamoDB for available time slots
- Save confirmed bookings to database
- Fire off SNS and SES notifications


# Benefits: 
- Only pay for split seconds when code actually runs, automatically handles whether one person or hundred people book simultaneously

# Amazon API Gateway:

- Creates secure endpoints connecting static website to Lambda functions
- When someone clicks "Confirm Reservation": form sends data to API Gateway → triggers appropriate Lambda function
- Built-in security features: rate limiting to prevent spam, validates incoming data before passing along
- Acts as secure bridge between customer-facing website and background processing

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



# Execution Speed: 
- Entire sequence executes in matter of seconds, providing both parties instant confirmation.

# Why We Chose AWS:

# Actually Affordable:

- Owner worried about costs, but AWS pricing was eye-opening
- Only charged for actual usage—no expensive servers gathering dust in back room
- For static website like this: monthly cost less than printer paper and ink for old system

# It Just Works:

- Promised 99.99% uptime
- In real terms: "Website will be up and running pretty much always—even at 2 AM when someone's craving your food and wants to place order for tomorrow"
- That explanation clicked immediately

# Handles the Rush:

- Website handles traffic spikes without breaking a sweat
- No crashes, no slowdowns, no turning customers away

# Way More Secure:

- AWS protects customer information way better than filing cabinet or old computer ever could
- In today's world, that peace of mind matters to customers

# Zero Maintenance Headaches:

- Owner doesn't know much about technology and didn't want to learn
-With AWS managing infrastructure, they don't need to:
No updates to install, no servers to maintain, nothing
- It just runs

# Fast Loading Times:

- With CloudFront: site loads quickly whether customers at home or commuting
- Happy customers, more orders

# Room to Grow:

- AWS makes expansion straightforward without starting from scratch


# Operational Benefits:
# Self-Sustaining Architecture:

- Once deployed: requires no ongoing technical maintenance from restaurant owner
- System automatically handles:

- Traffic fluctuations
- Security certificate maintenance
- Notification processing


- No manual intervention needed
- Business can focus entirely on food quality and customer service
- Technology infrastructure operates reliably in background

# Scalability:

- Can handle current operations and future expansion seamlessly


# Real-World Impact:
- A Few Weeks After Launch:
- Double bookings: gone
- Orders: coming through clearly

- Even staff was relieved
- When orders are clear and bookings organized, everyone's job gets easier


# Team Collaboration Experience:
- Working as Team of Five:

-Five people working on one project could've been messy, but we made it work
- Split up tasks based on individual strengths:

- Some handled design and coding
- Others tackled AWS setup
- Few focused on content creation and presentation preparation


- We had moments of disagreement (especially about color schemes!)
- Overall: pretty proud of what we pulled together


