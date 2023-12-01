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

- Create A Domain Controller and Ensure Connectivity Between the Client and Domain Controller
- Install Active Directory 
- Create an Admin and Normal User
- Setup Remote Desktop and Create Additional Users

<h2>Deployment and Configuration Steps</h2>

<p>
<img width="1440" alt="Screenshot 2023-11-28 at 10 52 25 PM" src="https://github.com/Beth-Agbassekou/configure-ad/assets/148320585/38391318-a09d-4fb9-9ae0-a2e8765bc87e">
<img width="1440" alt="Screenshot 2023-11-28 at 10 52 32 PM" src="https://github.com/Beth-Agbassekou/configure-ad/assets/148320585/ea25d83d-aa43-44a4-8680-4b9bd7add4d4">


</p>
<p>
When creating a domain controller and ensuring connectivity between the client and domain controller, I used Microsoft Azure.  
Setting up the domain controler was essentially running Windows server 2020 and running active directory on it. 
I had the client ping the domain controler since I connected the client to the domain controler. At first it failed, since the client could not recognize the domain controler, so I fixed a setting on the domain controller. Then I pinged the domain controler from the client and it worked after fixing some DHCP settings.   
</p>
<br />
<p>

<img width="1440" alt="Screenshot 2023-11-28 at 10 55 02 PM" src="https://github.com/Beth-Agbassekou/configure-ad/assets/148320585/901f8a8d-7c6a-4ca1-9061-fc2d516c2ce2">

<img width="1440" alt="Screenshot 2023-11-28 at 11 11 33 PM" src="https://github.com/Beth-Agbassekou/configure-ad/assets/148320585/7aa5d2ea-b9e0-4339-a3c5-9cd75403ee4b">
 
</p>
<p>
I installed Active Directory onto the domain controler to create the domain and promote DC-1 (domain controller name) to a proper domain controller. Then I had to restart the domain controller to complete the promotion DC-1. 
<p>
</p>
  
<img width="1440" alt="Screenshot 2023-11-28 at 11 18 17 PM" src="https://github.com/Beth-Agbassekou/configure-ad/assets/148320585/f2dbdc39-9342-46e2-ba27-b9c2454e23e9">
<img width="1440" alt="Screenshot 2023-11-28 at 11 19 53 PM" src="https://github.com/Beth-Agbassekou/configure-ad/assets/148320585/c69b921a-36f6-46fe-82f1-e6dcb31fdfb3">

</p>
<p>
I created an admin and normal user within Active Directory. I also created several Organizational units to represent employees, admins, and clients. 
    
</p>
<br />

<p>

<img width="1440" alt="Screenshot 2023-11-29 at 12 08 14 AM" src = "https://github.com/Beth-Agbassekou/configure-ad/assets/148320585/c724fffd-f0d0-4935-a5fa-de41c1268ccc">

<img width="1440" alt="Screenshot 2023-11-29 at 12 08 14 AM" src= "https://github.com/Beth-Agbassekou/configure-ad/assets/148320585/35ee1c78-62b1-4e6e-b387-977323103156"> 


<img width="1440" alt="Screenshot 2023-11-29 at 12 08 14 AM" src="https://github.com/Beth-Agbassekou/configure-ad/assets/148320585/560bd362-ed78-41e2-9b88-6d29de0ac700">

<img width="1440" alt="Screenshot 2023-11-29 at 12 08 21 AM" src="https://github.com/Beth-Agbassekou/configure-ad/assets/148320585/22b6b4b9-b996-4a37-8eab-1fd9c5e47641">



  
</p>
<p>
I set up a remote desktop after connecting the client virtual machine to the domain I created when setting up the active directory. When setting up the remote desktop connection it was important to allow the domain users to access remote desktop. When logging into the client computer as admin was one of the ways to allow remote desktop. Then I used a powershell script to create users to test the remote desktop connection.  
  </p>
<br /># configure-ad
