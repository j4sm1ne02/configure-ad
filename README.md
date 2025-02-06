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
