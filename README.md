# Install-and-configure-pfsense-firewall

On this project will be deploying "pfSense" firewall on my home network following this diagram 

Internet > ISP Router > WAN PFSense > LAN PFsense > TP-Link Router

Proxmox for  virtualization 
Installed an Intel NIC on my server, upgraded to an SSD and upgraded the RAM.


Step 1 
Fownloaded and unzipped the netgate zip for pfsense and uploaded the ISO to my proxmox server


Step 2
Deployed the vm I will use for PFsense

Step 3
Adding the dedicated Intel interface and assigning its ports as a bridge making sure LAN is on a different subnet

Step 4
Started vm and proceeded to installation 

Step 4b 
Added Interfaces to Pfsense and configured dhcp

Step 5
Ran into a dns issue so deployed a windows vm to access pfsense and enabled DNS Resolver, Set the DNS servers, DHCP Gateway and made sure all the configurations were correct and able to ping google.

Step 6
Connected TP-LINK router to my server and configured the router making sure i have a static IP and turned off dhcp while setting the routers mode into access point mode and set the gateway to my pfsense LAN

Step 7
I am now able to connect to pfsense from my laptop and configured it further enabling dhcp for lan and setting the dhcp pool

Step 8
my initial idea was to install snort directly to pfsense as an addon but after reading a bit more ive decided to go with a standalone vm and make another project for it. since i am running a home server i may not always want snort on 24/7 that may impact the performance of the firewall so i will do another technical project of installing and configuring snort in a separate vm where i can switch it in line and outline however i like and easily shut it down and spin it back up after my experimenting. 
