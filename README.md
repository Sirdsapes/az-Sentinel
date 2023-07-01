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
-Next, we'll go to Microsoft Defender for the Cloud and Environment settings and click the log analytics workspace we just set up under Name.
-Turn SQL servers off and Save and then go to the Data collection section and click All events and Save.
</p>
<br />

<p>
<a href="https://imgtr.ee/image/IKziH"><img src="https://imgtr.ee/images/2023/07/01/edef34b843e4aacc8c61c0546fa1b610.png" alt="edef34b843e4aacc8c61c0546fa1b610.png" border="0"></a>
<a href="https://imgtr.ee/image/IKuIA"><img src="https://imgtr.ee/images/2023/07/01/350a03013901e0eb2232395123f4de0f.png" alt="350a03013901e0eb2232395123f4de0f.png" border="0"></a>
<a href="https://imgtr.ee/image/IKBWr"><img src="https://imgtr.ee/images/2023/07/01/2b0247a45b58d4ea26543a1bf631a947.png" alt="2b0247a45b58d4ea26543a1bf631a947.png" border="0"></a>
</p>
<p>
-Next, we'll connect the log analytics and VM.
-Go back to the Log analytics workspace and reopen the previously-made workspace, i.e. log-honeypot. Click the Virtual machines section in the left box. Then click the VM made earlier, i.e. honeypot, and click Connect.
-While that is connecting, we'll set up Sentinel.
</p>
<br />

<p>
<a href="https://imgtr.ee/image/IKOmj"><img src="https://imgtr.ee/images/2023/07/01/07fe9f701d0b8ab95f74397a15da227b.png" alt="07fe9f701d0b8ab95f74397a15da227b.png" border="0"></a>
<a href="https://imgtr.ee/image/IKavD"><img src="https://imgtr.ee/images/2023/07/01/cc35ef7b963abc46f613c46da94973ae.png" alt="cc35ef7b963abc46f613c46da94973ae.png" border="0"></a>
</p>
<p>
-Go to the VM we set up earlier and copy the Public IP address and then open Remote Desktop Connection from your start menu and past the IP so we can remote into the VM. Remember to use the username and password that was set up when creating the VM earlier.
-When you have finally connected to the VM, open Event Viewer from the Start menu. Expand Windows Logs and click Security -- it will take a bit to load. This is so we can see any major security events, like "Audit Failure".
-Open Windows Defender Firewall with Advanced Security. Click Windows Defender Firewall Property and turn off the firewall in Domain Profile, Private Profile, and Public Profile. This is so we can observe potential malicious activity for this specific lab. Click Apply and OK.
</p>
<br />

<p>
<a href="https://imgtr.ee/image/IKxse"><img src="https://imgtr.ee/images/2023/07/01/5a99d93219538128f5dc545b80a87e58.png" alt="5a99d93219538128f5dc545b80a87e58.png" border="0"></a>
<a href="https://imgtr.ee/image/IKeWx"><img src="https://imgtr.ee/images/2023/07/01/f36e6951b97b43b42202ab0043ca7878.png" alt="f36e6951b97b43b42202ab0043ca7878.png" border="0"></a>
<a href="https://imgtr.ee/image/IKYNb"><img src="https://imgtr.ee/images/2023/07/01/8bfeec71f57a11bc346de87661cf92f2.png" alt="8bfeec71f57a11bc346de87661cf92f2.png" border="0"></a>
<a href="https://imgtr.ee/image/IQHNM"><img src="https://imgtr.ee/images/2023/07/01/9d9fa50de222b008ddfd6efce31b0f6e.png" alt="9d9fa50de222b008ddfd6efce31b0f6e.png" border="0"></a>
</p>
<p>
-We'll be copying a PowerShell script from https://github.com/joshmadakor1/Sentinel-Lab/blob/main/Custom_Security_Log_Exporter.ps1.
-After copying the code, we'll open PowerShell ISE and create a new file and then paste the code.
-Save it to the desktop. Name it how you want. I used Log_Export.
-In the code we just pasted, get the API from line 1, i.e. https://ipgeolocation.io/. Sign up to get an API and paste the API in line 2, i.e. $API_KEY      = "d4600b4efdef42b39828f5155041a457" You can do this in the VM or in your own OS.
-After getting your API, replace the default API in the code with yours and run the script.
</p>
<br />

<p>
<a href="https://imgtr.ee/image/IQsAa"><img src="https://imgtr.ee/images/2023/07/01/151a77c67cc9164173d968b88cd761f0.png" alt="151a77c67cc9164173d968b88cd761f0.png" border="0"></a>
<a href="https://imgtr.ee/image/IQOyU"><img src="https://imgtr.ee/images/2023/07/01/65aa047bf0a922b2854d5ff22852ab9d.png" alt="65aa047bf0a922b2854d5ff22852ab9d.png" border="0"></a>
</p>
<p>
-Next, we go back to the Log Analytics Workspace in Azure. We need to create a new log. Go to Tables and Create (MMA-based).
-Go back to the VM and go to the Program Data folder, i.e. C:\ProgramData\. Open failed_rdp and copy the contents.
</p>
<br />

<p>
<a href="https://imgtr.ee/image/IQ2HW"><img src="https://imgtr.ee/images/2023/07/01/d6dcecfcb0405aa30658616a0f7b2617.png" alt="d6dcecfcb0405aa30658616a0f7b2617.png" border="0"></a>
<a href="https://imgtr.ee/image/IQ6Gl"><img src="https://imgtr.ee/images/2023/07/01/e8c01cb5e76e1850d3e6280ea926abb5.png" alt="e8c01cb5e76e1850d3e6280ea926abb5.png" border="0"></a>
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
