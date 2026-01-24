# pfSense Firewall Setup Project

## Objective

The objective of this project is to learn how to set up pfSense firewall to secure a network by controlling incoming and outgoing traffic in a simple way, implementing network segmentation. The project aims to enhance network security, improve traffic management, and provide hands-on experience with pfSense firewall.

## Skills Learned

- Firewall configuration and management
- Traffic filtering using firewall rules and NAT
- Network segmentation using VLANs
- Monitoring and troubleshooting network traffic
- Understanding TCP/IP, routing, and subnetting

## Tools

- pfSense Firewall – Open-source Community Edition (CE) 
- Virtualization Software: VMware Workstation Pro
- Client Operating Systems: Windows 11, Ubuntu Linux
- Web Browser – For pfSense web-based management interface
- ISO Images – pfSense installation media

<img width="551" height="611" alt="pfsense" src="https://github.com/user-attachments/assets/a91f175c-d414-4b95-b5ae-b4d2d34808a5" />


## Step
- Set up VMware Workstation Pro
- Set up Ubuntu and Windows 11 onto VMware machine
- Next, download pfSense firewall CE version from pfSense website > choose "AMD64 ISO IPMI/Virtual Machines" option > I got a file that end with .iso.gz so, I need to download "7-Zip file manager" > extracted to .iso file
- Create New Virtual machine set the name to `pfSense`
- Edit virtual machine settings
- Memory: `2GB`
- Processors: `2` In my case, but you can increase to `4` if you want
- Network Adapter: `Bridged`
- Select "Add.." below and choose "Network Adapter" 2 times
- For the "Network Adapter 2" we will choose "LAN segmant: `LAN Segment 1`"
- For the "Network Adapter 3" we will choose "LAN segmant: `LAN Segment 2`"

![1](https://github.com/user-attachments/assets/2cce1fb7-4775-4624-953f-eef7c105a3cf)

- Next we have to set Ubuntu and Windows 11 to corresponding LAN Segments
- On Windows 11 > Network Adapter: `LAN Segment 1`
- On Ubuntu > Network Adapter: `LAN Segment 2`

### Installing pfSense
- Power up pfsense from virtual machine that we just made > accept > install > "Please select the WAN interface" so we will select to first one
![2](https://github.com/user-attachments/assets/8e62ae6c-c2ee-48e0-9683-ce6505d89e04)
- Then press "OK"
- Next, we have to select the LAN interface > select the second options and set up according to our diagram
![3](https://github.com/user-attachments/assets/95c95fde-2d06-473e-b070-196cb2fafe7f)
- Next, it will show that
- LAN: `em1`
- WAN: `em0`
- Selected "Install CE" > OK > OK > Choose the "Current Stable version" > Hit enter > Installing process is start (It might take a while) > Reboot
![4](https://github.com/user-attachments/assets/8b0af03b-6f89-4e87-89e8-cd370e5b3257)

- We can see the IP for WAN is DHCP as we expected and LAN is `10.1.1.1/24`
- Hit number 3 to "Reset admin account and password" > create your own password
- We will go to configure on GUI on our LAN side
- Go to Windows 11 machine


