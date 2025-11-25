## SECURITY
Under Security, we had a few labs to do. I will showcase 2 labs from this topic

## FIRST LAB: SECURITY-HARDENING

Objectives
After completing this lab, you should be able to:

Patch Linux instances using default baseline

Create custom patch baseline 

Use patch groups to to patch Windows instances using custom patch baseline 

Verify patch compliance

STEPS ON HOW I DID THE LAB

# TASK 1  Patch Linux instances using default baselines

- Choose system manager

<img width="1600" height="900" alt="Screenshot (1460)" src="https://github.com/user-attachments/assets/f452f854-fe12-4e10-85e1-f43be0ad88c3" />

  
- In the left navigation pane, under Node Management, choose Fleet Manager

<img width="1600" height="900" alt="Screenshot (1461)" src="https://github.com/user-attachments/assets/f01575a7-e8d1-4286-9e3a-374480022415" />
  
- check Linux-1. Then choose the Node actions  dropdown list, and choose View details.
- View the details

  <img width="1600" height="900" alt="Screenshot (1462)" src="https://github.com/user-attachments/assets/38cd0141-9bb7-46c5-8375-86b1255bbb73" />

- choose AWS Systems Manager to go back to the Systems Manager homepage
- under Node Management, choose Patch Manager

<img width="1600" height="900" alt="Screenshot (1464)" src="https://github.com/user-attachments/assets/72ff8ce4-a783-43d9-9284-6991287ff723" />

- Choose Start with an overview
- Choose Patch now to patch the Linux instances with AWS-AmazonLinux2DefaultPatchBaseline.
- Under Basic configuration, configure as follows:

Patching operation:  Scan and install

Reboot option: Reboot if needed

Instances to patch: Patch only the target instances I specify

Target selection: Specify instance tags

Tag key:  Patch Group

Tag value: LinuxProd

Choose Add

<img width="1600" height="900" alt="Screenshot (1465)" src="https://github.com/user-attachments/assets/ef76ef19-08fc-444e-9e9b-40cf26465df8" />

<img width="1600" height="900" alt="Screenshot (1466)" src="https://github.com/user-attachments/assets/7842be4b-a261-4b28-97de-1381f775252b" />

<img width="1600" height="900" alt="Screenshot (1467)" src="https://github.com/user-attachments/assets/bb91351c-5abf-43ee-8f07-46115c854e4e" />

<img width="1600" height="900" alt="Screenshot (1468)" src="https://github.com/user-attachments/assets/7e18db90-4e14-48d7-94cb-5b1ef58b637b" />

<img width="1600" height="900" alt="Screenshot (1469)" src="https://github.com/user-attachments/assets/0020eba5-1365-4f6d-8379-6a53af58e379" />

# TASK 2 Create a custom patch baseline for Windows instances

- In the search bar at the top, enter Systems Manager
- under Node Management, choose Patch Manager.

  <img width="1600" height="900" alt="Screenshot (1472)" src="https://github.com/user-attachments/assets/301f1cae-11a1-431b-9e69-1880486e2577" />

  - Choose the Patch baselines tab
  - Choose the Create patch baseline button. 

For Patch baseline details, configure the following options:

For Name, enter WindowsServerSecurityUpdates

For Description - optional, enter Windows security baseline patch

For Operating system, choose Windows.

Leave the check box for Default patch baseline unselected.

<img width="1600" height="900" alt="Screenshot (1473)" src="https://github.com/user-attachments/assets/2e4b49dd-536f-4761-b6cd-81091103686f" />

<img width="1600" height="900" alt="Screenshot (1474)" src="https://github.com/user-attachments/assets/e9d6b0c3-fa86-43a9-bfc5-0716b8a293f8" />

<img width="1600" height="900" alt="Screenshot (1475)" src="https://github.com/user-attachments/assets/145397ec-2d66-4b39-a205-277034ce188b" />

 <img width="1600" height="900" alt="Screenshot (1476)" src="https://github.com/user-attachments/assets/48217750-4493-4439-84a4-7fd9931d9cbf" />

  - In the Patch baselines section, select the button for the WindowsServerSecurityUpdates patch
  - Choose the Actions dropdown list, and then choose Modify patch groups.
  - Modify patch groups section under Patch groups, enter WindowsProd 

