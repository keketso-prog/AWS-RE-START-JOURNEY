## AWS Serverless Image Recognition Pipeline

This project automatically detect objects, animals, scenes, and more in any image — powered by Amazon Rekognition, AWS Lambda, and S3. No servers. No manual steps. Just upload and go


# Step 1 — Create an S3 Bucket

Go to S3 in the AWS Console
Click Create bucket
Give it a unique name (e.g., my-rekognition-images-yourname)
Choose your region (e.g., us-east-1)
Leave all other settings as default and click Create bucket


# Step 2 — Create an IAM Role

Go to IAM → Roles → Create role
Select AWS service → Use case: Lambda
Attach these policies:

AmazonS3ReadOnlyAccess
AmazonRekognitionFullAccess
AWSLambdaBasicExecutionRole ← required for CloudWatch logs


Name the role LambdaRekognitionRole and click Create role


# Step 3 — Create the Lambda Function

Go to Lambda → Functions → Create function
Select Author from scratch
Function name: detect-image-labels
Runtime: Python 3.12
Execution role: Use an existing role → select LambdaRekognitionRole
Click Create function


# Step 4 — Add the S3 Trigger

In your Lambda function, click + Add trigger
Select S3
Choose your bucket
Event type: All object create events
Acknowledge the warning and click Add


# Step 5 — Deploy the Code
Replace the default Lambda code with the following and click Deploy:


# Real Test (Upload an Image)

Go to your S3 bucket
Click Upload → select any .jpg or .png
Click Upload
Wait 15–30 seconds
Go to Lambda → Monitor → View CloudWatch logs
Open the latest log stream and look for:
