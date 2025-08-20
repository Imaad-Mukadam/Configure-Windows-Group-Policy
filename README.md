# Configure-Windows-Group-Policy

## What is Group Policy?

Group Policy is a Windows Server feature that allows administrators to set rules and manage settings for users and computers in a network.

👉 With Group Policy, an admin can:

Block or allow access to Control Panel

Enforce password policies (length, complexity, expiry)

Restrict or allow software installations

Set desktop wallpaper or system configurations for all users

In this project, I configured Group Policy in Windows Server to manage user restrictions. First, I created two users and applied a domain-level policy to block the Control Panel. Then, I created an Organizational Unit (Demo OU) and moved one user into it. Finally, I linked the Group Policy to the OU, ensuring the restriction was applied only to that specific user. This project demonstrates practical skills in Active Directory management, Group Policy configuration, and policy scoping.

# Steps

1. First, I created two users in Active Directory to demonstrate this project.

![image alt](Images/1.PNG)

2. Next, I created an Organizational Unit, where I would later add a user and link the Group Policy.

![image alt](Images/2.PNG)

3. Now, I opened Group Policy Management to create a new Group Policy.

![image alt](Images/3.PNG)

4. Next, I right-clicked on the domain and created a new Group Policy, assigning it a name.

   ![image alt](Images/4.PNG)

5. The newly created policy is now visible with its assigned name.

![image alt](Images/5.PNG)

6. Now, right-click on the Group Policy that you created.

   ![image alt](Images/6.PNG)

7. Next, go to Administrative Templates and select Control Panel, as I will be blocking the Control Panel in this project.

   ![image alt](Images/7.PNG)

8. In the Control Panel settings, click on Prohibit access to Control Panel and PC settings

   ![image alt](Images/8.PNG)

9. Now, enable the setting, click Apply, and then OK. Your policy is now configured.

    ![image alt](Images/9.PNG)

10. Now, update the policy by running the gpupdate command.

    ![image alt](Images/10.PNG)

11. Now, when you try to open the Control Panel, it will be restricted because the policy is applied at the domain level. Next, we will apply it only to specific users.Here’s how we will do it

    ![image alt](Images/11.PNG)

12. Now, move the user into the Organizational Unit that we created in the beginning.

    ![image alt](Images/12.PNG)

13. In the Group Policy section, link the Group Policy to the Organizational Unit and remove the domain-level policy.

    ![image alt](Images/13.PNG)

14. You can now see that the policy is linked with the Organizational Unit.

    ![image alt](Images/14.PNG)

15. Now, when you try to open the Control Panel, it will open normally. However, the user added to the Organizational Unit will be restricted from accessing the Control Panel.

    ![image alt](Images/15.PNG)
