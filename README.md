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
- Step 6 Install Active Directory 


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
  
![image](https://github.com/user-attachments/assets/a4c87145-4132-48d2-82b4-2cf1cf53cd0e)
____________________________________________________________________________________________________

</p>




