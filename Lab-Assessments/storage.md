# STORAGE 

Under storage we have a few labs, i will share 2 labs i found intriguing

# FIRST LAB: Working with Amazon EBS

Objectives
By the end of this lab, you will be able to do the following:

Create an EBS volume.

Attach and mount an EBS volume to an EC2 instance.

Create a snapshot of an EBS volume.

Create an EBS volume from a snapshot.

<img width="1600" height="861" alt="Screenshot (1749)" src="https://github.com/user-attachments/assets/a7dc80c1-a426-4744-9266-029a4fbb4f80" />


THIS ARE THE STEPS I TOOK
# TASK 1:  Creating a new EBS volume
- Enter and choose EC2
- Choose Create volume
- In the Tags -optional section, choose Add tag, and configure the following options:

Key: Enter Name.

Value: Enter My Volume
-  Create volume

  <img width="1600" height="861" alt="Screenshot (1751)" src="https://github.com/user-attachments/assets/f249c1bf-1622-42cd-bc32-f95428b3a90a" />

<img width="1594" height="858" alt="Screenshot (1752)" src="https://github.com/user-attachments/assets/d225abe8-43b8-4b7b-975f-87167b0ce1e7" />

<img width="1600" height="819" alt="Screenshot (1753)" src="https://github.com/user-attachments/assets/6f66cb5d-33e7-48cf-9498-6ded4ab568d2" />


  # Task 2: Attaching the volume to an EC2 instance
  - Select My Volume
  - choose Attach volume.
  - choose the Lab instance.
  - Choose Attach volume.

 <img width="1600" height="845" alt="Screenshot (1754)" src="https://github.com/user-attachments/assets/1d6c9cfe-830c-4f3e-b7dd-308025cc664f" />

<img width="1597" height="858" alt="Screenshot (1755)" src="https://github.com/user-attachments/assets/90aa889b-749d-4749-a3db-4ed65423b953" />

<img width="1600" height="823" alt="Screenshot (1756)" src="https://github.com/user-attachments/assets/7b170471-f2ee-423e-be88-b2d31759809f" />


# Task 3: Connecting to the Lab EC2 instance
- CONNECTED TO THE EC2 via SSH

<img width="447" height="441" alt="Screenshot (1783)" src="https://github.com/user-attachments/assets/60bfa20a-694a-4c9d-9714-0d6213f86ed6" />

<img width="666" height="419" alt="Screenshot (1784)" src="https://github.com/user-attachments/assets/14deed0a-1063-428d-904c-def45caab57d" />

<img width="655" height="412" alt="Screenshot (1785)" src="https://github.com/user-attachments/assets/f94fc40f-2dea-4111-bb06-2dc95560301b" />


# Task 4: Creating and configuring the file system
- view the storage
- create an ext3 file system on the new volume
- create a directory to mount the new storage volume
- mount the new volume
- view the configuration file
- view the available storage again
-  create a file and add some text on the mounted volume
-  verify that the text has been written to your volume

<img width="662" height="422" alt="Screenshot (1759)" src="https://github.com/user-attachments/assets/22903744-57d0-4afa-be25-75458499281e" />

<img width="756" height="439" alt="Screenshot (1760)" src="https://github.com/user-attachments/assets/33f3b101-5405-4199-b531-5237918fd1b3" />

<img width="764" height="455" alt="Screenshot (1761)" src="https://github.com/user-attachments/assets/310466a6-7711-493e-aece-56e6063720e1" />

<img width="770" height="415" alt="Screenshot (1762)" src="https://github.com/user-attachments/assets/6cc2450a-6055-4743-bd59-50fa03fb21f2" />

<img width="747" height="432" alt="Screenshot (1763)" src="https://github.com/user-attachments/assets/0d7ddcd4-7940-440a-a06f-2161523a854a" />

<img width="769" height="419" alt="Screenshot (1764)" src="https://github.com/user-attachments/assets/a226dfac-be61-48b6-b2a7-04ab14c31fe8" />

<img width="776" height="423" alt="Screenshot (1765)" src="https://github.com/user-attachments/assets/1400bd40-b1b7-4c41-9125-62a51c87abaa" />

# Task 5: Creating an Amazon EBS snapshot
- choose Volumes, and select My Volume
- delete the file that you created on your volume
- verify that the file has been deleted
  
 <img width="1600" height="819" alt="Screenshot (1766)" src="https://github.com/user-attachments/assets/4445a255-0579-4e37-95ba-c4844809c89f" />

