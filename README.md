<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
<p align="center">[in progress]</p>

This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket. It requires a Microsoft Azure account. I can be the free trial susbcription or a paid subscription.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

1. Create a virtual machine in Azure
2. Install and enable IIS
3. Download and install PHP Manager for IIS 
4. Download and install the Rewrite Module 
5. Create the directory C:\PHP
6. Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
7. Download and install VC_redist.x86.exe
8. Download and install MySQL 5.5.62
9. Open IIS as an Admin
10. Register PHP from within IIS and reload IIS (Open IIS, Stop and Start the server)
12. Install osTicket v1.15.8 and reload IIS
13. Go to sites -> Default -> osTicket and configure
14. Move on to post installation steps

<h2>Deployment and Configuration Steps</h2>

<h3>1. Create a virtual machine in Azure</h3>

The first step is to create a virtual machine in Azure. To do that log in to your Azure account and select create a virtual machine. There are multiple ways to get there. Below, is a screenshot showing how to do it:

<img src="https://i.ibb.co/jZL6b6M/os-Ticket-prereqs1.jpg" alt="os-Ticket-prereqs1" border="0" />

Name it something convenient like VM-osticket

For the operating system select Windows 10.
For the resources, select 2 CPUs. 1 CPU will be too slow.

<h3>2. Install and enable IIS</h3>


<h3>3. Download and install PHP Manager for IIS </h3>
<h3>4. Download and install the Rewrite Module </h3>
<h3>5. Create the directory C:\PHP</h3>
<h3>6. Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP</h3>
<h3>7. Download and install VC_redist.x86.exe</h3>
<h3>8. Download and install MySQL 5.5.62</h3>
<h3>9. Open IIS as an Admin</h3>
<h3>10. Register PHP from within IIS and reload IIS</h3>
<h3>12. Install osTicket v1.15.8 and reload IIS</h3>
<h3>13. Go to sites -> Default -> osTicket and configure</h3>
<h3>14. Configure roles and SLAs</h3>

<p align="center">
<img src="https://i.ibb.co/jZL6b6M/os-Ticket-prereqs1.jpg" alt="os-Ticket-prereqs1" border="0" />
</p>
<i>screenshot of where to create a virtual machine in Azure.</i>
<p><br>
The first step is create a virtual machine. In this example I will be using Azure. It's very straightforward to set one up, just ensure to note down the username and password. A resource group and virtual network get created automatically.
  
For the operating system install Windows 10, with a minimum of 2 virtual CPUs. Otherwise it will be too slow.
</p>
<br />

<p>
<img src="https://i.ibb.co/yNypkpW/os-Ticket-prereqs2.jpg" alt="os-Ticket-prereqs2" border="0">
</p>
<i>screenshot showing where to select Windows 10 as the operating system</i><br>
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
