Creating LXC Container in Proxmox VE
====================================

The purpose of this markdown file is to document the process of creating an LXC container within the Proxmox VE environment.

For this demonstration, a test LXC container named "test" is created to document the process of deploying the NetBird VPN within the Proxmox Host with details at: [placeholder]

Creating LXC Container
----------------------

1. Logged into Proxmox VE web interface
2. Selected Proxmox data center node: (pve)
3. Clicked on "Create CT" in the interface
4. Configured container settings

Step 1: OS System Templete
--------------------------
| Setting | Configuration |
| ------- | ------------- | 
| Template Storage | local |  
| Operating System | Ubuntu | 
| OS Version | 26.04 | 
| File Name | ubuntu-26.04-standard_26.04-1_amd64.tar.zst |

Ubuntu OS is located in the local storage of the pve.

Template Screenshot

![template](./proxmox-screenshots/template_os.png)

Step 2: Disk Allocation
-----------------------
