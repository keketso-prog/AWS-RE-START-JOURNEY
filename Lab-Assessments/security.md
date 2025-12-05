## SECURITY
Under Security, we had a few labs to do. I will showcase 2 labs from this topic

## FIRST LAB: SECURITY-HARDENING
I worked through a hands-on lab with AWS Systems Manager Patch Manager, learning how to patch Linux and Windows instances, create custom baselines, and verify compliance. Here's what I did.
# Task 1: Patching Linux Instances with Default Baseline
I navigated to Systems Manager and selected Fleet Manager under Node Management. I checked the Linux-1 instance details, then went to Patch Manager and chose "Patch now." I configured the patching operation to scan and install with reboot if needed, targeting instances with the tag "Patch Group: LinuxProd." This patched my Linux instances using the default AWS baseline.
# Task 2: Creating a Custom Patch Baseline for Windows
In Patch Manager, I selected the "Patch baselines" tab and clicked "Create patch baseline." I named it "WindowsServerSecurityUpdates," set the operating system to Windows, and left it as a non-default baseline. Then I selected my new baseline, chose "Modify patch groups" from the Actions menu, and added "WindowsProd" as the patch group.
# Task 3: Tagging and Patching Windows Instances
I went to EC2 and tagged all three Windows instances (Windows-1, Windows-2, and Windows-3) with Key: "Patch Group" and Value: "WindowsProd." Then I returned to Patch Manager, clicked "Patch now," and configured it to scan and install patches on instances with the "Patch Group: WindowsProd" tag.
# Task 4: Verifying Patch Compliance
I checked the Compliance reporting tab in Patch Manager to verify that all my Linux and Windows instances were properly patched and compliant.
<img width="1600" height="900" alt="Screenshot (1461)" src="https://github.com/user-attachments/assets/f01575a7-e8d1-4286-9e3a-374480022415" />
<img width="1600" height="900" alt="Screenshot (1464)" src="https://github.com/user-attachments/assets/72ff8ce4-a783-43d9-9284-6991287ff723" />
<img width="1600" height="900" alt="Screenshot (1472)" src="https://github.com/user-attachments/assets/301f1cae-11a1-431b-9e69-1880486e2577" />
<img width="1600" height="900" alt="Screenshot (1473)" src="https://github.com/user-attachments/assets/2e4b49dd-536f-4761-b6cd-81091103686f" />
<img width="1600" height="900" alt="Screenshot (1476)" src="https://github.com/user-attachments/assets/48217750-4493-4439-84a4-7fd9931d9cbf" />
<img width="1600" height="900" alt="Screenshot (1478)" src="https://github.com/user-attachments/assets/b13b6b46-9ab3-4d4c-bd40-5f8da0a4d75c" />
<img width="1600" height="900" alt="Screenshot (1479)" src="https://github.com/user-attachments/assets/c044d76e-9feb-4d14-81af-2168c73aa449" />
<img width="1600" height="900" alt="Screenshot (1482)" src="https://github.com/user-attachments/assets/dd0cff7a-b3e0-4920-a1f5-f78ce4583b15" />
<img width="1600" height="900" alt="Screenshot (1483)" src="https://github.com/user-attachments/assets/59e0d40a-1d5c-4bce-912f-3cf317a0c1a9" />
<img width="1600" height="900" alt="Screenshot (1484)" src="https://github.com/user-attachments/assets/60cf30c5-90cc-4f87-b7ba-af8b9597c4f7" /> 
<img width="1600" height="900" alt="Screenshot (1486)" src="https://github.com/user-attachments/assets/f564420b-8b36-4daf-ab3c-1816e427bc2c" />

# CHALLENGES
Waiting for Completion: The patching process took longer than expected, especially for Windows instances. I had to refresh the compliance tab multiple times and be patient while patches installed and instances rebooted.


## WHAT I LEARNED
Here's what I learned from this lab:
- I learned how to use AWS Systems Manager to automatically patch Linux servers using Amazon's default security updates
- I figured out how to make a custom patch baseline, which lets me decide exactly which updates get installed and when
- I learned to use patch groups to manage Windows servers separately, so different groups can have different patching schedules and rules.
- I verified patch compliance to see which servers were properly updated and which ones might have missed patches
  # OVERALL
  I learned how to manage and automate security updates across multiple servers without having to manually update each one, and how to make sure everything stays secure and up-to-date
## Lab complete 🎓


## SECOND LAB: Introduction to AWS Identity and Access Management (IAM) 
I worked through a hands-on lab with AWS Identity and Access Management (IAM), learning how to create password policies, manage user groups, and test user permissions. Here's what I did.
# Task 1: Creating a Custom Password Policy
I navigated to IAM and selected "Account settings." I clicked "Change password policy" and configured:

