<p align="center">
<img src="https://imgur.com/GaolqUH.png" alt="osTicket logo"/>
</p>

<h1>Active Directory Home Lab</h1>


<h2>Description</h2>
In this tutorial we are going to learn the step-by-step process of creating an Active Directory Home Lab environment using Oracle Virtual Box. By following this lab it will definitely help develop your understanding of how active directory and Windows networking works, so I'd recommend going through it at least a couple times. Make sure to ask questions where you don't understand and even consider asking ChatGPT about any unfimiliar concepts until they make sense. Eventually try this lab without using the tutorial as well. Feel free to reach out if you have any questions!
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 

<h2>Environments Used </h2>

- <b>Virtual Box</b>
- <b>Windows 10 ISO</b>
- <b>Server 2019 ISO</b>

<h2>Lab Diagram:</h2>
<p align="center">
<img src="https://imgur.com/qOkMowa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<h2>Program walk-through:</h2>

<p align="center">
<img src="https://imgur.com/enejrBW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
First, download Virtual Box for Windows along w/ the Extention Pack via this link here www.virtualbox.org/wiki/Downloads, regardless of the Operating System you're using (e.g. Windows, Linux)
<br />
<br />

<p align="center">
<img src="https://imgur.com/Aqm3HLi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Download Windows 10 64-bit, save somewhere you will remember (e.g. save to Desktop)
<br />
<br />

<p align="center">
<img src="https://imgur.com/5HC22RW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Now to create our Virtual Machines, open Oracle Virtual Box and hit "New". We'll name this one DC (Domain Controller), and set to Windows Other (64-bit).
<br />
<br />

<p align="center">
<img src="https://imgur.com/VOqs1pA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
We will be allocating 2,048 MBs or 2Gbs of RAM MINIMUM to our VM.Then hit finish and create.
<br />
<br />

<p align="center">
<img src="https://imgur.com/HF8DUqJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Now our Domain Controller has been created but there is nothing on it yet, before we install Server 2019, we will go to Settings then Advanced. Here change "Shared Clipboard" and "Drag'n'drop" to Bidirectional. Turning that on for Shared Clipboard allows you to actively switch between your live VM and main desktop interchangably, with Drag'n'drop it allows you to drag files from for example your desktop onto the VM.
<br />
<br />

<p align="center">
<img src="https://imgur.com/Eyd5zWf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Go to "System" then "Processor", here we will allocate 4 cores instead of 1 as it speeds up the process for everything. But if you don't know how many cores you have or have a weak laptop you can simply keep it at 1 core.
<br />
<br />

<p align="center">
<img src="https://imgur.com/ktJaJNe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Lastly, go to the "Network" tab we will leave Adapter 1 alone as that will be one of our 2 total NICs for our DC, acting as the external NIC that will be connected to our home internet that will gain us access to browse the internet. Then go to "Adapter 2" we will be setting this adapter as our Internal private NIC so set it as "Internal Network" then hit create.
<br />
<br />

<p align="center">
<img src="https://imgur.com/6OXITbM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
We have now officially created our Virtual Machine but still has nothing on it yet. So to install Server 2019 we will turn on our VM by double clicking it. A window will pop up and we just want to select the Server 2019 file we saved to desktop earlier. Choose then hit Start to start the VM. Keep in mind that the installing portion of this will take a minute.
<br />
<br />

<p align="center">
<img src="https://imgur.com/To3F4f9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
With it finally installed hit Install Now then select either of the two Desktop Experience options because if we were to any other one it will just send us straight to the command line and not load us into the GUI like we want. Then hit Custom Install as we will format the hard drive and start it from scratch.
<br />
<br />

<p align="center">
<img src="https://imgur.com/R8IWiMH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
As it finalizes and installs Windows onto the Server this will also take awhile to complete. IMPORTANT DISCLAIMER: As it is downloading the server will restart several times, as it restart it will prompt you to "click any key to boot", IGNORE that and do not click any keys during this process because we do not to boot into the setup again.
<br />
<br />

