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
