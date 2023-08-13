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


