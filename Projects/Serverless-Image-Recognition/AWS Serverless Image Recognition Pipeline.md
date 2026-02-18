## AWS Serverless Image Recognition Pipeline

This project automatically detect objects, animals, scenes, and more in any image — powered by Amazon Rekognition, AWS Lambda, and S3. No servers. No manual steps. Just upload and go


# Step 1 — Create an S3 Bucket

- i went to S3 in the AWS Console
- Clicked on Create bucket
-  Gave it a unique name ( my-rekognition-images-2024)
- Choose MY region (e.g., us-east-1)
- Left all other settings as default and clicked Create bucket


# Step 2 — Create an IAM Role

- Went to IAM → Roles → Create role
- Selected AWS service → Use case: Lambda
- Attach these policies:

AmazonS3ReadOnlyAccess
AmazonRekognitionFullAccess
AWSLambdaBasicExecutionRole ← required for CloudWatch logs


Name the role LambdaRekognitionRole and click Create role


# Step 3 — Create the Lambda Function

- Went to Lambda → Functions → Create function
- Selected Author from scratch
- Function name: detect-image-labels
- Runtime: Python 3.12
- Execution role: Use an existing role → select LambdaRekognitionRole
- Clicked Create function


# Step 4 — Add the S3 Trigger

- In my Lambda function, clicked + Add trigger
 -Selected S3
- Choose my bucket
- Event type: All object create events
- Acknowledged the warning and click Add


# Step 5 — Deploy the Code
- Replaced the default Lambda code with the following and click Deploy:


# Real Test (Upload an Image)

- Went to my S3 bucket
- Clicked Upload → select any .jpg or .png
- Clicked Upload
- Wait 15–30 seconds
- Went to Lambda → Monitor → View CloudWatch logs
- Open the latest log stream and look for:
