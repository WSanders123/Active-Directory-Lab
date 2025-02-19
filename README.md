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

So now we will be creating the users and the groups in Active Directory. This will be crucial for who can access what on the network and thats only one feature it offers. Go to Active Directory Users and Computers on your server inside the Virtualboux

![image](https://github.com/user-attachments/assets/fa408970-fdf7-4781-88f6-c71787983a40)

This should show up when you click on it.

![image](https://github.com/user-attachments/assets/f53e5663-e28a-4b5f-b0e8-e1c400142b0c)

We will be creating some users on the network. Click create user in the task bar and give them a first and last name, and then give them a password (if your password isnt complex enough it will reject it).

![image](https://github.com/user-attachments/assets/5dbe9aaa-e896-45ab-8973-3d343c714ab2)

As you can see i created the user. Make 2 of them or however many you want.

![image](https://github.com/user-attachments/assets/cfa0020c-abe6-4a6c-a03e-f759f443c4fc)

Now do the same for groups, there is a create group button and for this lab i chose to just make the 3 most common groups i could think of (HR, It Support, It Manager)

![image](https://github.com/user-attachments/assets/154210bc-0017-4656-9abe-a05d4736c5ca)

I now got my 3 groups

![image](https://github.com/user-attachments/assets/a9748bef-96e9-45e9-88aa-a38f180255eb)

Now here comes the fun part, in It roles, users are link to specific roles they play in the network. For this im going to set, my first user Billy Brown as a It Manager and Sarah Matthew as It Support. To do that im going to click on It Manager and then members then i click Add, Search for Billy Brown, and then its done. You should see this here if you did it right.

![image](https://github.com/user-attachments/assets/40b32e06-635c-470b-aa15-07b0da03542a)

I just got done moving my users to their roles now i am going to log into the users i created. Since i kept the user having to make a new password when they log in for the first time, it shows this screen.

![image](https://github.com/user-attachments/assets/7c70ec73-061c-4546-aab2-bf3009de7bac)

Step 4: Implement a Group Policy

Group Policies are very useful for enforcing rules for the users. The way how i did this was, i went to group policy managment, went to the domain i made then i right clicked on it to create a new Group Policy.

![image](https://github.com/user-attachments/assets/42703ed5-1d84-4e90-ade4-4a48afc62a18)

What i ended up doing was making it so passwords need to be 10 characters long, i went to my policy and edited it. I went from Computer Configuration -> Policies -> Windows Settings -> Security Settings -> Account Policies -> Password Policy -> and then i changed the mimimum password length to 10 characters.

![image](https://github.com/user-attachments/assets/ca5bd56b-e73f-4ea5-a479-dcbf7082a7bc)

The Changed One

![image](https://github.com/user-attachments/assets/c0a24e36-9c24-43cb-a02b-9f925502d109)

After i made a new policy i went to the command line and made sure it was applied to the systems. The way how i did it was, in the cmd: gpupdate /force

![image](https://github.com/user-attachments/assets/273282d3-d5ea-45c3-af5c-d0ac4fa14b1b)

As you can see it says Policy update successful.

I just logged into Billy Brown, Here is what it looks like

![image](https://github.com/user-attachments/assets/4aa1ac1a-d97c-4e32-92d4-1cf1c4843a6b)

After Step 3: i tried to log in and i could not log in to the user, and i had to go through a lot of troubleshooting, i ended up finding out the issue was because i didnt set the group policy to allow the user to log in on the same device and oh boy im glad i figured it out. 

Summary: Throughout this lab i figured out how to make users, how to make groups, how to reset passwords, how to set password rules, how to classify the users on the machine, and many more things. Im glad that i spent time on this and yeah im ready to keep learning more, thanks for reading this if you got this far.













