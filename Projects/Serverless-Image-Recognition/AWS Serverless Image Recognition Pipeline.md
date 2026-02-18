## AWS Serverless Image Recognition Pipeline

This project automatically detect objects, animals, scenes, and more in any image — powered by Amazon Rekognition, AWS Lambda, and S3. No servers. No manual steps. Just upload and go


# Step 1 — Create an S3 Bucket

- i went to S3 in the AWS Console
- Clicked on Create bucket
-  Gave it a unique name ( my-rekognition-images-2024)
- Choose MY region (e.g., us-east-1)
- Left all other settings as default and clicked Create bucket

<img width="1594" height="861" alt="Screenshot (2034)" src="https://github.com/user-attachments/assets/9cd47b15-427e-4f19-a149-dedb6220dc5e" />
<img width="1600" height="852" alt="Screenshot (2035)" src="https://github.com/user-attachments/assets/79948eb9-b8e1-4e4a-b232-c838905f4333" />


# Step 2 — Create an IAM Role

- Went to IAM → Roles → Create role
- Selected AWS service → Use case: Lambda
- Attach these policies:

AmazonS3ReadOnlyAccess
AmazonRekognitionFullAccess
AWSLambdaBasicExecutionRole ← required for CloudWatch logs


Name the role LambdaRekognitionRole and click Create role

<img width="1600" height="861" alt="Screenshot (2036)" src="https://github.com/user-attachments/assets/f57ded25-0e49-473c-9d44-655e197fa273" />
<img width="1581" height="855" alt="Screenshot (2037)" src="https://github.com/user-attachments/assets/dc2819dc-6f2a-4240-b9ee-c3a780a94a75" />
<img width="1597" height="861" alt="Screenshot (2038)" src="https://github.com/user-attachments/assets/a9b2c25c-0708-46ea-ae2d-dcd995a9848a" />
<img width="1597" height="858" alt="Screenshot (2039)" src="https://github.com/user-attachments/assets/79ec3eee-1819-4748-ab11-76c5e85b613e" />
<img width="1594" height="865" alt="Screenshot (2055)" src="https://github.com/user-attachments/assets/0d54b0f1-0ff1-45df-89be-8f5bc18c0e93" />
<img width="1600" height="865" alt="Screenshot (2040)" src="https://github.com/user-attachments/assets/7c1f554f-795d-4497-92ae-a52b4bb63e65" />


# Step 3 — Create the Lambda Function

- Went to Lambda → Functions → Create function
- Selected Author from scratch
- Function name: detect-image-labels
- Runtime: Python 3.12
- Execution role: Use an existing role → select LambdaRekognitionRole
- Clicked Create function

<img width="1597" height="865" alt="Screenshot (2042)" src="https://github.com/user-attachments/assets/b68fdc01-6e3b-4d39-bb3f-4f7a6a5a79df" />
<img width="1600" height="865" alt="Screenshot (2043)" src="https://github.com/user-attachments/assets/240d73c6-b911-42f0-ba2a-f7849437adec" />
<img width="1600" height="848" alt="Screenshot (2044)" src="https://github.com/user-attachments/assets/be74d70d-1cfe-4969-b727-d7ae48e9bc91" />



# Step 4 — Add the S3 Trigger

- In my Lambda function, clicked + Add trigger
 -Selected S3
- Choose my bucket
- Event type: All object create events
- Acknowledged the warning and click Add

<img width="1600" height="865" alt="Screenshot (2046)" src="https://github.com/user-attachments/assets/30b308fa-28e0-4b18-a73d-0c90de2fd17e" />
<img width="1597" height="861" alt="Screenshot (2047)" src="https://github.com/user-attachments/assets/e52c8f34-d047-4fb2-a639-dccbddcd2677" />


# Step 5 — Deploy the Code
- Replaced the default Lambda code with the following and click Deploy:

<img width="1600" height="848" alt="Screenshot (2049)" src="https://github.com/user-attachments/assets/25711e4b-44a9-4ce2-9f0d-21fd36976e3a" />


# Real Test (Upload an Image)

- Went to my S3 bucket
- Clicked Upload → select any .jpg or .png
- Clicked Upload
- Wait 15–30 seconds
- Went to Lambda → Monitor → View CloudWatch logs
- Open the latest log stream and look for:
  
<img width="1600" height="865" alt="Screenshot (2052)" src="https://github.com/user-attachments/assets/fd5456aa-0c68-4c95-9557-1d4a96d8bd97" />
<img width="1600" height="861" alt="Screenshot (2057)" src="https://github.com/user-attachments/assets/3b6cff45-45c9-424e-96d0-6f21aac3bc8f" />
<img width="1600" height="858" alt="Screenshot (2058)" src="https://github.com/user-attachments/assets/4d508945-68a4-414a-a905-4f8ed6246480" />
<img width="1597" height="868" alt="Screenshot (2060)" src="https://github.com/user-attachments/assets/12c0de94-e9d1-4623-85ce-2b705f77a71a" />