<p align="center">
<img src="https://imgur.com/yeLKZ0u.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
With Server 2019 finally installed, you will be prompted to set an Adminstrative Password, for this password and every other password from this lab onward we will be using the same password "Password1" so we can remember it easily. Just never do that in a real world environment! ;)
<br />
<br />

<p align="center">
<img src="https://imgur.com/6Fz5gSd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
To login to the VM, you'll notice it will say to do the combined keystroke "Cntrl+Alt+Dlt" to login but when you try to do that it will not work. Depending whether you are using Mac or Windows you'll go to Input then Keyboard, then hit "Insert Cntrl+Alt+Dlt" it will then prompt you to enter our simple password from earlier. "Password1"
<br />
<br />

<p align="center">
<img src="https://imgur.com/zA9rmLS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Once you're logged into the VM you'll notice how the user experience around is very choppy, for example simply moving around your mouse or minimizing/maximizing the window size for the VM. To fix this click Devices at the top of the window then enable "Insert Guest Additions".
<br />
<br />

<p align="center">
<img src="https://imgur.com/0mW4yD2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
To finilize guest additions, go to your file explorer app. You will now see a new Drive appear called "CD Drive (D:) VirtualBox Guest Additions", double click that then near the bottom of the listed contents inside double click the executable "VBoxWindowsAdditions-amd64". Agree to each of the prompts until it asks you to reboot now, click reboot later then "Finish". Now, shutdown the VM.
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/zPO31J7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Double click our VM to start it up again. Once open, login by clicking input at the top then "Insert Cntrl+Alt+Dlt". Now you notice how much smoother the overall user experience is. 
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/MoQVPYG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Looking back at the diagram we have 2 NICs for our DC, our internet NIC does not require us to setup up an IP as it will use DHCP to get addressing from your home router. But for our Internal NIC, we must set it up manually.
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/ir5GZsC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Open up "Control Panel" then go to "Network and Internet" then "Network Connections". We want to identify which NIC is our Internal versus our Internet NIC and rename them accordingly. 
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/KMIr3Tj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Right click the left one the hit "Details". We'll see this contains a home-like IP "10.0.2.15" so we will rename this "_INTERNET_". You'll notice the other NIC contains the address 169.254.196.79, meaning at one point it tried utilizing DHCP to assign an address but was unable to so it assigned itself this specific IP. So if you see a NIC with this specifc address that's how you'll know it's our Internal one. Rename this one "X_Internal_X".
<br />
<br />
  
<p align="center">
<img src="https://imgur.com/BREeW6V.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
To assign an IP to our Internal NIC now right click our Internal NIC then hit "Properties". Double click "Internet Protocol Version 4 (TCP/Ipv4)", then click "Use the following IP address:" and insert the IP and Subnet Mask all according to the Diagram. DISCLAIMER: We will not be assigning a default gateway because the DC itself will server as the default gateway so this particular NIC will not use one.
<br />
<br />
  
<p align="center">
<img src="https://imgur.com/9FrjlRw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
For DNS, when installing Active Directory it automatically installs DNS so this server will actually be using itself as the DNS server. To do that we either re-enter it's own IP address "172.16.0.1", or we can the universal loopback address 127.0.0.1. Then hit OK then OK again.
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/7QTgTz1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Next, we will rename this PC as it currently has a randomly generated name. Right click the Windows icon at the bottom left then "System". Then "Rename this PC" to something arbritrary like "DC". Next, then "Restart Now" and allow it to reboot.
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/thKgibG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Looking back at our diagram we have both our NICs setup, we configured IP addressing for our Internal NIC and it is connected to the internal network where nothing is actually there yet. We will now install Active Directory Domain Services or shown on the diagram "AD DS" and create a domain!
<br />
<br />
  
