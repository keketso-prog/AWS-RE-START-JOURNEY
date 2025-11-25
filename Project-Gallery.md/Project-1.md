
# How We Built It
We built Marble Bistro's website using a combination of AWS services that work together to create a reliable, secure, and efficient platform. Here's a breakdown of our technical approach

<img width="1600" height="900" alt="Screenshot (1622)" src="https://github.com/user-attachments/assets/7d56e334-724b-4278-a595-33f27bce1708" />

# Technical Implementation
We built Marble Bistro's website using a combination of AWS services that work together to create a reliable, secure, and efficient platform. 

Here's a breakdown of our technical approach:
# Amazon S3 - Static Website Hosting
We chose Amazon S3 as the hosting solution for our static website. S3 provides a simple yet powerful way to store and serve web content without the complexity of managing traditional servers. We created an S3 bucket to house all our website files—HTML pages, CSS stylesheets, JavaScript functionality, and image assets including menu photos and branding materials. After uploading our files, we enabled static website hosting in the bucket configuration and set the appropriate permissions to make the content publicly accessible. This approach gave us reliable hosting at a fraction of the cost of conventional server solutions.
# Amazon CloudFront - Content Delivery Network
To ensure fast loading times for all users, we integrated Amazon CloudFront as our content delivery network. CloudFront caches our website content across multiple edge locations around the world, which means customers receive data from the server closest to their physical location. We configured our CloudFront distribution to pull content from the S3 bucket as its origin source. This setup dramatically reduced page load times and improved the browsing experience, particularly during peak hours when the restaurant receives the most online traffic.
# Route 53 - DNS Management
Professional presentation was important to us, so we registered a custom domain name for Marble Bistro and managed it through Amazon Route 53. Route 53 is AWS's domain name system service that translates the easy-to-remember domain name into the technical addresses needed to locate our CloudFront distribution. We created a hosted zone and configured the necessary DNS records to properly route traffic from the domain to our website. This gave the restaurant a professional web presence with a clean, memorable URL that customers can easily find and trust.
# AWS Certificate Manager - SSL/TLS Encryption
Security was non-negotiable for this project, especially since customers would be providing personal information for reservations and orders. We used AWS Certificate Manager to provision a free SSL/TLS certificate for the domain. This certificate, attached to our CloudFront distribution, encrypts all communication between customers' browsers and our website. The result is a secure HTTPS connection indicated by the padlock icon in the browser address bar, which both protects customer data and builds trust in the platform.
# Amazon SNS - Instant SMS Notifications
One of the most valuable features we implemented was real-time notifications for the restaurant staff. Using Amazon Simple Notification Service (SNS), we created a notification system that alerts the owner immediately when new bookings or orders come through. We set up an SNS topic dedicated to restaurant notifications and subscribed the owner's phone number to it. When a customer completes a booking form on the website, the form submission triggers the SNS topic, which sends an SMS message to the owner's phone containing the reservation details—customer name, date and time, number of guests, and any special requests noted. This immediate notification system eliminates the risk of missed bookings and allows the restaurant to respond quickly to customer needs.
# Amazon SES - Automated Email Confirmations
To enhance the customer experience, we integrated Amazon Simple Email Service (SES) to handle automated email confirmations. After a customer submits a booking or places an order, SES immediately sends them a confirmation email with a complete summary of their transaction. The email includes their reservation details, a unique confirmation number, estimated preparation times for orders, and the restaurant's contact information in case they need to make changes. These automated confirmations provide customers with immediate peace of mind and a record they can reference, while simultaneously reducing the number of confirmation calls the restaurant receives.
System Architecture and Workflow

<img width="1287" height="600" alt="Screenshot (1635)" src="https://github.com/user-attachments/assets/d9c0d5e7-f0a4-4ab3-8a07-319d5f4390b1" />


# The complete system works through the following process:

- A customer navigates to Marble Bistro's website using the custom domain name
- Route 53 resolves the domain and directs the request to our CloudFront distribution
- CloudFront serves the website content from the nearest edge location, pulling from S3 as needed
- All data exchanged between the customer and the website is encrypted via the SSL/TLS certificate
# When the customer submits a booking or order:

- SNS immediately sends an SMS alert to the restaurant owner with the details
- SES simultaneously sends a confirmation email to the customer



This entire sequence executes in a matter of seconds, providing both parties with instant confirmation.
# Operational Benefits
- The architecture we've built is designed to be self-sustaining. Once deployed, it requires no ongoing technical maintenance from the restaurant owner.
-  The system automatically handles traffic fluctuations, maintains security certificates, and processes notifications without manual intervention.
-  This allows the business to focus entirely on food quality and customer service while the technology infrastructure operates reliably in the background.
-  The combination of these AWS services has created a solution that's not only functional but also scalable for future growth.
