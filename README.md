# network-traffic-monitoring


<p align="center">
<img width="617" height="219" alt="Screenshot 2026-02-15 at 10 31 42 AM" src="https://github.com/user-attachments/assets/80dd86d9-53e4-4d16-9990-1f9e8712dc62" />


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
<img width="1512" height="982" alt="Open wndows-VM" src="https://github.com/user-attachments/assets/cba120e2-49d8-47b0-8f8d-2907795e0997" />

Downloading and installing Wireshark the packet sniffer needed to monitor Network traffic on the Virtual Machines.
<img width="1512" height="982" alt="SetUpWireShark" src="https://github.com/user-attachments/assets/04516429-1e18-4a3d-b9e0-3db62221369e" />

Opening up Wireshark and observing the continual stream of traffic being sent through packet capture.
<img width="1512" height="982" alt="openUpWireshark-startPacketCapture-observeTraffic" src="https://github.com/user-attachments/assets/5b53d004-b441-49ea-9cd1-0c8c7627d28f" />

After filtering for ICMP traffic only, I input the private IP Address for Linux VM, using the ping command along with the Linux private IP, from inside the Windows PowerShell. We can now observe the successful ping requests and replies within WireShark. 
<img width="1512" height="982" alt="Ping-Window-Vm-to Linux_Vm" src="https://github.com/user-attachments/assets/3d41800f-28e5-4418-961f-1514967bd279" />

Initiating a perpetual ping from the Windows VM to the Linux VM, using the ping command with -t.
<img width="1512" height="982" alt="Perpetual-Ping" src="https://github.com/user-attachments/assets/ad511652-bb88-4222-894a-6dc2b9a26f11" />

Disrupting the perpetual ping, by creating a rule for all inbound traffic. In Azure open the Network Security Group that the Linux VM is using and disable all incoming ICMP traffic.
<img width="1512" height="982" alt="Create-rule-for inbound-traffic" src="https://github.com/user-attachments/assets/f90459b1-4b27-435b-bb92-60d25ba4b7f0" />

Observing how the rule that was set in Azure to disabled all incoming ICMP traffic, begins to override the perpetual ping. After reenabling the ICMP traffic, the perpetual ping starts up again until prompting the ping activity to stop in the PowerShell with Ctrl + C. 
<img width="1512" height="982" alt="SetRule-Disabled-incoming-ICMP-Traffic" src="https://github.com/user-attachments/assets/caefbd9d-e63a-4b48-83fd-3abcf5ecde47" />

Continuing to observe network traffic by filtering for DNS traffic only. After limiting traffic shown through the packet capture I input nslookup into the PowerShell to ping a public website. I am able to view disney.com’s IP address, and observ the DNS traffic being show in WireShark.
<img width="1512" height="982" alt="DNS-Observation" src="https://github.com/user-attachments/assets/3c79b899-476a-4f0f-ad6b-57dfdf0aa5fc" />

Filter for RDP traffic only (tcp.port == 3389), observing the non-stop spam of traffic, as RDP is a continual live stream from one computer to another.
<img width="1512" height="982" alt="observeConstantLiveStream-trafficFromRDP" src="https://github.com/user-attachments/assets/8039747f-bb0d-4c3b-b5a2-e28d5a3f5a99" />




# network-traffic-monitoring
