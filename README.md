<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>Observing ICMP Traffic</h2>

- Install Wireshark on VM
- Open Wireshark 
- Ping ICMP traffic only

<h2> Configuring a FireWall<h2>

- Inbound security rules
- Delete the rule and re-enable ICMP traffic in network security group

<h2>FOR ICMP TRAFFIC</h2>

<p>
<img src="https://github.com/user-attachments/assets/42b64483-1e8a-48fc-8a9e-2c20a2a172a9" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
Run Windows 10 VM on Azure, open Remote Desktop to paste the IP address, go into Internet Explorer on the VM, and install Wireshark X64 
</p>
<br />

<p>
<img  src="https://github.com/user-attachments/assets/5361ccf1-31ba-4448-bc9d-3968cca03123" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
Open Wireshark and start packet capture. Within Wireshark, filter for ICMP traffic only

</p>
<br />

<p>
<img  src="https://github.com/user-attachments/assets/a7b7ace1-e233-4f87-ba4b-365b23da16c1" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img  src="https://github.com/user-attachments/assets/e55e462e-b04f-4ac1-81a0-e5907e2f6422" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img <img width="847" alt="image" src="https://github.com/user-attachments/assets/cf5924b5-3951-4565-b109-f0074e99da22" />


</p>
<p>
Retrieve the private IP address of the Ubuntu VM (linux-vm) and attempt to ping it from within the Windows 10 VM. You can see the pings in the 3rd screenshot.

</p>
<br />

<h2> FOR CONFIGURING A FIREWALL<h2>

<p>
<img width="1270" alt="image" src="https://github.com/user-attachments/assets/890333a1-9d72-43ce-b551-614c1f281d8b" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
Open the Linux VM in Azure. Go to the settings, click on network, and edit the Inbound Security Rules as seen in the picture.

</p>
<br />

</p>
<img src="https://github.com/user-attachments/assets/a3a3dc04-59e2-4a53-b7ed-e92fd8180f28" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
When the rule takes effect, it will start to time out and ignore the traffic.

<p>
<img src="https://github.com/user-attachments/assets/b020ef76-d65a-4bf9-b7e5-5a76c98636cf" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
Delete the rule and Re-enable ICMP traffic for the Network Security Group your Ubuntu VM. When you go back to the Windows VM, the ping activity will start working.
