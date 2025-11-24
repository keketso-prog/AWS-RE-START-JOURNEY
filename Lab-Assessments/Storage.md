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
# TASK 1;  Creating a new EBS volume
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

#Task 4: Creating and configuring the file system
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

 # Lab complete