<img width="1600" height="823" alt="Screenshot (1767)" src="https://github.com/user-attachments/assets/9c446999-6b94-4b86-bc2c-27eb9486402e" />

<img width="1584" height="813" alt="Screenshot (1768)" src="https://github.com/user-attachments/assets/3c904661-1e76-4c0b-85a0-46cf2dcd564d" />

<img width="1587" height="826" alt="Screenshot (1769)" src="https://github.com/user-attachments/assets/7f1865e5-5566-4a63-8d1e-6249fdc6cb38" />

<img width="770" height="420" alt="Screenshot (1770)" src="https://github.com/user-attachments/assets/761a32d2-dc2c-4bee-8f8f-bc0f9be75f58" />



# Task 6: Restoring the Amazon EBS snapshot
# Task 6.1: Creating a volume by using the snapshot
- select My Snapshot
- In the Tags - optional section, choose Add tag, and then configure the following options:

Key: Enter Name.

Value: Enter Restored Volume.
- Create volume
- choose Volumes

<img width="1600" height="816" alt="Screenshot (1772)" src="https://github.com/user-attachments/assets/8215ab51-bafe-431b-a873-df7b83f6e934" />

  # Task 6.2: Attaching the restored volume to the EC2 instance
- Select Restored Volume
- choose Attach volume
- choose the Lab instance.
- Attach volume.

<img width="1600" height="826" alt="Screenshot (1773)" src="https://github.com/user-attachments/assets/d9485041-815a-4bc7-8a90-07f93fa2e52f" />

<img width="1600" height="819" alt="Screenshot (1774)" src="https://github.com/user-attachments/assets/13852a49-7ffd-4dcc-8fa3-5197047e53fb" />

<img width="1600" height="823" alt="Screenshot (1775)" src="https://github.com/user-attachments/assets/793dd118-41c4-4f57-8656-b3c588ac6138" />

<img width="1597" height="819" alt="Screenshot (1776)" src="https://github.com/user-attachments/assets/ea968577-7b63-43e5-91af-68bbec99ab65" />

<img width="1600" height="823" alt="Screenshot (1777)" src="https://github.com/user-attachments/assets/31317094-63a5-4acd-9187-03b1a9cc270d" />

<img width="1600" height="823" alt="Screenshot (1778)" src="https://github.com/user-attachments/assets/5d97a426-ba59-44e1-b326-29ac828b5528" />

<img width="1597" height="800" alt="Screenshot (1779)" src="https://github.com/user-attachments/assets/b100f948-88a1-41f1-b2b0-441f17954294" />

  # Task 6.3: Mounting the restored volume
- create a directory for mounting the new storage volume
- mount the new volume
- verify that the volume

<img width="774" height="428" alt="Screenshot (1780)" src="https://github.com/user-attachments/assets/bd8801c4-dff9-4ab6-89a2-fba66d9ba2f3" />

<img width="754" height="405" alt="Screenshot (1781)" src="https://github.com/user-attachments/assets/3319671b-26cf-47b0-9396-37066294fd3a" />


  # WHAT I LEARNED
Here's what I learned from this lab:
- I made an EBS volume, which is like adding a new hard drive to my server in the cloud.
- I attached the EBS volume to an EC2 instance and mounted it so I could actually use it to store files.
- I created a snapshot of my EBS volume, which is basically a complete backup of all the data at that moment
- I learned how to create a brand new EBS volume from that snapshot, which is useful for copying data or recovering from problems
  # OVERALL
 I learned how to add storage to cloud servers, back it up, and restore it when needed - all the essential skills for managing data in AWS.

 # Lab complete 🎓

# SECOND LAB: Challenge Lab: Amazon S3 

# Task 1: Connecting to the CLI Host instance
- Connected to EC2 instance via SSH

# Task 2: Configuring the AWS CLI
- At the prompts, copy the following values that you pasted into your text editor, and paste them into the terminal window as directed.

AWS Access Key ID: Enter the value for AccessKey.

AWS Secret Access Key: Enter the value for SecretKey.

Default region name: Enter us-west-2.

Default output format: Enter json

<img width="447" height="441" alt="Screenshot (1783)" src="https://github.com/user-attachments/assets/60bfa20a-694a-4c9d-9714-0d6213f86ed6" />