<img width="1600" height="900" alt="Screenshot (1478)" src="https://github.com/user-attachments/assets/b13b6b46-9ab3-4d4c-bd40-5f8da0a4d75c" />

<img width="1600" height="900" alt="Screenshot (1479)" src="https://github.com/user-attachments/assets/c044d76e-9feb-4d14-81af-2168c73aa449" />

# TASK 3 Tagging Windows instances

- enter EC2 and select it
-Choose Instances, select the check box next to the Windows-1 instance, and then choose the Tags tab.
- Choose the Manage tags button, choose Add new tag, and configure the following options:

Key: Enter Patch Group

Value: Enter WindowsProd

Choose Save.

Repeat the previous steps to tag the Windows-2 and Windows-3 instances with the same tag

<img width="1600" height="900" alt="Screenshot (1481)" src="https://github.com/user-attachments/assets/8b60dbcc-6ab2-48fd-adb9-c8e9ce85d8af" />

<img width="1600" height="900" alt="Screenshot (1482)" src="https://github.com/user-attachments/assets/dd0cff7a-b3e0-4920-a1f5-f78ce4583b15" />

# Task 3.2: Patching Windows instances

- enter Systems Manager
- Choose Patch Manager
- hoose Patch now
- Patching operation:  Scan and install

Reboot option: Reboot if needed

Instances to patch: Patch only the target instances I specify

Target selection: Specify instance tags

Tag key:  Patch Group

Tag value: WindowsProd

Choose Add

Choose Patch now

<img width="1600" height="900" alt="Screenshot (1483)" src="https://github.com/user-attachments/assets/59e0d40a-1d5c-4bce-912f-3cf317a0c1a9" />

<img width="1600" height="900" alt="Screenshot (1484)" src="https://github.com/user-attachments/assets/60cf30c5-90cc-4f87-b7ba-af8b9597c4f7" />

# task 4

- under Node Management, choose Patch Manager
- hoose the Compliance reporting tab
  
- <img width="1600" height="900" alt="Screenshot (1486)" src="https://github.com/user-attachments/assets/f564420b-8b36-4daf-ab3c-1816e427bc2c" />

Conclusion
 Congratulations! You now have successfully:

Patched Linux instances using default baseline.

Created custom patch baseline.

Used patch groups to to patch Windows instances using custom patch baseline.

Verified patch compliance

## WHAT I LEARNED
Here's what I learned from this lab:
- I learned how to use AWS Systems Manager to automatically patch Linux servers using Amazon's default security updates
- I figured out how to make a custom patch baseline, which lets me decide exactly which updates get installed and when
- I learned to use patch groups to manage Windows servers separately, so different groups can have different patching schedules and rules.
- I verified patch compliance to see which servers were properly updated and which ones might have missed patches
  # OVERALL
  I learned how to manage and automate security updates across multiple servers without having to manually update each one, and how to make sure everything stays secure and up-to-date
## Lab complete 🎓


## SECOND LAB: Introduction to AWS Identity and Access Management (IAM) 279

Objectives
After completing this lab, you should be able to:

Create and apply an IAM password policy
Explore pre-created IAM users and user groups
Inspect IAM policies as applied to the pre-created user groups
Add users to user groups with specific capabilities active
Locate and use the IAM sign-in URL
Experiment with the effects of policies on service access

<img width="632" height="300" alt="Screenshot (1575)" src="https://github.com/user-attachments/assets/5081f0e6-1642-4f53-b116-69345038e426" />


# TASK 1: Create an account password policy

- create a custom password policy for your AWS account
- enter IAM
- In the left navigation pane, choose Account settings
- Choose Change password policy
- Under Select your account password policy requirements, configure the following options:

- For Enforce minimum password length, change 8 to 10 characters.
- Select every check box except the check box for Password expiration requires administrator reset.
- For Enable password expiration, leave the default option of 90 days. 
-For Prevent password reuse, leave the default option of 5 passwords.
- Choose Save changes.

