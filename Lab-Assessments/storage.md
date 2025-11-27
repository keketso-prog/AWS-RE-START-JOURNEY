# STORAGE 182

under storage we have a few labs, i will share 2 labs i found intriguing

# FIRST LAB: Working with Amazon EBS

Objectives
By the end of this lab, you will be able to do the following:

Create an EBS volume.

Attach and mount an EBS volume to an EC2 instance.

Create a snapshot of an EBS volume.

Create an EBS volume from a snapshot.

THIS ARE THE STEPS I TOOK
# TASK 1:  Creating a new EBS volume
- Enter and choose EC2
- Choose Create volume
- In the Tags -optional section, choose Add tag, and configure the following options:

Key: Enter Name.

Value: Enter My Volume
-  Create volume

  # Task 2: Attaching the volume to an EC2 instance
  - Select My Volume
  - choose Attach volume.
  - choose the Lab instance.
  - Choose Attach volume.

# Task 3: Connecting to the Lab EC2 instance
- Enter and choose EC2
- choose Instances
- select the Lab instance
- select the Lab instance

# Task 4: Creating and configuring the file system
- view the storage
- create an ext3 file system on the new volume
- create a directory to mount the new storage volume
- mount the new volume
- view the configuration file
- view the available storage again
-  create a file and add some text on the mounted volume
-  verify that the text has been written to your volume

# Task 5: Creating an Amazon EBS snapshot
- choose Volumes, and select My Volume
- delete the file that you created on your volume
- verify that the file has been deleted

# Task 6: Restoring the Amazon EBS snapshot
# Task 6.1: Creating a volume by using the snapshot
- select My Snapshot
- In the Tags - optional section, choose Add tag, and then configure the following options:

Key: Enter Name.

Value: Enter Restored Volume.
- Create volume
- choose Volumes
  # Task 6.2: Attaching the restored volume to the EC2 instance
- Select Restored Volume
- choose Attach volume
- choose the Lab instance.
- Attach volume.
 
  # Task 6.3: Mounting the restored volume
- create a directory for mounting the new storage volume
- mount the new volume
- verify that the volume
 
  # WHAT I LEARNED
Here's what I learned from this lab:
- I made an EBS volume, which is like adding a new hard drive to my server in the cloud.
- I attached the EBS volume to an EC2 instance and mounted it so I could actually use it to store files.
- I created a snapshot of my EBS volume, which is basically a complete backup of all the data at that moment
- I learned how to create a brand new EBS volume from that snapshot, which is useful for copying data or recovering from problems
  # OVERALL
 I learned how to add storage to cloud servers, back it up, and restore it when needed - all the essential skills for managing data in AWS.

 # Lab complete 🎓

# SECOND LAB: Challenge Lab: Amazon S3 184

# Task 1: Connecting to the CLI Host instance
- Enter and choose EC2
- select the CLI Host instance
- Connect
- choose Connect

# Task 2: Configuring the AWS CLI
- At the prompts, copy the following values that you pasted into your text editor, and paste them into the terminal window as directed.

AWS Access Key ID: Enter the value for AccessKey.

AWS Secret Access Key: Enter the value for SecretKey.

Default region name: Enter us-west-2.

Default output format: Enter json

# Task 3: Finishing the challenge
- Create an S3 bucket. 

- Upload an object into this bucket.

- Try to access the object by using a web browser. 

- Make the object (not the bucket) publicly accessible.

- Access the object by using a web browser. 

- List the contents of the S3 bucket by using the AWS CLI. 

# WHAT I LEARNED
Here’s what I learned from this lab:
- I set up an S3 bucket, which works like creating a dedicated folder in the cloud for storing data.
- I uploaded an object into the bucket so I could store and manage data directly in S3.
- I learned how to open the object in a web browser, showing how S3 can be used to make files publicly accessible when needed
- I used the AWS CLI to list everything inside the S3 bucket, which is helpful for managing and checking files through the command line
# OVERALL
I learned how to create cloud storage, upload data, access it from the web, and manage it using the CLI — all essential skills for working with Amazon S3


 # Lab complete 🎓
