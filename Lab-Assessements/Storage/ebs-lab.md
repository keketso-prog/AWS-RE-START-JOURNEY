# Working with Amazon EBS

<img width="1600" height="861" alt="Screenshot (1749)" src="https://github.com/user-attachments/assets/a7dc80c1-a426-4744-9266-029a4fbb4f80" />

Objectives
- By the end of this lab, you will be able to do the following:
- Create an EBS volume.
- Attach and mount an EBS volume to an EC2 instance.
- Create a snapshot of an EBS volume.
- Create an EBS volume from a snapshot.

I worked through a hands-on lab with Amazon EBS volumes, learning how to create, attach, snapshot, and restore storage on AWS. Here's what I did.

# Task 1: Creating a New EBS Volume
I started by navigating to the EC2 service in my AWS Console. I clicked "Create volume" and added a tag to help me identify it later—I set the Key as "Name" and the Value as "My Volume." Then I created the volume.

<img width="1600" height="861" alt="Screenshot (1751)" src="https://github.com/user-attachments/assets/f249c1bf-1622-42cd-bc32-f95428b3a90a" />
<img width="1600" height="823" alt="Screenshot (1756)" src="https://github.com/user-attachments/assets/7b170471-f2ee-423e-be88-b2d31759809f" />

# Task 2: Attaching the Volume to My EC2 Instance

Once my volume was ready, I selected "My Volume" and clicked "Attach volume." I chose my Lab instance from the dropdown and confirmed the attachment.

<img width="1600" height="823" alt="Screenshot (1778)" src="https://github.com/user-attachments/assets/5d97a426-ba59-44e1-b326-29ac828b5528" />
<img width="1597" height="800" alt="Screenshot (1779)" src="https://github.com/user-attachments/assets/b100f948-88a1-41f1-b2b0-441f17954294" />

# Task 3: Connecting to My Lab EC2 Instance

I connected to my EC2 instance using SSH so I could work directly on the Linux system.

<img width="662" height="422" alt="Screenshot (1759)" src="https://github.com/user-attachments/assets/22903744-57d0-4afa-be25-75458499281e" />
<img width="770" height="415" alt="Screenshot (1762)" src="https://github.com/user-attachments/assets/6cc2450a-6055-4743-bd59-50fa03fb21f2" />
<img width="747" height="432" alt="Screenshot (1763)" src="https://github.com/user-attachments/assets/0d7ddcd4-7940-440a-a06f-2161523a854a" />

# Task 4: Creating and Configuring the File System

This is where things got technical.

- Viewed the existing storage to see what was available
- Created an ext3 file system on my new volume
- Created a directory to serve as the mount point
- Mounted the new volume to that directory
- Checked the configuration file to verify everything
- Viewed the available storage again to confirm the mount was successful
- Created a test file and added some text to it on the mounted volume
- Verified that the text was properly written to my volume

# Task 5: Creating an Amazon EBS Snapshot

I went back to the Volumes section and selected "My Volume." Then I deleted the file I had created on the volume and verified it was actually gone.

<img width="1600" height="823" alt="Screenshot (1767)" src="https://github.com/user-attachments/assets/9c446999-6b94-4b86-bc2c-27eb9486402e" />
<img width="1600" height="823" alt="Screenshot (1775)" src="https://github.com/user-attachments/assets/793dd118-41c4-4f57-8656-b3c588ac6138" />

# Task 6: Restoring the Amazon EBS Snapshot

- Task 6.1: Creating a Volume from the Snapshot
I selected "My Snapshot" and created a new volume from it. I tagged this one with the Key "Name" and Value "Restored Volume," then created the volume and navigated to the Volumes section.
- Task 6.2: Attaching the Restored Volume to My EC2 Instance
I selected "Restored Volume," clicked "Attach volume," chose my Lab instance, and attached it.
- Task 6.3: Mounting the Restored Volume
Finally, I created a new directory for mounting the restored volume, mounted it, and verified that everything was working correctly.

<img width="774" height="428" alt="Screenshot (1780)" src="https://github.com/user-attachments/assets/bd8801c4-dff9-4ab6-89a2-fba66d9ba2f3" />
<img width="754" height="405" alt="Screenshot (1781)" src="https://github.com/user-attachments/assets/3319671b-26cf-47b0-9396-37066294fd3a" />

# CHALLENGES
The only problem i encountered with this lab was the linux command line not out putting the desired outcomes.but i redid it till the required outcome was eventually showing.
  # WHAT I LEARNED
Here's what I learned from this lab:
- I made an EBS volume, which is like adding a new hard drive to my server in the cloud.
- I attached the EBS volume to an EC2 instance and mounted it so I could actually use it to store files.
- I created a snapshot of my EBS volume, which is basically a complete backup of all the data at that moment
- I learned how to create a brand new EBS volume from that snapshot, which is useful for copying data or recovering from problems
  # OVERALL
 I learned how to add storage to cloud servers, back it up, and restore it when needed - all the essential skills for managing data in AWS.

 # Lab complete 🎓


