<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Set up Microsoft Azure Virtual Machines with proper resource and network groups and any additional resources needed.
- Using Remote Desktop, sign into Azure Virtual Machine and install Wireshark.
- Using Wireshark and Powershell, use Various Command-Line Tools to observe various Network Protocol traffic between virtual machines.
- Add additional security rules within Azure's Virtual Machine in the Azure portal to disable/enable various rules involving Network Protocols.

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/Trf67t1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Setting up all of your resources should give you access to your virtual machine, its IP address, network security and also other useful resources. I set up both a Windows 10 virtual machine and also an Ubuntu Server virtual machine. Using Remote Control, we log into the Windows 10 virtual machine and install Wireshark in order to observe traffic between our virutal machines.
</p>
<br />

<p>
<img src="https://i.imgur.com/e35am6T.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Using Wireshark and Powershell, we are then able to observe traffic between our virtual machines network and also other networks as well. With Wireshark, we are able to filter what we can see such as if we are only looking for ICMP, UDP or even SSH. In this example I log into the Ubuntu virtual machine using SSH on the Windows 10 virtual machine. The Wireshark application in the background displays how many interactions are happening between the two virtual machines, the source of interactions, the destinations and the information that is being transmitted. For SSH, everytime we type something into the PowerShell while we are signed in through SSH, there will be an SSH signal transferring between the Windows 10 virtual machine and the Ubuntu Virtual Machine. Potentially we could also use Wireshark to test network connectivity with pings between local computers or even online networks.
</p>
<br />

<p>
<img src="https://i.imgur.com/LopwCeZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In the Ubuntu Inbound security rules, we deny any inbound ICMP signals to be denied. To do this we add an additional setting to the inbound security rules and make sure that the priority is correct. This makes it so that on our Windows 10 virtual machine, anytime we try to singal with ICMP to the Ubuntu virtual machine, there will be no response unless we update the security rules. 
</p>
<br />
