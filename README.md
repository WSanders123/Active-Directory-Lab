# Active-Directory-Lab

Goals: Set up a Windows Server with Active Directory, user accounts, groups, and policies

I am going to show my thought process in this lab

Step 1: To make this lab possible you need to download virtualbox and you need to download windows server 2022 ISO file. After you download virtualbox, you have to drag the iso file into the virtualbox interface and it will be installed into virtual box.
The settings i went was 4GB Ram, 2 CPUs, and 60GB of disk space.

You will need to make sure you are downloading the right windows server 2022 iso, because i originally downloaded the core iso and it only showed the command line.
(should look like this)

![image](https://github.com/user-attachments/assets/12e68558-c789-4fdf-aa96-85cc6893aefb)


![image](https://github.com/user-attachments/assets/cd2d8653-deba-416e-b49e-33810364cc3c)

You can see it is downloaded and showing here.

After opening it up and configuring the settings, you should get the administrator, you can make any password then it should be done. The screen should look like this when you open it up

![image](https://github.com/user-attachments/assets/497fcd15-cde3-4d19-af40-dfb63b0f069a)

Next you will log in with the password you chose, when you successfully logged in, the first thing that will popup is server manager. 

![image](https://github.com/user-attachments/assets/d5a8145d-189e-47ba-9d72-0d2ee89237cf)

Step 2: Install Active Directory Domain Services AD DS.

Active Directory is a very powerful tool that allows you to manage users, groups, and access. Server Manager allows you to create these roles and Active Directory helps manage access to the roles.

We are going to make roles where we can access them through the the Active Directory. First we click on Manage and then click on Add Roles and Features.

![image](https://github.com/user-attachments/assets/405de0c5-67ea-4afe-a3c4-b639d1a65d61)

When you install it make sure that it says Role-Based.

![image](https://github.com/user-attachments/assets/557f4a29-627d-4d74-9bca-2e1d3dc24850)

After you click install, the flag next to the Manage Tab should light up.

![image](https://github.com/user-attachments/assets/9ac017a8-6275-4b17-936d-2aba228d7e60)

I already did it so you dont see it but, after that you click on the flag and it should say promote this server to a domain controller, you click on that.
Then you choose add a forest name, it can be anything and then once you click everything your windows will reset. You will know you did everything right when you see this.

![image](https://github.com/user-attachments/assets/243719b8-e79d-4ea2-a8e5-c58812828423)

Originally there was only 1 role, now there is 3 roles here.

![image](https://github.com/user-attachments/assets/e568cd23-922b-47c5-b82b-e5436a7fb5ca)

Step 3: Create Users and Groups in the Active Directory

So now we will be creating the users and the groups in Active Directory. 




