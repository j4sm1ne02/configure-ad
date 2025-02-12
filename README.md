<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://youtu.be/cwlVz4tD8pk?si=fsgucRQYYbdXTK8O)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Preparing AD Infrastructure in Azure
- Step 2
- Step 3
- Step 4

<h2>Preparing AD Infrastructure in Azure</h2>

<p>
<img width="567" alt="image" src="https://github.com/user-attachments/assets/ee3e05d0-5887-408a-8041-49749b17db54" />
</p>
<p>
Create a resource group: Active-Directory
</p>
<br />

<p>
<img width="604" alt="image" src="https://github.com/user-attachments/assets/702a6f6f-2ce0-4012-b0da-bea6bbbaab80" />
</p>
<p>
Create a virtual network and subnet
</p>
<br />

<p>
<img width="905" alt="image" src="https://github.com/user-attachments/assets/c6851c45-ed8a-4e2d-938a-79c39091108e" />
<img width="1271" alt="image" src="https://github.com/user-attachments/assets/137f84b1-e96d-4ddb-8562-c43c7aa5bc46" />
</p>
<p>
Create the Domain Controller VM (Windows Server 2022) named “DC-1”

Username: labuser

Password: Cyberlab123!

After the VM is created, set the Domain Controller’s NIC Private IP address to be static
</p>
<br />

<p>
<img width="826" alt="image" src="https://github.com/user-attachments/assets/e5c0d245-47b6-4de9-9fa1-002eb0c07296" />
</p>
<p>
Create the Client VM (Windows 10) named “Client-1”

Username: labuser

Password: Cyberlab123!
</p>
<br />

<p>
<img width="860" alt="image" src="https://github.com/user-attachments/assets/0d74ab8a-15b9-48ee-beb7-24c0327cc45a" />
</p>
<p>
After VM is created, set Client-1’s DNS settings to DC-1’s Private IP address
</p>
<br />

<p>
<img width="620" alt="image" src="https://github.com/user-attachments/assets/18ea3cd9-277d-4bf1-8087-3faecaeadb20" />
</p>
<p>
From the Azure Portal, restart Client-1
</p>
<br />

<h2>Deploying Active Directory</h2>
<p>
<img width="617" alt="image" src="https://github.com/user-attachments/assets/7b207554-ff36-4adb-bf46-06c3b451ba3e" />
</p>
<p>
Login to DC-1 and install Active Directory Domain Services
</p>
<br />

<p>
<img width="598" alt="image" src="https://github.com/user-attachments/assets/706db11f-220c-42f9-8a7e-28b1560cc3d8" />
</p>
<p>
Click on the triangle with the exclamation mark and
Promote as a DC: Setup a new forest as mydomain.com

For the password, put "password1"

Restart and then log back into DC-1 as user: mydomain.com\labuser
</p>
<br />

<p>
<img width="565" alt="image" src="https://github.com/user-attachments/assets/8e46a28c-cc0f-4635-ba77-d05e70cf0b33" />
<img width="560" alt="image" src="https://github.com/user-attachments/assets/d53db429-7582-4ce0-8344-5807d2c3aa2a" />
</p>
<p>
In Active Directory Users and Computers (ADUC), create an Organizational Unit (OU) called “_EMPLOYEES” and another one called "_ADMINS"
</p>
<br />

<p>
<img width="559" alt="image" src="https://github.com/user-attachments/assets/80be55ba-6f1b-4606-be5b-064f815c50e7" />
<img width="329" alt="image" src="https://github.com/user-attachments/assets/e8701659-0b95-4132-8985-ff16dfbec3be" />
<img width="444" alt="image" src="https://github.com/user-attachments/assets/c4f0d313-e614-4a78-8016-3a43f503f514" />
</p>
<p>
Create a new employee named “Jane Doe” (same password) with the username of “jane_admin” / Cyberlab123!

Add jane_admin to the “Domain Admins” Security Group
</p>
<br />

<p>
<img width="537" alt="image" src="https://github.com/user-attachments/assets/0cef31ba-d769-4cf2-8dd6-13edc564819b" />
</p>
<p>
Log out / close the connection to DC-1 and log back in as “mydomain.com\jane_admin”
</p>
<br />

<p>
<img width="574" alt="image" src="https://github.com/user-attachments/assets/c9185d2a-a88d-481b-8c59-69bc6fb4de03" />
<img width="349" alt="image" src="https://github.com/user-attachments/assets/0e82ba43-7842-445a-a97a-4cbd6b183499" />
</p>
<p>
Login to Client-1 as the original local admin (labuser) and join it to the domain

Enter Jane and the password.
</p>
<br />

<p>
<img width="563" alt="image" src="https://github.com/user-attachments/assets/73b13e80-264e-4b38-a3c1-7d9c9e47a842" />
<img width="475" alt="image" src="https://github.com/user-attachments/assets/7abff493-669f-4484-bf14-7a826e9363b9" />
<img width="561" alt="image" src="https://github.com/user-attachments/assets/04332383-b7e4-4fa7-a382-7083bb31425d" />
</p>
<p>
Login to the Domain Controller and verify Client-1 shows up in ADUC

Create a new organizational unit called "_CLIENTS" and drag "client-1" in there
</p>
<br />

<p>
<img width="490" alt="image" src="https://github.com/user-attachments/assets/db1a80a7-054d-43b3-a041-6e9921dab841" />
</p>
<p>
Log into Client-1 as mydomain.com\jane_admin

Open system properties

Click “Remote Desktop”

Allow “domain users” access to remote desktop
</p>
<br />

<h2>Creating Users In Powershell</h2>

<p>
<img width="615" alt="image" src="https://github.com/user-attachments/assets/a67eaefb-0249-48a9-80e3-aadfeeb2ae6c" />
<img width="528" alt="image" src="https://github.com/user-attachments/assets/64c21faa-1f48-4859-be76-3f5863449689" />
</p>
<p>
Login to DC-1 as jane_admin

Open PowerShell_ise as an administrator

Create a new File and paste the contents of the script into it

Observe the accounts being created. When finished, open ADUC and observe the accounts in the appropriate OU　(_EMPLOYEES) and attempt to log into Client-1 with one of the accounts (take note of the password in the script)
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
