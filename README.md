# Install-and-configure-pfsense-firewall

In this project, I deployed a "pfSense" firewall on my home network using the following setup:

The network configuration was as follows: Internet connected to an ISP router, which then connected to the WAN interface of pfSense. The LAN interface of pfSense connected to a TP-Link router.

For the infrastructure, I used Proxmox for virtualization. I installed an Intel NIC on my server, upgraded it to an SSD, and increased the RAM.


<pre> STEP 1 
Uploaded the downloaded and unzipped netgate ISO file to Proxmox server
</pre>
![Step 1 Upload](https://github.com/user-attachments/assets/e76af91d-e731-4385-bc5f-7e8331808a38)

<pre>
STEP 2
Deployed the virtual machine designated for pfSense.
</pre>
![Step 2 Create VM](https://github.com/user-attachments/assets/f511e165-e0de-400f-a92c-b93fff471db2)


<pre>
STEP 3
Added the dedicated Intel interface and assigned its ports as a bridge, ensuring the LAN was on a different subnet.
</pre>
![Step 3 Add NIC Interfaces](https://github.com/user-attachments/assets/e7ac7eed-456f-4ddf-a91d-3b57eb6696cf)


<pre>
STEP 4
Started the virtual machine and initiated the pfSense installation. 
</pre>
![Step 4 Installation](https://github.com/user-attachments/assets/50d83ddc-f11f-494f-984f-c90e216e8109)


<pre>
STEP 4b 
During this process, I added the necessary interfaces to pfSense and configured DHCP.
  </pre>
![Step 4 b Adding Interfaces to PFsense](https://github.com/user-attachments/assets/56bc5279-ae58-4258-add0-7a9bb17e5bfc)


<pre>
STEP 5
I encountered a DNS issue, so I deployed a Windows VM to access pfSense. I enabled the DNS Resolver, set the DNS servers and DHCP Gateway, verified all configurations, and ensured connectivity by successfully pinging Google.
</pre>
![Step 5 DNS Issue](https://github.com/user-attachments/assets/d55915b5-4c29-4336-a064-090dbfec3f98)


<pre>
STEP 6
I connected the TP-Link router to my server and configured it with a static IP. I disabled DHCP, set the router to access point mode, and assigned the gateway to pfSense LAN.
</pre>
![Step 6 Configuring TP Link](https://github.com/user-attachments/assets/e77d512d-5971-44cf-81f0-ed271fc0f4fb)


<pre>
STEP 7
I connected to pfSense from my laptop and further configured it, enabling DHCP for LAN and setting the DHCP pool.
</pre>
![Step 7 Enabled DHCP and set configs](https://github.com/user-attachments/assets/f2195dd7-eb77-4d40-91bc-038ef47417dd)

  <pre>
STEP 8
Initially, I planned to install Snort directly on pfSense as an addon. However, after further consideration, I decided to create a standalone VM for Snort. This decision was made to avoid impacting the firewall's performance and to allow for flexible deployment and testing. I planned another technical project to install and configure Snort in a separate VM, allowing me to switch it in and out as needed and easily shut it down and spin it back up for experimentation.
  </pre>
![Step 8 Snort](https://github.com/user-attachments/assets/0abc36a0-3174-477c-8193-61731b7166a6)

