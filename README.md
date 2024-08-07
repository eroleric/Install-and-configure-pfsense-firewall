# Install-and-configure-pfsense-firewall

On this project will be deploying "pfSense" firewall on my home network following this diagram
Internet > ISP Router > WAN PFSense > LAN PFsense > TP-Link Router

I am using Proxmox for virtualization also installed an Intel NIC on my server, upgraded to an SSD and upgraded the RAM.


Step 1 
Downloaded and unzipped the netgate zip for pfsense and uploaded the ISO to my proxmox server
![Step 1 Upload](https://github.com/user-attachments/assets/e76af91d-e731-4385-bc5f-7e8331808a38)

Step 2
Deployed the vm I will use for PFsense
![Step 2 Create VM](https://github.com/user-attachments/assets/f511e165-e0de-400f-a92c-b93fff471db2)

Step 3
Adding the dedicated Intel interface and assigning its ports as a bridge making sure LAN is on a different subnet
![Step 3 Add NIC Interfaces](https://github.com/user-attachments/assets/e7ac7eed-456f-4ddf-a91d-3b57eb6696cf)

Step 4
Started vm and proceeded to installation 
![Step 4 Installation](https://github.com/user-attachments/assets/50d83ddc-f11f-494f-984f-c90e216e8109)

Step 4b 
Added Interfaces to Pfsense and configured dhcp
![Step 4 b Adding Interfaces to PFsense](https://github.com/user-attachments/assets/56bc5279-ae58-4258-add0-7a9bb17e5bfc)

Step 5
Ran into a dns issue so deployed a windows vm to access pfsense and enabled DNS Resolver, Set the DNS servers, DHCP Gateway and made sure all the configurations were correct and able to ping google.
![Step 5 DNS Issue](https://github.com/user-attachments/assets/d55915b5-4c29-4336-a064-090dbfec3f98)

Step 6
Connected TP-LINK router to my server and configured the router making sure i have a static IP and turned off dhcp while setting the routers mode into access point mode and set the gateway to my pfsense LAN
![Step 6 Configuring TP Link](https://github.com/user-attachments/assets/e77d512d-5971-44cf-81f0-ed271fc0f4fb)

Step 7
I am now able to connect to pfsense from my laptop and configured it further enabling dhcp for lan and setting the dhcp pool
![Step 7 Enabled DHCP and set configs](https://github.com/user-attachments/assets/f2195dd7-eb77-4d40-91bc-038ef47417dd)

Step 8
my initial idea was to install snort directly to pfsense as an addon but after reading a bit more ive decided to go with a standalone vm and make another project for it. since i am running a home server i may not always want snort on 24/7 that may impact the performance of the firewall so i will do another technical project of installing and configuring snort in a separate vm where i can switch it in line and outline however i like and easily shut it down and spin it back up after my experimenting. 
![Step 8 Snort](https://github.com/user-attachments/assets/0abc36a0-3174-477c-8193-61731b7166a6)

