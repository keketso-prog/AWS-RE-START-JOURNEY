# Lambda

I worked through a hands-on lab with AWS Lambda, learning how to create a serverless function that automatically counts words in text files and sends email notifications. Here's what I did.

# Task 1: Creating an SNS Topic for Email Notifications
I started by creating an Amazon SNS topic to handle email notifications:

- Navigated to the SNS service in the AWS Management Console
- Created a new topic with a descriptive name (WordCountTopic)
- Created a subscription with the protocol set to Email
- Entered my email address as the endpoint
- Confirmed the subscription by clicking the link sent to my email
<img width="1600" height="823" alt="Screenshot (1864)" src="https://github.com/user-attachments/assets/afce4f2b-2bf5-4b3a-8448-69ebe5d81d75" />
<img width="1590" height="823" alt="Screenshot (1865)" src="https://github.com/user-attachments/assets/0b0e9b7b-1760-45ef-90b7-516b48c9bab2" />

# Task 2: Creating the Lambda Function
I navigated to the Lambda service and created a new function:

- Chose "Author from scratch"
- Named the function (WordCountFunction)
- Selected Python as the runtime
- Created a new execution role with basic Lambda permissions

I then wrote the Lambda function code in Python that:

- Retrieved the uploaded text file from the S3 bucket using the event data
- Read the file contents
- Counted the number of words in the text
- Formatted the message as: "The word count in the <textFileName> file is nnn."
- Published the result to the SNS topic with the subject "Word Count Result"

I also configured the Lambda function's execution role to grant permissions for:

- Reading objects from S3
- Publishing messages to SNS

<img width="1594" height="823" alt="Screenshot (1866)" src="https://github.com/user-attachments/assets/c5f4e794-f603-4a59-96c9-56730dbae535" />
<img width="1594" height="819" alt="Screenshot (1867)" src="https://github.com/user-attachments/assets/1138b51c-d95d-4f58-b574-c90984460ad0" />

# Task 3: Configuring the S3 Bucket Trigger
I created an S3 bucket to store text files:

- Navigated to the S3 service and created a new bucket
- Configured the bucket to trigger the Lambda function automatically when objects are uploaded
- Added an event notification with:

- Event type: PUT (object created)
- Destination: Lambda function
- Lambda function: Selected my WordCountFunction

This setup ensured that whenever a text file was uploaded to the bucket, the Lambda function would automatically execute.
<img width="1590" height="819" alt="Screenshot (1868)" src="https://github.com/user-attachments/assets/7cffc751-2e90-434e-b712-ba760f73f870" />
<img width="1590" height="819" alt="Screenshot (1869)" src="https://github.com/user-attachments/assets/9a0a786d-c253-4172-a89f-cb6c61530284" />
<img width="1590" height="819" alt="Screenshot (1870)" src="https://github.com/user-attachments/assets/32162231-0a3b-4dd4-8547-fd7cfb4054a9" />
<img width="1600" height="816" alt="Screenshot (1871)" src="https://github.com/user-attachments/assets/4ad26a6d-ed83-4fc9-96d8-da7f0b2660e9" />
<img width="1590" height="819" alt="Screenshot (1872)" src="https://github.com/user-attachments/assets/eec53673-1f63-4005-ac4f-e99558659bb1" />
<img width="1590" height="819" alt="Screenshot (1873)" src="https://github.com/user-attachments/assets/bc4c245e-a4d4-4b29-b24c-c6f5344bae75" />
<img width="1587" height="819" alt="Screenshot (1874)" src="https://github.com/user-attachments/assets/be02ede0-e47d-47bb-b277-5645b02c27b2" />

# Task 4: Testing the Function
I tested the function by uploading several sample text files to the S3 bucket:

- Created text files with different word counts (5 words, 17 words, 50 words)
- Uploaded each file to the S3 bucket
- Verified that the Lambda function was triggered automatically for each upload
- Checked my email inbox for the SNS notifications

Each test successfully generated an email with the correct word count and filename.

<img width="1600" height="819" alt="Screenshot (1875)" src="https://github.com/user-attachments/assets/a57b6cae-26fc-4091-996d-5575d692f625" />
<img width="1594" height="816" alt="Screenshot (1876)" src="https://github.com/user-attachments/assets/bb9ccff0-4c53-4c2f-bbf3-33192188790f" />

# Task 5: Submitting Results

<img width="1584" height="826" alt="Screenshot (1877)" src="https://github.com/user-attachments/assets/a0867698-f998-4906-afab-82a624814954" />
<img width="1587" height="855" alt="Screenshot (1878)" src="https://github.com/user-attachments/assets/359c0453-ba18-498d-b69c-5f7cb9779f8a" />



# CHALLENGES
I initially encountered permission errors when the Lambda function tried to read files from S3. The error messages indicated "Access Denied." After troubleshooting, I realized the Lambda execution role didn't have the necessary S3 permissions. I had to manually add an IAM policy to the role that allowed s3:GetObject actions on the specific bucket. Once I updated the permissions, the function worked correctly and could read the text files without issues.
# WHAT I LEARNED
Here’s what I learned from this lab:
- I created a Lambda function that counts the number of words in a text file, showing how AWS can run code automatically without needing a server
- I configured an S3 bucket so that whenever a text file is uploaded, it automatically invokes the Lambda function to process the file
- I set up an Amazon SNS topic to send an email notification with the word count, making it easy to get automated results.
# OVERALL
I learned how to connect Lambda, S3, and SNS to create a serverless workflow that processes files and sends notifications — a powerful example of event-driven architecture in AWS.

##  Lab Complete 🎓