<img width="1569" height="740" alt="Screenshot (1577)" src="https://github.com/user-attachments/assets/a88acf9b-5365-4908-a3a8-681f434815e6" />

<img width="1600" height="900" alt="Screenshot (1478)" src="https://github.com/user-attachments/assets/9bbdcb68-d7b2-4c0f-9f99-6cc23734eba8" />


# TASK 2: Explore users and user groups
- In the left navigation pane, choose Users.
- Choose user-1
- Choose the Groups tab
- Choose the Security credentials tab
- In the left navigation pane, choose User groups
- Choose the EC2-Support group.

- Choose the Permissions tab
- Under Actions, choose the Show Policy link
- choose User groups
- Choose the S3-Support group
- From the Actions menu, choose the Show Policy link.

- choose User groups
- Choose the EC2-Admin group
- choose Show Policy to view the policy

<img width="1554" height="740" alt="Screenshot (1578)" src="https://github.com/user-attachments/assets/4466af62-669b-48cb-a943-44f493b31555" />

<img width="1575" height="734" alt="Screenshot (1579)" src="https://github.com/user-attachments/assets/dd0ec59f-ee75-4704-9343-350f9a6071bf" />

<img width="1569" height="735" alt="Screenshot (1580)" src="https://github.com/user-attachments/assets/d47670e1-3a29-42f0-8089-23ef3d23b02e" />

<img width="1581" height="737" alt="Screenshot (1581)" src="https://github.com/user-attachments/assets/8008167c-5540-41b1-8cb9-963e632cd939" />

<img width="1588" height="746" alt="Screenshot (1582)" src="https://github.com/user-attachments/assets/aa393ca7-ff5c-440d-9ea1-c03ad519de8c" />

<img width="1572" height="740" alt="Screenshot (1583)" src="https://github.com/user-attachments/assets/85d7a270-7fde-415f-a1ac-3cfc3287a98b" />

<img width="1581" height="737" alt="Screenshot (1584)" src="https://github.com/user-attachments/assets/1a38d5c9-0cc2-4872-ace8-aa6b4ecce88f" />

<img width="1571" height="743" alt="Screenshot (1585)" src="https://github.com/user-attachments/assets/84ed5b83-2eed-4ee2-9016-e3762c27fc47" />

<img width="1584" height="751" alt="Screenshot (1586)" src="https://github.com/user-attachments/assets/dafd5390-d74d-4f6d-9479-934d46e91346" />

<img width="1584" height="754" alt="Screenshot (1587)" src="https://github.com/user-attachments/assets/244313e0-e226-4dad-8e61-c1fd3d60c4de" />

<img width="1559" height="735" alt="Screenshot (1588)" src="https://github.com/user-attachments/assets/374cb2c5-bf1f-41bc-869c-b62dc890dcbb" />

<img width="1594" height="749" alt="Screenshot (1589)" src="https://github.com/user-attachments/assets/c3eeff0e-ed82-4aae-957a-d76a6efa93cc" />


# TASK 3: Add users to user groups
- choose User groups.
- Choose the S3-Support group.
- Choose the Users tab
- choose Add users
- In the Add users to S3-Support window, configure the following options:

<img width="1588" height="749" alt="Screenshot (1590)" src="https://github.com/user-attachments/assets/3f8ca987-4317-4ee2-a9d4-91857a2e26f5" />

<img width="1584" height="740" alt="Screenshot (1591)" src="https://github.com/user-attachments/assets/ce2e3fca-0579-4b0b-9124-03351c2b8c38" />

<img width="1594" height="743" alt="Screenshot (1592)" src="https://github.com/user-attachments/assets/ef00ccba-f5e2-4500-b9bb-80e8d59b822d" />


Select the check box for user-1.
Choose Add Users.
- add user-2 to the EC2-Support group.

<img width="1600" height="746" alt="Screenshot (1593)" src="https://github.com/user-attachments/assets/220cdfd0-3026-477a-a852-d4f7b014a745" />