<p align="center">
<img src="https://imgur.com/xnBehTn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Now looking at Server Manager, click "Add roles and features". Hit "Next >" until you get to Server Selection, this is where you select the server on which Active Directory will be working on. In this lab we only use 1 so we'll choose that one.
<br />
<br />
  
<p align="center">
<img src="https://imgur.com/iizEEmV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
With Server Roles we'll be only selecting "Active Directory Domain Services". Then Next > and "Install". Depending on how much resources you dedicated to the VM in the beginning and your personal internet speed, this process may take a minute to complete.
<br />
<br />
  
<p align="center">
<img src="https://imgur.com/XlVRsxX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Now with the role installed, we can close that window. You'll notice this "yellow flag" at the top right corner. Telling us that we have to do our "Post-deployment Configuration" that we installed the software for active directory services but we haven't actually created the domain yet. So click this to promote this server to Domain.
<br />
<br />
  
<p align="center">
<img src="https://imgur.com/JxoQ5TI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
"Add a new forest". We can name the domain whatever we want but for this lab we will name it "mydomain.com". Next > then under Domain Controller Options, type the Directory Services Restore Mode (DSRM) password. Password1. Next > then Install. It will automatically restart the server for us.
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/FK6nGHC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
You'll now notice your current user begins w/ MYDOMAIN\. Login with "Password1".
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/z47DBN9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
We are actually going to create our own dedicated Admin account, rather than use the built-in adminstrator account. To do so, go to Start on the bottom left -> Windows Adminstative Tools -> Active Directory Users and Computers.
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/Evmwk8O.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
We have our new and freshly created domain now "mydomain.com". To store our dedicated admin account we will store it in a newly created "Organizational Unit" or OU. Which is essentially acts as a folder in active directory. We will name it "_ADMINS".
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/5DEt3nl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Right click _ADMINS -> New -> User. Name it your name. For our user we will use the most common naming convention used in a work environment for ex. "a-*insert first initial + full last name". So for us it would be "a-ssandoval". Then finish.
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/sYNcGBK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
With our newly created Admin account you'll see it's still a regular "User" account. To assign it as a admin role, right-click your user -> Properties -> Membor of -> Add -> under "Enter the object names to select:" enter "domain admins" -> Check Names. We'll see it resolves to Domain Admins, then hit OK. We now have our very own admin account!
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/9ZKlJ2S.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
To now use this account, sign out of the VM then log back in clicking "Other User" at the bottom left. Enter the admin user we created earlier, for myself it would be "a-ssandoval" and our simple password "Password1". Allowing it to pull our name out from Active Directory.
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/AucdXW9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Next we will install RAS/NAT (Remote Access Server/Network Address Translator). Which will allow our Windows 10 client to be on this private virtual network but still able to access the internet through this Domain Controller.
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/csG8MLR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Next we will install RAS/NAT (Remote Access Server/Network Address Translation). Which will allow our Windows 10 client to be on this private virtual network but still able to access the internet through the Domain Controller.
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/GZSBOHk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
To do so go to Server Manager and click "add roles and features", select the server we created and hit next. Under Server Roles, check "Remote Access". Under Roles Services install "routing" then install.
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/JCvLUJ0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Once that is done installing, on Server Manager go to "Tools" on the top right. Click "Routing and Remote Access". Right click our DC then click "Configure and Enable Routing and Remote Access". Select NAT then next. When choosing which network out of the two NICs we created we will select our Internet NIC as our means of connecting. Finalize and then we have successfully installed and configured RAS / NAT.
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/Yl9aPkO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Now we will setup a DHCP Server on our Domain Controller. Which will allow our users on the network to automatically obtain an IP address on their computers and browse the internet. We want to go back to Server Manager and select "Add roles and features", once again select our server, check "DHCP", next then Install. Now with it installed we can setup our Scope.
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/1CjpnCM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Go to Tools on the top right, then DHCP. Right click IPv4 then "New Scope.". We can simply name the Scope what the IP range is, in our case "172.16.0.100-200". Next. Under Lease Duration, meaning how long a user on that network can use a given IP (e.g. as the owner of a cafe we would want it to be only around 2 hours). Leave it as 8 days since this is in a home lab setting.
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/V0kgxrD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Under Configure DHCP Options, configuring this we can tell each client which server to connect to for DNS or the Gateway and we do want to configure that so our clients can access the internet. Looking back at our diagram we can see we configured NAT on the DC so its job is to also forward traffic from the clients to the internet. Because of this we are going to use our Internal NIC as the router (default gateway) for DHCP. In our case "172.16.0.1". Then hit "Add".
<br />
<br />
 
