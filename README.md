<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />
<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

<h2>Installation Set up</h2>

<h4> - Create a resource group and Virtual Machine in Azure where the prerequisites and installation of osTicket will be done. Take note of your username and password as they would be needed when you remote into the VM. </h4>

  
![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/aaeff093-8161-4cba-a8bf-aaf5632b2193)

<h4> - Connect to the Virtual Machine, grab the VM's public IP address and open remote desktop. Enter the username and password you made when creating the VM. </h4>


![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/9c81224d-57b7-4fb1-af10-d10b0433663c)

![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/b7960194-cd61-4e17-bb8a-077e9092156c)



<h4> - Install / Enable IIS in Windows with CGI and Common HTTP Features </h4>
-> Control Panel -> Programs -> Turn Windows Feature on or off -> *Expand Internet Information Services -> World Wide Web Services -> Application Development Features ->

- Check or tick CGI
-  Expand Common HTTP Features and check all the boxes

![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/884923bf-7aea-4632-957e-9aa55a2db49f) ![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/5ebede53-62e3-4364-9a90-9ae4c150f4cc) ![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/02ab9778-cadf-419b-8e41-c67c954ebe72)


<h4> - Open a web browser and enter 127.0.0.1 into the search bar to check if IIS is working.</h4>

![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/16b27d1a-c883-4a99-995b-b99ad0cdf06d)

<h4> - Download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) (Once the new tab opens click download anyway.)</h4>
<h4> - Download and install the Rewrite Module (rewrite_amd64_en-US.msi) (Once the new tab opens click download anyway.)</h4>
<h4> - Create the directory C:\PHP </h4>
<h4> - Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP </h4>

![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/50131cad-22dc-4012-9d5d-19e805f0756d)

<h4> - Download and install VC_redist.x86.exe. (Once the new tab opens click download anyway.) </h4>
<h4> -Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) (Once the new tab opens click download anyway.) </h4>
 - Choose the Typical Setup -> Launch Configuration Wizard (after install) -> Choose Standard Configuration
 
 - Take note of the root password that you create

<h4> - Open IIS as an admin and register PHP from within IIS</h4>

![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/e0dbea31-dba6-48cb-9dc3-5828395b33f9) ![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/2fe4c467-3fbd-4a93-bcfc-26c43c02f275)

-> Click PHP Manager -> Register new PHP version -> Browse files and open the PHP folder -> click php-cgi -> On the right hand side on the Actions Panel, below Manager Server click Restart.

![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/b938f090-13fe-4050-aa6d-86493671cf7b)

<h4> - Download and Install osTicket v1.15.8 </h4>
-> Open the downloaded osTicket folder and copy the "Upload" folder -> Open the C: Drive and open the inetpub folder -> Open the wwwroot folder -> Paste the "Upload" folder -> Rename the "Upload" folder to osTicket

![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/19820853-acbf-49a0-984e-c8763e52a1dc)

<h4> - Reload IIS (Open IIS as an admin and Restart the Server)</h4>

![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/b938f090-13fe-4050-aa6d-86493671cf7b)
-> After restarting, on the left side of the window on the Connections panel, expand sites -> Expand Default Web site -> Click osTicket -> On the right hand side under the Manage Folder Click Browse *:80(http) 

![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/0a9f6271-985a-46a6-95c4-f53dd12c52ce)

<h4> osTicket Installer page should open</h4>

![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/d6924a02-9fe0-4599-aa8a-0de5c1f9dc2b)

<h4> -Note that some extensions are not enabled</h4>
-> Head back to IIS manager -> Click open PHP Manager -> Under PHP extensions click Enable or Disable extension

- Enable: php_imap.dll
- Enable: php_intl.dll
- Enable: php_opache.dll
  
![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/bf9cf5cf-34c6-4499-8127-663a65e3e126)

<h4> Before and After extensions are enabled</h4>

 ![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/03f86c47-fd53-48bf-89c6-f20eb2801ec7)

<h4> - Rename: ost-config.php</h4>

- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/4c3dd8f5-172e-4f53-acc7-94d3de12e6ba)

<h4> - Assign PermissionsL ost-config.php</h4>

Right click ost-config.php -> Open Properties ->j Open Security tab and click Advanced -> On the Permissions Tab, click Disable Inheritance -> Click Add -> Click Select a Principal -> Type in Everyone and click Check names to verify -> Click Full Control -> Apply and click OK

![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/0419b82d-7cc2-42a8-b342-b0b61ab546c3) ![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/aa3cf041-796c-4166-a620-78898945b3cc)

<h4> - Continue Setting up osTicket in the broswser (clcik Continue)</h4>

- Name Helpdesk
- Default email (receives  email from customers)
- Take note of Credentials
-  Before clicking Install now, Heidi SQL needs to be installed.

<h4> - Download and install HeidiSQL</h4> 

- Open Heidi SQL
- Create a new session, root and (password you created when installing MySQL)

![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/2e58cfcc-004c-48cb-a82c-43a61d829b89)

- Connect to the session
- Create a database called "osTicket"

![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/c6d65b6c-6e93-4d77-9867-ea144945dcae)

<h4> - Continue Setting up osTicket in the Browser</h4>

- MySQL Database: osTicket
- MySQL uswername : root
- MySQL Password : Password you created
- Click Install Now!

![image](https://github.com/marvrodriguez/osticket-prereqs/assets/141983161/3a3d7f4d-168a-4eaf-acc4-a39ef8bce056)