<img width="1584" height="746" alt="Screenshot (1594)" src="https://github.com/user-attachments/assets/e2337eb5-584d-4c4f-b4b0-d46361a2c4f5" />

<img width="1594" height="731" alt="Screenshot (1595)" src="https://github.com/user-attachments/assets/e4a2262d-d445-48fe-848d-b841d33bc6da" />

  
- add user-3 to the EC2-Admin group

<img width="1587" height="737" alt="Screenshot (1596)" src="https://github.com/user-attachments/assets/425bb63c-6ea2-466f-9d94-f034dbccdf11" />

<img width="1600" height="746" alt="Screenshot (1597)" src="https://github.com/user-attachments/assets/9f7cd270-afee-4666-a918-6ec154ecbbbb" />

<img width="1590" height="737" alt="Screenshot (1598)" src="https://github.com/user-attachments/assets/951a9396-c3f3-41e5-adc7-823a9d2c54a9" />

-  choose User groups

<img width="1581" height="749" alt="Screenshot (1599)" src="https://github.com/user-attachments/assets/c9842e07-b94a-426b-ad8d-8ad72f8f80ed" />

  
# TASK 4: Sign in and test user permissions

- In the left navigation pane, choose Dashboard.
- Copy the Sign-in URL for IAM users in this account
- Open a private window
- Paste the Sign-in URL for IAM users in this account
-  Sign in

- choose S3.
-  choose EC2
-  Sign user-1 out of the AWS Management Console
-  Sign out.
-  Paste the Sign-in URL for IAM users in this account
-  Sign in using the following credentials:

<img width="1600" height="900" alt="Screenshot (1601)" src="https://github.com/user-attachments/assets/4ea8e86e-ab12-4fc7-b6ec-976a373cff62" />

<img width="1600" height="900" alt="Screenshot (1605)" src="https://github.com/user-attachments/assets/3b5ff11a-b1d0-4bfc-a09a-6f5412dfe071" />

<img width="1600" height="900" alt="Screenshot (1606)" src="https://github.com/user-attachments/assets/37a8ddd2-7276-4570-8d4e-0a75588ef9a2" />
  

IAM user name: Enter user-2
Password: Enter Lab-Password2
- Choose Sign in.
- choose EC2
- choose Instances
- choose Stop instance.
- choose Stop
- choose Cancel
- choose S3
- Sign user-2 out of the AWS Management Console by following these steps:

At the top of the screen, choose user-2.
Choose Sign out.

<img width="1600" height="900" alt="Screenshot (1607)" src="https://github.com/user-attachments/assets/c229328b-faaf-44d9-8291-f8c508b61960" />

<img width="1587" height="737" alt="Screenshot (1609)" src="https://github.com/user-attachments/assets/8977eae7-d5c0-45f6-ae31-ec6f4cc31c6b" />

<img width="1594" height="746" alt="Screenshot (1610)" src="https://github.com/user-attachments/assets/59d34a8e-d93e-4a49-8ac3-41b5e28d7b5d" />


- Paste the Sign-in URL for IAM users in this account
- Sign in using the following credentials:

IAM user name: Enter user-3
Password: Enter Lab-Password3
- Choose Sign in
- choose EC2
- choose Instances.
- As an EC2 administrator,I now have permissions to stop the EC2 instance.
- choose Stop instance.
- choose Stop

<img width="1587" height="852" alt="Screenshot (1612)" src="https://github.com/user-attachments/assets/bfc3b645-43ef-41ee-a856-c94d0ebe99dc" />

<img width="1584" height="819" alt="Screenshot (1613)" src="https://github.com/user-attachments/assets/50cb910e-c31a-48b2-a2b7-e8c14ee8bf7f" />

 <img width="1587" height="728" alt="Screenshot (1614)" src="https://github.com/user-attachments/assets/af531b54-8381-46c5-9a4c-3e552687f33c" />
 
<img width="1587" height="749" alt="Screenshot (1615)" src="https://github.com/user-attachments/assets/d6d105bc-f45a-4b61-81a5-ea46d6164021" />

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







