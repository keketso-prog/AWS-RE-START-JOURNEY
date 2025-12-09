# Introduction to AWS Identity and Access Management (IAM) 

<img width="632" height="300" alt="Screenshot (1575)" src="https://github.com/user-attachments/assets/5081f0e6-1642-4f53-b116-69345038e426" />

I worked through a hands-on lab with AWS Identity and Access Management (IAM), learning how to create password policies, manage user groups, and test user permissions. Here's what I did.
# Task 1: Creating a Custom Password Policy
I navigated to IAM and selected "Account settings." I clicked "Change password policy" and configured:

- Minimum password length: 10 characters
- Selected all checkboxes except "Password expiration requires administrator reset"
- Password expiration: 90 days
- Prevent password reuse: 5 passwords


<img width="1554" height="740" alt="Screenshot (1578)" src="https://github.com/user-attachments/assets/4466af62-669b-48cb-a943-44f493b31555" />

# Task 2: Exploring Users and User Groups
I explored the existing IAM setup by viewing user-1's groups and security credentials. Then I examined three user groups and their permission policies:

- EC2-Support: Read-only EC2 access
- S3-Support: S3 access permissions
- EC2-Admin: Full EC2 administrative rights


<img width="1572" height="740" alt="Screenshot (1583)" src="https://github.com/user-attachments/assets/85d7a270-7fde-415f-a1ac-3cfc3287a98b" />
<img width="1571" height="743" alt="Screenshot (1585)" src="https://github.com/user-attachments/assets/84ed5b83-2eed-4ee2-9016-e3762c27fc47" />
<img width="1584" height="751" alt="Screenshot (1586)" src="https://github.com/user-attachments/assets/dafd5390-d74d-4f6d-9479-934d46e91346" />
<img width="1584" height="754" alt="Screenshot (1587)" src="https://github.com/user-attachments/assets/244313e0-e226-4dad-8e61-c1fd3d60c4de" />
<img width="1559" height="735" alt="Screenshot (1588)" src="https://github.com/user-attachments/assets/374cb2c5-bf1f-41bc-869c-b62dc890dcbb" />
<img width="1594" height="743" alt="Screenshot (1592)" src="https://github.com/user-attachments/assets/ef00ccba-f5e2-4500-b9bb-80e8d59b822d" />

# Task 3: Adding Users to User Groups
I assigned users to their groups:

- user-1 → S3-Support group
- user-2 → EC2-Support group
- user-3 → EC2-Admin group

<img width="1594" height="731" alt="Screenshot (1595)" src="https://github.com/user-attachments/assets/e4a2262d-d445-48fe-848d-b841d33bc6da" />
<img width="1590" height="737" alt="Screenshot (1598)" src="https://github.com/user-attachments/assets/951a9396-c3f3-41e5-adc7-823a9d2c54a9" />
<img width="1581" height="749" alt="Screenshot (1599)" src="https://github.com/user-attachments/assets/c9842e07-b94a-426b-ad8d-8ad72f8f80ed" />
<img width="1587" height="737" alt="Screenshot (1609)" src="https://github.com/user-attachments/assets/8977eae7-d5c0-45f6-ae31-ec6f4cc31c6b" />
<img width="1594" height="746" alt="Screenshot (1610)" src="https://github.com/user-attachments/assets/59d34a8e-d93e-4a49-8ac3-41b5e28d7b5d" />

# Task 4: Testing User Permissions
I copied the IAM Sign-in URL and tested each user in private windows:
- user-1: Successfully accessed S3 but couldn't access EC2.
- user-2: Accessed EC2 and viewed instances but couldn't stop them (read-only). Had no S3 access.
- user-3: Had full EC2 admin access and successfully stopped an instance.

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


