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

- Create Virtual Machines in Resource Group
- Connect Virtual Machine Remotely
- Observe ICMP Traffic
- Observe SSH Traffic
- Observe DHCP Traffic
- Observe DNS Traffic
- Observe RDP Traffic 

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/i72gwDT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here I created a Resource Group named RG-lab2. I then created two virtual machines named Vm-1 and Vm-2. For Vm-1 I ran it on windows 10 and chose RG-lab2 for its resource group. While creating I allowed it to create a new Virtual Network and Subnet. When creating Vm-2 I used Ubuntu, I chose RG-lab2 for its resource group and Virtual Network. Now I was able to observe within Network Watcher. 

</p>
<br />the c

<p>
<img src="https://i.imgur.com/2tRTmLp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here I connected to Vm-1 remotely using Remote Desktop. I found the public ip address for Vm-1 (20.171.68.49) and connected using the credentials for "labuser". 
</p>
<br />

<p>
<img src="https://i.imgur.com/9Ttvleb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here I installed Wire Shark and filterd for ICMP traffic only. I then retrieved the Private ip address for Vm-2 (10.0.0.5) and attempted to ping it using from with Vm-1.
</p>
<br />


<p>
<img src="https://i.imgur.com/ebJDhG3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here I observed he SSH traffic from Vm-1 on Wire Shark. From Vm-1 SSH into Vm-2 using its private ip address 10.0.0.5
</p>
<br />


<p>
<img src="https://i.imgur.com/GZS0zfy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here I observed DHCP traffic from Wire Shark. From Vm-1 I attempted to issue a new ip address from the command line ipconfig/renew. 
</p>
<br />

<p>
<img src="https://i.imgur.com/qRrgOsw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here I observed the DNS traffic in Wireshark. From Vm-1 in the command line I used nslookup www.disney.com to view the ip address and watched the DNS traffic on Wire Shark afterwards.
</p>
<br />


<p>
<img src="https://i.imgur.com/ySr03Ur.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here I observed the RDP traffic in Wire Shark using tcp.port. Traffic began to spam non stop because the RDP is constantly showing a live stream from one computer to another.
</p>
<br />
