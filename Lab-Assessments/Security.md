Under Security, we had a few labs to do. I will showcase 2 labs from this topic

SECURITY-HARDENING

Objectives
After completing this lab, you should be able to:

Patch Linux instances using default baseline

Create custom patch baseline 

Use patch groups to to patch Windows instances using custom patch baseline 

Verify patch compliance

STEPS ON HOW I DID THE LAB

TASK 1  Patch Linux instances using default baselines

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

TASK 2 Create a custom patch baseline for Windows instances

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

<img width="1600" height="900" alt="Screenshot (1475)" src="https://github.com/user-attachments/assets/145397ec-2d66-4b39-a205-277034ce188b" 

  <img width="1600" height="900" alt="Screenshot (1476)" src="https://github.com/user-attachments/assets/48217750-4493-4439-84a4-7fd9931d9cbf" />

  - In the Patch baselines section, select the button for the WindowsServerSecurityUpdates patch
  - Choose the Actions dropdown list, and then choose Modify patch groups.
  - Modify patch groups section under Patch groups, enter WindowsProd 

<img width="1600" height="900" alt="Screenshot (1478)" src="https://github.com/user-attachments/assets/b13b6b46-9ab3-4d4c-bd40-5f8da0a4d75c" />

<img width="1600" height="900" alt="Screenshot (1479)" src="https://github.com/user-attachments/assets/c044d76e-9feb-4d14-81af-2168c73aa449" />

TASK 3 Tagging Windows instances

- enter EC2 and select it
-Choose Instances, select the check box next to the Windows-1 instance, and then choose the Tags tab.
- Choose the Manage tags button, choose Add new tag, and configure the following options:

Key: Enter Patch Group

Value: Enter WindowsProd

Choose Save.

Repeat the previous steps to tag the Windows-2 and Windows-3 instances with the same tag

<img width="1600" height="900" alt="Screenshot (1481)" src="https://github.com/user-attachments/assets/8b60dbcc-6ab2-48fd-adb9-c8e9ce85d8af" />

<img width="1600" height="900" alt="Screenshot (1482)" src="https://github.com/user-attachments/assets/dd0cff7a-b3e0-4920-a1f5-f78ce4583b15" />

Task 3.2: Patching Windows instances

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

task 4

- under Node Management, choose Patch Manager
- hoose the Compliance reporting tab
  
- <img width="1600" height="900" alt="Screenshot (1486)" src="https://github.com/user-attachments/assets/f564420b-8b36-4daf-ab3c-1816e427bc2c" />

Conclusion
 Congratulations! You now have successfully:

Patched Linux instances using default baseline.

Created custom patch baseline.

Used patch groups to to patch Windows instances using custom patch baseline.

Verified patch compliance

Lab complete














