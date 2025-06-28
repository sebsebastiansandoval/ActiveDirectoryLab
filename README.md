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

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