<p align="center">
<img src="https://imgur.com/fc2sJEM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Now it asks what we wanna use for our DNS Server, but because it comes autmatically installed when installing Active Directory onto our DC, we will use our DC as the DNS Server. Then hit Next. Yes "Activate Scope' then Finish. To finalize our changes, on our DHCP window right click the DC, "Authorize", then hit "Refresh".
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/disablefeatureIE.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Now we must create a configuration that allows us to browse the internet from the DC (NEVER DO IN A REAL LIFE WORK ENVIRONMENT THIS IS JUST FOR THE LAB). Go to Server Manager then "Configure this local server". Here we want to diable this feature here "IE Enhanced Security Configuration", if left on before each page on the internet loads Internet Explorer will bug us asking "Are you sure you want to open this link?".
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/pastescriptlink.png" width="80%" alt="Disk Sanitization Steps" />
<br />
We will now use our Powershell script to automate the creation of each and every mock user on our private network, similar to a actual work setting. This link here, , is it the source code to the powershell script to create all the users. All credits to Tech Influencer and IT Professional, Josh Madakor, for creating the source code and providing it to the public for anyone to use! :) First go to your DC and open Internet Explorer and paste that link there. Download and save the file onto your Desktop. Then extract it there.
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/scriptnames.png" width="80%" alt="Disk Sanitization Steps" />
<br />
But before we dive into anything a short explanation on how this script works. After extracting onto the desktop we want to open that file, and open this plain text files "names". You'll see here each randomly generated name, each to act as individual mock users. And create one for yourself at the top of the list with your first and last name. Save your changes then close this window.
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/enablescripts.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Click the windows start icon at the bottom left, look for Powershell ISE and right click to open as administrator. Click the Open Script icon at the top left then select our downloadaed script. As a security feature first we must enable the use of all scripts, as you'll notice how when we try to execute as is you will receive an error message.  
<br />
<br />
 
<br />
Type into Powershell "Set-ExecutionPolicy Unrestricted" then enter. Then "Yes to all".
<br />
<br />

