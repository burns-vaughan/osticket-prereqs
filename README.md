<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>

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
3. Install PHP Manager for IIS 
4. Install the Rewrite Module 
5. Create the directory C:\PHP
6. Install PHP 7.3.8
7. Install VC_redist.x86.exe
8. Install MySQL 5.5.62
9. Open IIS as an Admin
10. Register PHP from within IIS and reload IIS (Open IIS, Stop and Start the server)
12. Install osTicket v1.15.8 and reload IIS
13. Enable PHP extensions in IIS 
14. Move on to post installation steps

<h2>Deployment and Configuration Steps</h2>

<h3>1. Create a virtual machine in Azure</h3>

The first step is to create a virtual machine in Azure. To do that log in to your Azure account and select create a virtual machine. There are multiple ways to get there. Below, is a screenshot showing how to do it:<br><br>

<kbd><img src="https://i.ibb.co/jZL6b6M/os-Ticket-prereqs1.jpg" alt="os-Ticket-prereqs1" border="0" /></kbd><br><br>

Name it something convenient like VM-1. And create a new resource group. Name it something like osTicket.

For the operating system select Windows 10.
For the resources, select 2 CPUs. 1 CPU will be too slow.
Here's a screenshot showing what to select for the OS, and the CPU.<br><br>

<kbd><img src="https://i.ibb.co/9yQPFRM/osticket-prereqs3.jpg" alt="osticket-prereqs3" border="0"></kbd><br><br>

Make note of the username and password on a Notepad or similar. Because this is for testing a simple username and password is sufficient.
It will take a minutes or so to create the new VM.

<h3>2. Install and enable IIS</h3>
After creating the virtual machine log in to it using Windows Remote Desktop. 
If it's your first time doing it, open up Windows Remote Desktop from the Windows start menu.
<br><br>
1. Then click on your virtual machine in Azure to show the settings.<br>
2. Copy the public IP address.<br>

Shown in the screenshot below:<br><br>

<kbd><img src="https://i.ibb.co/zrnXxg4/osticket-prereqs4.jpg" alt="osticket-prereqs4" border="0"></kbd><br><br>

4. Paste that into Windows Remote Desktop, shown in the screenshots below.<br><br>

<kbd><img src="https://i.ibb.co/y0KgK93/osticket-prereqs5.jpg" alt="osticket-prereqs5" border="0"></kbd><br><br>

You then need to select more choices > use another account, shown below.<br><br>

<kbd><img src="https://i.ibb.co/9NkCNKT/osticket-prereqs6.jpg" alt="osticket-prereqs6" border="0"></kbd><br><br>

6. Input your username and password to connect to the VM

<h3>3. Install PHP Manager for IIS </h3>

There are a bunch of prerequesite files that need to be downloaded to install osTicket. In my experience it's far easier to download everything at once. Google Drive scans the files for viruses which takes a long time one by one. Also, when using a VM for any length of time I install Google Chrome, as I'm more used to using it. Rather than, Microsoft Edge.

To download all of the required files access the Google Drive <a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">link</a> and download the entire contents

Once it has finished downloading unzip it by right clicking on it, and selecting extract all.

Next open go to the start menu and type 'turn windows features off'. Select the option at the top that says 'turn Windows features on and off.

A new windows will open with a bunch of settings. Below, is a screen shot showing which ones need to be enabled.<br><br>

<kbd><img src="https://i.ibb.co/5jxBR7Z/1.jpg" alt="1" border="0"></kbd><br><br>

You enable them by clicking on the check box. For the last option you select all of the options. The main thing is to ensure yours looks exactly the same as the screenshot above. Select OK, and will take 20 seconds or so to make some changes.

After that go to the folder where you unzipped all of the download files and double click on: 

It will open the installer for it. Select next, and ok using all the default options and it will install it.

<h3>4. Install the Rewrite Module </h3>
Go to your folder with all of the files you downloaded.
Double click on rewrite_amd64_en-US and hit accept, and next to install it. Use all the default options.

<h3>5. Create the directory C:\PHP</h3>
Open up File Explorer - My Computer and navigate to the C: Drive.
Create a new folder - it will be empty for now and call it PHP.
The path should be C:\PHP 

<h3>6. Install PHP 7.3.8</h3>
First unzip the file:
php-7.3.8-nts-Win32-VC15-x86.zip from the downloads folder
Open up the unzipped folder. Select all of the contents and copy it into the C:\PHP folder

