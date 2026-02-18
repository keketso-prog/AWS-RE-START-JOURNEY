# Serverless Image Recognition on AWS

This project uses AWS to automatically look at an image and tell you what is in it.
You upload a photo, and the system figures out what it sees — like a dog, a car, or a tree.
No servers needed. It all runs on its own.



## What It Does

1. You upload a photo to Amazon S3 (cloud storage)
2. S3 notices the upload and tells Lambda to wake up
3. Lambda runs the Python code
4. The code sends the image to Amazon Rekognition (AWS AI service)
5. Rekognition looks at the photo and returns a list of labels
6. The labels get saved to CloudWatch so you can see them



## Services Used

- **Amazon S3** — stores the image
- **AWS Lambda** — runs the code automatically
- **Amazon Rekognition** — reads the image and finds what is in it
- **IAM** — gives Lambda permission to use S3 and Rekognition
- **CloudWatch** — shows the logs and results

## What the Results Look Like

Processing image: s3://my-bucket/portrait.jpg
Detected labels: ['Face', 'Head', 'Person', 'Photography', 'Portrait', 'Adult', 'Male', 'Man', 'Baby', 'Earring']


Rekognition looked at the photo and correctly identified that there was a person in it.
It also picked up smaller details like the earring and that a baby was in the image.
All of this happened automatically just from uploading the photo.



## My Results

- The function ran in 2.6 seconds
- No errors
- 100% success rate
- Used 91 MB of memory out of 128 MB available

## Problems I Ran Into

**No logs showing in CloudWatch**
The IAM role was missing the AWSLambdaBasicExecutionRole permission. Adding it fixed it.

**Labels not visible in the log**
The log only showed the END and REPORT lines. Had to click Load more at the top of the log stream to see the full output.


## What I Learned

- When you upload a file to S3, it can automatically trigger other AWS services
- Lambda lets you run code without setting up any servers
- Every AWS service needs permission to talk to another service through IAM
- CloudWatch stores everything your code prints, so you can check it later

## Built By

KEKE — AWS Cloud Project, February 2026