<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/entercorrectdirectory.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Now that we can officially run our script to create our mock users, we first have to make sure we're in the correct directory for it to properly pull out the content from our "names.txt" file. In the GUI, type "cd c:\users\a-*enter your username*\desktop\AD-PS-master" then enter. Then if we type "ls" into the GUI we'll see the "names.txt" present.
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/playscript.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Click the green arrow icon at the top to play the script. As you will see it will then automatically create the new "_USERS" folder in AD, and automate the creation of our mock users :) P.S. Here and there as the users are being created you will notice some errors but that is simply due to there being some duplicate names from the list of users. The script will still run seemlessly.
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/diagramagain.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Once the script has finish running, looking back at our diagram we essentially have everything setup at this point. Our internet is connected, our NICs are setup, we have the domain setup with our mock users, RAS/NAT is setup, we have DHCP setup for IP addressing, and we are connected to our VMWare Private Network as well. Lastly we just need to create our interal Windows VM client here. Which uses our Internal NIC we created earlier.
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/createnewwindowsvm.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Go back to Virtual Box, then create a new Virtual Machine and name it "CLIENT1". Set the windows version to "Windows 10 (64-bit). If you know how much RAM your system contain you may allocate more than just 2 gigabytes to speed things up, but if not, no worries simply leave as is at 2. Then finalize and hit create.
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/windowsclientbi.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Before we turn on our Windows Client VM, right click the VM and go to settings -> then "Advanced". And change both Shared Clipboard and Drag'n'drop to "Bidirectional", if we ever need to copy and paste anything onto the VM client.
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/allocatemorecores.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Then, go to the System tab and allocate more cores to further speed up the processing of things (ONLY IF YOU KNOW HOW MANY CORES YOUR SYSTEM HAS, IF NOT LEAVE AS IS).
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/changetointernal.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Go to the Network tab and change it to "Internal Network" for it to connect to our Internal NIC. Since we connected it to our Internal NIC it allows our DHCP server to allocate an IP address and also to emulate an actual work-like environment. Finalize those changes and now we can double-click our VM to officially get it running.
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/installwindows10iso.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Once the window pops up, click "Add" then search for your Windows 10 ISO file which we saved onto the desktop from the beginning of this tutorial. Then hit "Start". This process does take a minute to fully install.
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/windows10isosetup.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Once complete, click "I don't have a product key". IMPORTANT: Select Windows 10 Pro NOT HOME as it is not compatible with Windows 10 Home.
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/windows10customdisk.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Accept the terms, then click "Custom Install" because our hard-drive is empty. Then "Next" and "Install". This part also takes awhile to complete. IMPORTANT: Do not "Click any key to start" as it will restart the setup.
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/idonthaveinternet.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Once complete, select your personal region and keyboard layout. If it asks you to connect to internet simply click "I don't have internet" then continue. If it also asks click you are using it for home as well.
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/continuewithlimitedsetup.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Our goal in this part of the process is to NOT create a Microsoft account so if it asks you to, try to login as a local user instead.
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/enteruserasuser.png" width="80%" alt="Disk Sanitization Steps" />
<br />
For your username, enter it as just as "user" for this lab. For password we won't be needing one for this lab so just click "Next" to skip. For the Privacy Settings portion of this turn each and every feature off. Then click "Accept" and finalize. At this point, we'll let Windows finalize and finish setting up. 
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/completediagram.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Looking back at our diagram, we now have our full infrastructure working. We have full connectivity to the default gateway (Domain Controller), then our DC is properly forwarding that traffic (RAS / NAT) to the internet and now can ping back to us as an echo reply.
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/renametoclient1.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Now to change the name of our client desktop. Right click the start menu and hit "Settings". Scroll down and click "Rename this PC (advanced)" and we can join the domain at the same time. Hit the "Change" button then rename to "CLIENT1" as per our diagram. Now under "Member of:" enter our domain "mydomain.com" then hit OK.
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/clientscope.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Go back to our DC, then to the DHCP settings in Server Manager. On the left let's expand the Scope folder, then click Address Leases. We'll see here we have 1 address lease. When we created our client computer and connected it to the donain, it reached out to the DHCP server for an IP address and gave it one. 
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/usersandcomputers.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Staying on our DC Virtual Machine, click the start menu and under Windows Administrative Tools, hit Active Directory Users and Computers. Click the "Computers" container on the left. We'll see here our Client 1 computer pop up. And with that being said we can now use any of the mock user accounts to login to that client VM which is the next step.
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/logintowindowsvm.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Go back to Windows 10 Virtual Machine, click Other User and here you'll notice "Sign into: MYDOMAIN". Remember our usernames are just first initial, lastname. Passwords are just "Password1". Then login. Here it will be creating our user profile since it is our time logging into this machine. This may take awhile. 
<br />
<br />
 
<p align="center">
<img src="https://raw.githubusercontent.com/sebsebastiansandoval/ActiveDirectoryLab/main/images/logintowindowsvm.png" width="80%" alt="Disk Sanitization Steps" />
<br />
Looking back at our network diagram, essentially we've created a mini corporate network. And the  
<br />
<br />
 
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