<h3>7. Install VC_redist.x86.exe</h3>
Go to your folder with all the download files.
Double click on:
VC_redist.x86

Select all the default options, and hit next, and accept to install it.

<h3>8. Install MySQL 5.5.62</h3>

Go to the folder with all the downloads and double click on:
mysql-5.5.62-win32

Accept all of the default settings and click, ok, next. Once it finished installing it will prompt you run a wizard to set up the MySQL server. You want to change the default option when this open after installing MySQL. Change it to standard configuration as shown in the screen shot below: <br><br>

<kbd><img src="https://i.ibb.co/vLtG1nq/3.jpg" alt="3" border="0"></kbd><br><br>

Then set a password for your SQL server. This is used because osTicket creates a database to store all of the tickets.

Make note of the password somewhere.

<h3>9. Open IIS as an Admin</h3>
Go to the start menu and type in IIS. Then select Internet Informations Services Manager.

<h3>10. Register PHP from within IIS and reload IIS</h3>
A new windows will open from the tiles select PHP Manager as shown in the screenshot below: <br><br>

<kbd><img src="https://i.ibb.co/sv2wQLq/3.jpg" alt="3" border="0"><br><br></kbd><br><br>

Click on 'Register new PHP version'. It will ask you where the PHP file is located. It's in the C:\PHP folder which we created earlier. Select that, and the file name it's asking for which will be shown there.

Nothing will happen to let you know it's finished. Click back, or on the virtual machine on the right hand side to go back to the main screen with the list of options. From the right hand side click on 'restart' to restart the server.

<h3>12. Install osTicket v1.15.8 and reload IIS</h3>
Go to the folder where you have all the files downloaded and extract osTicket v1.15.8.
When it has finished extracting copy the folder it unzipped called “upload” to this folder C:\inetpub\wwwroot
After that, rename the folder called 'upload' to 'osTicket'.<br><br>
Go into IIS, and restart the server, then open osTicket by selecting 'sites' on the lefthand side, and then osTicket from the dropdown menu. After that, 'Browse *:80 on the right hand side, shown in the screenshot below: <br><br>

<kbd><img src="https://i.ibb.co/6ZdwWJL/4.jpg" alt="4" border="0"></kbd><br><br>

<h3>13. Enable PHP extensions in IIS </h3>
Click on the PHP Manager option on the IIS home screen, and scroll down to the bottom.
Click on 'enable or disable' and extension.
Then enable the following extensions: <br><br>
php_imap.dll<br>
php_intl.dll<br>
php_opcache.dll<br><br>

After that refresh the server

<h3>14. Configure roles and SLAs</h3>
Go into the following folder and edit the following file:
C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php

change is so to remove the word sample from the filename. It should be:
C:\inetpub\wwwroot\osTicket\include\ost-config.php

Write click on the file and select properties. On the new window that opens up open up click on the security tab at the top. Then click on Advanced. Next select the option that says remove all inheritance. And select remove all on the pop-up. Which is the bottom option. 
<br><br>
After that click on add. Select create principle. In the search box type everyone and click 'check names'. Give them full access.
Then click ok and apply.

Install the HeidiSQL file from the installation folder you downloaded. Select all the default options and install it. After that create a new database in HeidiSQL. To that click on add at the bottom right. Leave everything the same but put in your username and password.

Shown in the screenshot below <br><br>
<kbd><img src="https://i.ibb.co/k8vmXqj/4.jpg" alt="4" border="0"></kbd><br><br>
It's the same username and password you noted down when you installed MySQL.

After that you also need to create a database within the new database called osticket.

To do that right click on the database name on the left hand side. It should be 'unnamed'. Then select New > Database
Name is osticket and leave everything else the same. Then select ok and accept.

Finally, go to the website for your osTicket helpdesk, which is:

http://localhost/osTicket

And click on install at the bottom. Fill out all the options. At the bottom it asks for the database details.
It should be following which we created earlier:
database name: osticket
database username: root
database password: what you set it to in the previous step

Then click on install, and you will get the following screen:<br><br>

<kbd><img src="https://i.ibb.co/7Ycyfp0/5.jpg" alt="5" border="0"><br></kbd><br><br>

Congratulations, now on to the post installation set up.


