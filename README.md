# network-traffic-monitoring


<p align="center">
<img width="617" height="219" alt="Screenshot 2026-02-15 at 10 31 42 AM" src="https://github.com/user-attachments/assets/894a656f-4b33-4569-9f72-35853fe92ab3" /></p>

<h1>Inspecting Network Protocols: Pre-Production Through Network Traffic Monitoring</h1>
This tutorial follows the creation and deployment of Virtual Machines- observation of Network traffic within the public cloud computing platform Microsoft Azure.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- MacOS</b> 
- Windows 10</b> 
- Linux</b>

<h2>Implementing Virtual Networking Stages</h2>

- Virtual Machine deployment
- Download Packet Sniffer
- Observe ICMP Traffic
- Configuring a Firewall
- Observe DNS and RDP Traffic

<h2>Staging/Pre-production</h2>

Launching Windows VM using the installed "Windows App" on MAC OS operating system.
<img width="1512" height="982" alt="Open wndows-VM" src="https://github.com/user-attachments/assets/42da153f-b8f8-41b3-a539-d81642cec703" />

<p align="center">

Downloading and installing Wireshark the packet sniffer needed to monitor Network traffic on the Virtual Machines.
<img width="1512" height="982" alt="SetUpWireShark" src="https://github.com/user-attachments/assets/87a16cd9-44d6-4493-abc2-0996b0f60cc6" />

Opening up Wireshark and observing the continual stream of traffic being sent through packet capture.
<img width="1512" height="982" alt="openUpWireshark-startPacketCapture-observeTraffic" src="https://github.com/user-attachments/assets/657e0b11-45aa-4b72-9818-b04f43a435fe" />

After filtering for ICMP traffic only, I input the private IP Address for Linux VM, using the ping command along with the Linux private IP, from inside the Windows PowerShell. We can now observe the successful ping requests and replies within WireShark. 
<img width="1512" height="982" alt="Ping-Window-Vm-to Linux_Vm" src="https://github.com/user-attachments/assets/3d8c0b40-e7d8-45c9-b154-1bfa63df22c6" />

Initiating a perpetual ping from the Windows VM to the Linux VM, using the ping command with -t.
<img width="1512" height="982" alt="Perpetual-Ping" src="https://github.com/user-attachments/assets/d50e93ea-9c14-46ff-96bf-2ca54d77c61f" />

Disrupting the perpetual ping, by creating a rule for all inbound traffic. In Azure open the Network Security Group that the Linux VM is using and disable all incoming ICMP traffic.
<img width="1512" height="982" alt="Create-rule-for inbound-traffic" src="https://github.com/user-attachments/assets/c54ea14c-32d8-451b-9ea7-27e1e14a5c01" />

Observing how the rule that was set in Azure to disabled all incoming ICMP traffic, begins to override the perpetual ping. After reenabling the ICMP traffic, the perpetual ping starts up again until prompting the ping activity to stop in the PowerShell with Ctrl + C. 
<img width="1512" height="982" alt="SetRule-Disabled-incoming-ICMP-Traffic" src="https://github.com/user-attachments/assets/58849057-c71e-4605-8108-20ee57db28f0" />

Continuing to observe network traffic by filtering for DNS traffic only. After limiting traffic shown through the packet capture I input nslookup into the PowerShell to ping a public website. I am able to view disney.com’s IP address, and observ the DNS traffic being show in WireShark.
<img width="1512" height="982" alt="DNS-Observation" src="https://github.com/user-attachments/assets/2936c90a-b195-4d71-a447-f9df5ae1c2b7" />

Filter for RDP traffic only (tcp.port == 3389), observing the non-stop spam of traffic, as RDP is a continual live stream from one computer to another.
<img width="1512" height="982" alt="observeConstantLiveStream-trafficFromRDP" src="https://github.com/user-attachments/assets/821d9827-5e8d-4d46-9d6a-b220519afce7" />



# network-traffic-monitoring
