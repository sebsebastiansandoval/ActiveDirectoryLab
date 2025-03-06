<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop (mstsc)
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10 Pro </b> (21H2)

<h2>List of Prerequisites</h2>

- Install web platform installer
- Install my sequel, username and password
- Install C++ Redistributable
- Install OSticket
- Enable Internet Information Services (IIS)
- Configure Permissions

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/y8nB6ik.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this tutorial after we download all of the necessary dependencies, creating the necessary virtual machines and installing osTicket, at the end we should have a working ticketing systeming where we'll be able to send and receive tickets but also troubleshoot them as well. 
</p>
<br />

<p>
<img src="https://i.imgur.com/LDjihna.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/ihZZw9g.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
First, login into Microsoft Azure Portal with your tenant (organization) and subscription already setup. Create an Azure Virtual Machine Windows 10. Name it "osticket-vm". Set the username as "labuser" and the password as "osTicketPassword!". Let's name the vm "osTicket-vm", Select any region (for ex: US Central). Set under "image" to Windows 10 Pro. And of course we must agree with the licensing agreement at the bottom before continuing. Then click review + create.
</p>
<br />

<p>
<img src="https://i.imgur.com/imLNKPz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open Remote Desktop Connection on your desktop (for Windows). Connect using the virtual machines public IP (130.131.160.162 in this case). Enter the username and password we created earlier.
</p>
<br />

<p>
<img src="https://i.imgur.com/n0CwIqC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download the osTicket Installation zip files onto the VM. Extract the file specifically onto desktop. 
</p>
<br />

<p>
<img src="https://i.imgur.com/b0H55es.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now let's enable IIS and CGI. To start, open Control Panel in Windows. Select under Programs and Features "Unistall a Program". Click and enable "Internet Information Services". Expand that then expand "World Wide Web Services", then expand "Application Development Features". Now finally, enable CGI then hit OK.
</p>
<br />

<p>
<img src="https://i.imgur.com/jqy1DDo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
For us to run osTicket, we will need to install PHP, which is a backend web server language. 
First go back to extracted osTicet file and double click "PHPManagerForllS_V1.5.0". From the same osTicket installation folder, we will also download "rewrite_amd64_en-US.msi", which is the Rewrite Module.
</p>
<br />

<p>
<img src="https://i.imgur.com/lUcMLqo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create the directory C:\Windows PHP
</p>
<br />

<p>
<img src="https://i.imgur.com/c4wAfKP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the same osTicket foler we unzipped, we want to unzip PHP 7.3.8 php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\Windows PHP” folder.
</p>
<br />

<p>
<img src="https://i.imgur.com/PjIV7o8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/l2Bacz3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the same osTicket folder, double click and install Microsoft Visual C++ (VC_redist.x86.exe)
</p>
<br />

<p>
<img src="https://i.imgur.com/U2shtEp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next we must download MySQL. Which will act as a database which includes all the user account or ticketing information. 
Select and double click the "mysql=5.5.62-win32" file, located in the same osTicket folder. Accept all terms and agreements then hit install.
</p>
<br />

<p>
<img src="https://i.imgur.com/hsLS9zs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Select Standard Configuration, the next.
</p>
<br />

<p>
<img src="https://i.imgur.com/Pb98TX8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
For this step, it is VERY curcial we do this part correctly. Our root password is "root" but it is NEVER recommended to use such a simple password in a real work setting.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
hi
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