- Minimum password length: 10 characters
- Selected all checkboxes except "Password expiration requires administrator reset"
- Password expiration: 90 days
- Prevent password reuse: 5 passwords

# Task 2: Exploring Users and User Groups
I explored the existing IAM setup by viewing user-1's groups and security credentials. Then I examined three user groups and their permission policies:

- EC2-Support: Read-only EC2 access
- S3-Support: S3 access permissions
- EC2-Admin: Full EC2 administrative rights

# Task 3: Adding Users to User Groups
I assigned users to their groups:

- user-1 → S3-Support group
- user-2 → EC2-Support group
- user-3 → EC2-Admin group

# Task 4: Testing User Permissions
I copied the IAM Sign-in URL and tested each user in private windows:
- user-1: Successfully accessed S3 but couldn't access EC2.
- user-2: Accessed EC2 and viewed instances but couldn't stop them (read-only). Had no S3 access.
- user-3: Had full EC2 admin access and successfully stopped an instance.


<img width="632" height="300" alt="Screenshot (1575)" src="https://github.com/user-attachments/assets/5081f0e6-1642-4f53-b116-69345038e426" />
<img width="1554" height="740" alt="Screenshot (1578)" src="https://github.com/user-attachments/assets/4466af62-669b-48cb-a943-44f493b31555" />
<img width="1572" height="740" alt="Screenshot (1583)" src="https://github.com/user-attachments/assets/85d7a270-7fde-415f-a1ac-3cfc3287a98b" />
<img width="1571" height="743" alt="Screenshot (1585)" src="https://github.com/user-attachments/assets/84ed5b83-2eed-4ee2-9016-e3762c27fc47" />
<img width="1584" height="751" alt="Screenshot (1586)" src="https://github.com/user-attachments/assets/dafd5390-d74d-4f6d-9479-934d46e91346" />
<img width="1584" height="754" alt="Screenshot (1587)" src="https://github.com/user-attachments/assets/244313e0-e226-4dad-8e61-c1fd3d60c4de" />
<img width="1559" height="735" alt="Screenshot (1588)" src="https://github.com/user-attachments/assets/374cb2c5-bf1f-41bc-869c-b62dc890dcbb" />
<img width="1594" height="743" alt="Screenshot (1592)" src="https://github.com/user-attachments/assets/ef00ccba-f5e2-4500-b9bb-80e8d59b822d" />
<img width="1594" height="731" alt="Screenshot (1595)" src="https://github.com/user-attachments/assets/e4a2262d-d445-48fe-848d-b841d33bc6da" />
<img width="1590" height="737" alt="Screenshot (1598)" src="https://github.com/user-attachments/assets/951a9396-c3f3-41e5-adc7-823a9d2c54a9" />
<img width="1581" height="749" alt="Screenshot (1599)" src="https://github.com/user-attachments/assets/c9842e07-b94a-426b-ad8d-8ad72f8f80ed" />
<img width="1587" height="737" alt="Screenshot (1609)" src="https://github.com/user-attachments/assets/8977eae7-d5c0-45f6-ae31-ec6f4cc31c6b" />
<img width="1594" height="746" alt="Screenshot (1610)" src="https://github.com/user-attachments/assets/59d34a8e-d93e-4a49-8ac3-41b5e28d7b5d" />
<img width="1587" height="749" alt="Screenshot (1615)" src="https://github.com/user-attachments/assets/d6d105bc-f45a-4b61-81a5-ea46d6164021" />
# CHALLENGES
Managing Multiple Browser Sessions: Testing three different users required opening multiple private windows and keeping track of different sign-in credentials. I accidentally signed in with the wrong user once and had to sign out and start over, which was a bit confusing at first.
# Summary of task 4
In this task, you were able to sign in as all three users. You verified that user-1 was able to view S3 buckets but unable to view EC2 instances. You then signed in as user-2 and verified that they were able to view EC2 instances but unable to perform the stop instance action. user-2 was also unable to view S3 buckets. After signing in as user-3, you were able to view EC2 instances and perform the stop instance action.
# WHAT I LEARNED
Here's what I learned from this lab:
- I created an IAM password policy that sets requirements like minimum length and complexity, so everyone has strong passwords
- I explored how IAM users and groups work, seeing how multiple users can be organized into groups instead of managing them individually.
- I looked at IAM policies to understand what permissions each group has and what they're allowed to do in AWS
-  I added users to different groups and saw how they instantly got all the permissions that group has
-   I found and used the special IAM sign-in URL to log in as regular users (not the root account)
-   I experimented by trying to access different AWS services with different users to see what they could and couldn't do based on their policies.

# OVERALL
I learned how to control who can access what in AWS, how to organize users efficiently, and how policies actually affect what people can do once they log in.Retry

 # Lab complete 🎓







