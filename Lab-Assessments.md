WEEK 1 LAB ASSESSMENTS

Had to make a lab that introduced me to Amazon EC2.
After doing the lab, the outcome was to learn the following
Launch a web server with termination protection enabled

- Monitor Your EC2 instance

- Modify the security group that your web server is using to allow HTTP access

- Resize your Amazon EC2 instance to scale

- Test termination protection

- Terminate your EC2 instance

  I had to start the lab
  Launch the instance on the EC2

  TASK 1 :
  LAUNCH EC2 INSTANCE
  
  Under task one i had to follow this steps below to get te required outcome

-  Name the instance
-  Choose an Amazon machine image
-  Choose an instance type
-  Configure a key pair
-  Configure the network settings
-  Add storage
-  Configure advanced network settings
-  Then finally launch the instance

  TASK 2 :
  MONITOR THE INSTANCE
  
  under task two, i had to do the following
  - Monitor and troubleshoot to get the this outcome
    THIS IS THE OUTCOME

    TASK 3 :
    UPDATE SECURITY RULES AND ACCESS THE WEB SERVER
    
    Under task three i had to do the following
    - Go to network & security
    - The select security groups
    - select inbound rules
    - Edit the rules with the following : - Type: HTTP      Source: Anywhere-IPv4
    - Save the rules and reload web server to see the desired outcome.
      THIS IS THE OUTCOME
   
    TASK 4 :
    RESIZE YOUR INSTANCE
    
    Under task four i had to do the following
    - Navigate to instance and select the web server you created
    - Select instance state > Stop instance
    - Instance must display stopped
    - Change the instance to t3.small under Actions tab
    - Resize volume under actions to 10
    The desired outcome must display the new changes i just did
     THIS IS THE OUTCOME

TASK 5:
TEST TERMINATION PROCESS

Under task five i had to do the following
- Navigate to instance, and then select the web server you just created
- Under instance menu select the termination delete tab
- Bescause he it did not work, go to actions > select instance setting > change protection then uncheck ENABLE
- Go to actions again instance state > terminate instance
  THIS IS THE OUTCOME

  
  