<img width="666" height="419" alt="Screenshot (1784)" src="https://github.com/user-attachments/assets/14deed0a-1063-428d-904c-def45caab57d" />

<img width="655" height="412" alt="Screenshot (1785)" src="https://github.com/user-attachments/assets/f94fc40f-2dea-4111-bb06-2dc95560301b" />

# Task 3: Finishing the challenge
- Create an S3 bucket. 


<img width="1600" height="823" alt="Screenshot (1786)" src="https://github.com/user-attachments/assets/9b264efd-7d89-481b-9c25-380d11a7ac82" />

<img width="1594" height="823" alt="Screenshot (1787)" src="https://github.com/user-attachments/assets/d9f3d306-dfcb-4bdd-b677-455c70478948" />

<img width="1590" height="819" alt="Screenshot (1788)" src="https://github.com/user-attachments/assets/ec9d69bd-4849-406f-bd7e-2f3a88e16540" />

<img width="1594" height="823" alt="Screenshot (1789)" src="https://github.com/user-attachments/assets/3e513cdc-b9ec-4aca-af0a-808efb382b36" />


- Upload an object into this bucket.


<img width="1584" height="823" alt="Screenshot (1791)" src="https://github.com/user-attachments/assets/677c979b-22b9-4330-86b1-39b335c1af0e" />

<img width="1590" height="819" alt="Screenshot (1792)" src="https://github.com/user-attachments/assets/f7e7b26d-457b-43a9-9736-cc506d5ce5ae" />

<img width="1594" height="823" alt="Screenshot (1793)" src="https://github.com/user-attachments/assets/8a4449bb-2bd5-4fe7-8fd7-6a0c39559e59" />

<img width="1590" height="819" alt="Screenshot (1794)" src="https://github.com/user-attachments/assets/e1acac76-c7c1-433f-94f0-5c4d683baf46" />

- List the contents of the S3 bucket by using the AWS CLI. 

<img width="660" height="406" alt="Screenshot (1799)" src="https://github.com/user-attachments/assets/b24529d5-fb4f-4695-8097-6fc5cf6288bc" />

<img width="655" height="424" alt="Screenshot (1801)" src="https://github.com/user-attachments/assets/4de20839-64d4-450a-95a7-8f84822eb893" />

<img width="664" height="428" alt="Screenshot (1803)" src="https://github.com/user-attachments/assets/374e3708-4102-4671-9e83-461894cdf427" />

<img width="664" height="419" alt="Screenshot (1804)" src="https://github.com/user-attachments/assets/0f019164-679b-4f69-8ce8-962aae63ebff" />

<img width="666" height="419" alt="Screenshot (1805)" src="https://github.com/user-attachments/assets/36230039-0a24-472e-8133-95a4367e2ebf" />

<img width="661" height="415" alt="Screenshot (1807)" src="https://github.com/user-attachments/assets/2cafcf71-dacd-4a88-9b09-d3adce76c7f4" />

<img width="648" height="415" alt="Screenshot (1808)" src="https://github.com/user-attachments/assets/a8360baf-c7d7-4887-ae3c-09546c77dba4" />

<img width="664" height="419" alt="Screenshot (1809)" src="https://github.com/user-attachments/assets/8b34635e-14dc-476b-b963-a141fb18fb2b" />

- Use the command line to view the contents of the s3

  <img width="654" height="406" alt="Screenshot (1811)" src="https://github.com/user-attachments/assets/f2a397cf-a81e-4b54-87e9-af5517e0d11e" />

- Access the object by using a web browser.

<img width="1590" height="868" alt="Screenshot (1810)" src="https://github.com/user-attachments/assets/477aab86-a92f-4158-9659-92e2ca988f1b" />

  
# WHAT I LEARNED
Here’s what I learned from this lab:
- I set up an S3 bucket, which works like creating a dedicated folder in the cloud for storing data.
- I uploaded an object into the bucket so I could store and manage data directly in S3.
- I learned how to open the object in a web browser, showing how S3 can be used to make files publicly accessible when needed
- I used the AWS CLI to list everything inside the S3 bucket, which is helpful for managing and checking files through the command line
# OVERALL
I learned how to create cloud storage, upload data, access it from the web, and manage it using the CLI — all essential skills for working with Amazon S3


 # Lab complete 🎓
