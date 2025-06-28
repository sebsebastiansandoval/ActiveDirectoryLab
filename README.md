<p align="center">
<img src="https://imgur.com/qk72Wsu.jpeg" alt="osTicket logo"/>
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
<img src="https://imgur.com/dJkUTXJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<h2>Program walk-through:</h2>

<p align="center">
<img src="https://i.imgur.com/OtkPEUL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
First, download Virtual Box for Windows along w/ the Extention Pack via this link here, ?, regardless of the Operating System you're using (e.g. Windows, Linux)
<br />
<br />

<p align="center">
<img src="https://imgur.com/laaaVAI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Download Windows 10 64-bit, save somewhere you will remember (e.g. save to Desktop)
<br />
<br />

<p align="center">
<img src="https://imgur.com/7Swfp63.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Now to create our Virtual Machines, open Oracle Virtual Box and hit "New". We'll name this one DC (Domain Controller), and set to Windows Other (64-bit).
<br />
<br />

<p align="center">
<img src="https://imgur.com/gtZkApl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
We will be allocating 2,048 MBs or 2Gbs of RAM MINIMUM to our VM.Then hit finish and create.
<br />
<br />

<p align="center">
<img src="https://imgur.com/cqjvA6a.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Now our Domain Controller has been created but there is nothing on it yet, before we install Server 2019, we will go to Settings then Advanced. Here change "Shared Clipboard" and "Drag'n'drop" to Bidirectional. Turning that on for Shared Clipboard allows you to actively switch between your live VM and main desktop interchangably, with Drag'n'drop it allows you to drag files from for example your desktop onto the VM.
<br />
<br />

<p align="center">
<img src="https://imgur.com/wghH8Db.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Go to "System" then "Processor", here we will allocate 4 cores instead of 1 as it speeds up the process for everything. But if you don't know how many cores you have or have a weak laptop you can simply keep it at 1 core.
<br />
<br />

<p align="center">
<img src="https://imgur.com/wghH8Db.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Go to "System" then "Processor", here we will allocate 4 cores instead of 1 as it speeds up the process for everything. But if you don't know how many cores you have or have a weak laptop you can simply keep it at 1 core.
<br />
<br />

<p align="center">
<img src="https://imgur.com/a78WTa3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Lastly, go to the "Network" tab we will leave Adapter 1 alone as that will be one of our 2 total NICs for our DC, acting as the external NIC that will be connected to our home internet that will gain us access to browse the internet. Then go to "Adapter 2" we will be setting this adapter as our Internal private NIC so set it as "Internal Network" then hit create.
<br />
<br />

<p align="center">
<img src="https://imgur.com/ZgMUzBq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
<img src="https://imgur.com/ZfGBAKh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
As it finalizes and installs Windows onto the Server this will also take awhile to complete. IMPORTANT DISCLAIMER: As it is downloading the server will restart several times, as it restart it will prompt you to "click any key to boot", IGNORE that and do not click any keys during this process because we do not to boot into the setup again.
<br />
<br />

<p align="center">
<img src="https://imgur.com/jevncQO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
With Server 2019 finally installed, you will be prompted to set an Adminstrative Password, for this password and every other password from this lab onward we will be using the same password "Password1" so we can remember it easily. Just never do that in a real world environment! ;)
<br />
<br />

<p align="center">
<img src="https://imgur.com/OchiQXu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
To login to the VM, you'll notice it will say to do the combined keystroke "Cntrl+Alt+Dlt" to login but when you try to do that it will not work. Depending whether you are using Mac or Windows you'll go to Input then Keyboard, then hit "Insert Cntrl+Alt+Dlt" it will then prompt you to enter our simple password from earlier. "Password1"
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
