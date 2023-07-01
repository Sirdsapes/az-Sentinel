# az-Sentinel
Setting up Azure Sentinel and monitoring attacks
<p align="center">
<a href="https://ibb.co/72ZfxzR"><img src="https://i.ibb.co/gzf2b7P/image.png" alt="image" border="0"></a>
</p>

<h1>Setting up Azure Sentinel and monitoring attacks</h1>
In this tutorial, we will be setting up Sentinel in Azure Virtual Machines and monitoring activity. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Sentinel
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Actions and Observations</h2>

</p>
<p>
-First, we are going to create a VM in Azure. 
-Within the VM, create a new Resource Group and name it -- I used honeypotlab.
-Name the VM -- I used honeypot. Choose Windows 10 Pro as the image.
-Fill out the rest of the information as needed. Size of the VM is up to you, but Standard should be fine.
-Click Next: Disks and then Next: Networking.
-In the NIC network security group section, click Advanced and Create new in the Configure network security group section underneath.
-Remove the default inbound rule and create a new one. Change Destination port ranges to * to allow all and a high priority so it's not filtered.
-Click OK and then Review + create and Create after validation has passed and the VM will begin setting up.
</p>
<br />

<p>
<a href="https://imgtr.ee/image/I04rW"><img src="https://imgtr.ee/images/2023/07/01/ea0ed3f68c2773e52ae56e96d9bafb37.png" alt="ea0ed3f68c2773e52ae56e96d9bafb37.png" border="0"></a>
<a href="https://ibb.co/x5dv72m"><img src="https://i.ibb.co/PC0p6rT/New-RG.png" alt="New-RG" border="0"></a>
<a href="https://ibb.co/KyCHgBm"><img src="https://i.ibb.co/Lp4fyBv/VM-Setup-1.png" alt="VM-Setup-1" border="0"></a>
<a href="https://imgtr.ee/image/I0RUK"><img src="https://imgtr.ee/images/2023/07/01/8de7790da8e3cb4ad260522dfd897706.png" alt="8de7790da8e3cb4ad260522dfd897706.png" border="0"></a>
<img src="https://imgtr.ee/images/2023/07/01/4f5f90735c9ec0ac894d4b9528256a49.png" alt="4f5f90735c9ec0ac894d4b9528256a49.png" border="0">
<img src="https://imgtr.ee/images/2023/07/01/b23807b4dae9d9b06cc9ba36ae2dde84.png" alt="b23807b4dae9d9b06cc9ba36ae2dde84.png" border="0">
<a href="https://imgtr.ee/image/IKila"><img src="https://imgtr.ee/images/2023/07/01/9f5026b685a986a6c606ff1f96b7f3a6.png" alt="9f5026b685a986a6c606ff1f96b7f3a6.png" border="0"></a>
</p>
<p>
-Next, we'll create a Log analytics workspace. Create a new log analytics workspace.
-Select the resource group set up earlier, i.e. honeypotlab.
-Name the workspace and select the same region as before.
-Click Review + create and Create after validation has passed to create the workspace just like with the VM.
</p>
<br />

<p>
<a href="https://ibb.co/b1sBFxz"><img src="https://i.ibb.co/Nx9jrXZ/VM-Log.png" alt="VM-Log" border="0"></a>
<a href="https://imgtr.ee/image/IKC7x"><img src="https://imgtr.ee/images/2023/07/01/a78a1a7d9e3f66c69b55a71840e82faf.png" alt="a78a1a7d9e3f66c69b55a71840e82faf.png" border="0"></a>
<a href="https://imgbb.com/"><img src="https://i.ibb.co/fYwqZm4/Vm-Log-Dep.png" alt="Vm-Log-Dep" border="0"></a>
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
