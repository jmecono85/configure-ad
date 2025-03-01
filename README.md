<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1 Create the Domain Controller VM (Windows Server 2022) named “DC-1” 
- Step 2 After VM is created, set Domain Controller’s NIC Private IP address to be static.
- Log into the  DC-1 VM and disable the Windows Firewall (for testing connectivity) Right click on the Windows icon and click run. Then type (wf.msc) and turn off Domain Profile, Private Profile, and Public Profile.
- Step 3 Create the Client VM (Windows 10) named “Client-1”
- Step 4 After VM is created, set Client-1’s DNS settings to DC-1’s Private IP address (10.0.0.4)
- Step 5 Attempt to ping DC-1’s private IP address
Ensure the ping succeeded
From Client-1, open PowerShell and run ipconfig /all
The output for the DNS settings should show DC-1’s private IP Address (10.0.0.4)

 [Step 6] Install Active Directory
- Login in the Domain Controller (DC-1 Public, IP Address: 172.184.192.165)
- Go to "START" and select "Server Manager"
- Go to "Manage" and select "Add Roles and Features"
- Keep clicking next and at "Server Role" Select "Active Directory Domain Services" then Add Features, and keep clicking next and "Install."

[Step 7] Setup a new forest in the Active Directory as (mydomain.com)
- Click the "FLAG" on top right --> click on "Promote this Server to a Domain Controller"
- In Deployment Configuration select "add new forrest" in the "Root domain name" type (mydomain.com) and "Install"

[Step 8] Create a Domain Admin user within the domain (mydomain.com)
- Go to Start Menu
- In "Active Directory Users and Computers" (ADUC), create an Organizational Unit (OU) called "_ADMINS"
- Go to "Active Directory Users and Computers"
- Right Click on (mydomain.com) "NEW"--> "Organizational Unit" and create a folder for "_ADMINS"
- Create a user, (Jane Doe) under "_ADMINS" --> Right Click on "_ADMINS" --> "NEW" --> "USER"
- Add Jane to the “Domain Admins” Security Group to make her an official ADMIN. --> Right Click on Jane's account --> Properties--> Member of --> Type: "Domain Admins"--> Check Names--> Apply

[Step 9] Create a bunch of additional users in Folder "_EMPLOYEES" 
- Login in the Domain Controller (DC-1 Public, IP Address: 172.184.192.165) as "Jane"
- In "Active Directory Users and Computers" (ADUC), create an Organizational Unit (OU) called "_EMPLOYEES"
- Go to "Active Directory Users and Computers"
- Right Click on (mydomain.com) "NEW"--> "Organizational Unit" and create a folder for "_EMPLOYEES"
- Open PowerShell_ise as an administrator
- Create a new File and paste the contents of the script into it
- Run the script and observe the accounts being created
- When finished, open ADUC and observe the accounts in the appropriate OU

[Step 10] Dealing with Account Lockouts
- Log in to CLIENT-1 IP Address: 172.184.199.219 as one of the user (jag.jut), that was created in PowerShell_ise
- Purposely enter incorrect password to lock the account 
- Login in the Domain Controller (DC-1 Public, IP Address: 172.184.192.165) as "Jane"
- Go to "Active Directory Users and Computers"
- Right Click (mydomain.com) --> Find --> enter user (jag.jut) --> Right Click on user --> Account --> Check "Unlock Account" section --> Apply --> OK

[Step 11] Enabling and Disabling Accounts
- Go to "Active Directory Users and Computers"
- Right Click (mydomain.com) --> Find --> enter user (jag.jut) --> Right Click on user --> select ENABLE ACCOUNT OR DISABLE ACCOUNT.


 
       


<h2>Deployment and Configuration Step 1</h2>

<p>
  
![Server 2022](https://github.com/user-attachments/assets/e00cda20-9dea-418e-ba26-2166e34a64dd)
____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/24966794-2a24-4a2e-8235-42cc71adab28)
____________________________________________________________________________________________________



<h2>Deployment and Configuration Step 2</h2>


____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/b74b1717-efb0-4969-b20b-c8514825c193)
____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/8572acdc-45ef-47e8-bc40-60d9b3551ec4)
____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/790bc2e0-7c0b-4ed0-a5cd-19883ff5cee4)
____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/eb238244-b9f5-4c5a-9e99-c01a73887def)
____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/de943591-ef05-4547-9855-04931ca6da27)
____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/a37f8c70-b3ee-4d9b-996e-b96213005748)



<h2>Deployment and Configuration Step 3</h2>


![image](https://github.com/user-attachments/assets/ac27b990-b14a-4eca-ac1a-31d4f8279acd)
____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/7e0a3d3b-29aa-4c78-b53e-8af378c1354c)
____________________________________________________________________________________________________


</p>

<h2>Deployment and Configuration Step 4</h2>

<p>
  
![image](https://github.com/user-attachments/assets/f3c31044-8cab-46a8-9058-67cf0c99be06)
____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/88d546cf-ad8c-4292-a79b-bd5d72f4b72a)
____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/92e96df8-336d-4ccb-8dba-b577f240b196)
____________________________________________________________________________________________________


</p>

<h2>Deployment and Configuration Step 5</h2>

<p>
  
![image](https://github.com/user-attachments/assets/a4c87145-4132-48d2-82b4-2cf1cf53cd0e)
____________________________________________________________________________________________________

</p>

<h2>Deployment and Configuration Step 6</h2>

<p>
  
![image](https://github.com/user-attachments/assets/6a5763f2-39af-4aca-b0e8-3c86af766229)
____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/45f28cc8-5fd0-4ab0-a79c-4ce37cf084f6)
____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/d29ae36c-f274-498d-9fed-a6103e451bfd)

</p>

____________________________________________________________________________________________________

</p>

<h2>Deployment and Configuration Step 7</h2>

<p>
  
![image](https://github.com/user-attachments/assets/312b735a-3365-4730-8fee-361a63fc04ec)
____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/e5a1b4d1-b537-416a-85aa-5429e2db6b3b)
____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/5858fab8-26fc-45ae-b413-61c99e3f834c)
____________________________________________________________________________________________________

</p>


</p>

<h2>Deployment and Configuration Step 8</h2>

<p>
  
![image](https://github.com/user-attachments/assets/50b4c313-cc33-4e52-94b3-8b9101a41667)
____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/b58f77a0-8fb8-4833-a7d0-f64f55529b26)
____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/5845d75c-9fa5-474a-ac79-f44ef5fb8694)
____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/66e282de-ffca-4a56-9a1a-644889d55d63)
_____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/0d640d86-2367-4dc5-8958-a3351e33aa9c)

</p>

</p>

<h2>Deployment and Configuration Step 9</h2>

<p>
  
![image](https://github.com/user-attachments/assets/c36e76f5-46cf-4bbc-9d8e-94a4214fc382)
_________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/c2d1f4f9-db84-47e0-9d4e-f969cf51acdd)
____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/9d2ec682-710c-449b-873a-9f1791ec01c3)
____________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/b34963ac-d177-48d2-850f-2fc4940d3c3b)
__________________________________________________________________________________________________
![image](https://github.com/user-attachments/assets/d63e36d2-19bf-4e85-ad31-21f649495560)

</p>













