Proxmox VE Infrastructure
=========================


Summary
-------
My personal homelab uses the Proxmox Virtual Environment to host and manage multiple VM's and Linux containers on a single physica server. Proxmox allows me to allocate hardware resources, manage virtual machines and systems, and to monitor the health and statuses of my homelab

Hardware Specifications
| Component | Configuration | 
| --------- | ------------- |
| Processor | AMD Ryzen 5 4600 G (1 Socket) | 
| CPU Cores | 6 Cores & 12 Threads |
| Memory | 32 Gib | 
| Storage | 1 TB | 
| VM Platform | Proxmox VE 9.2.0 | 
| Manager | 9.2.2 |
| Linux Kernal | 7.0.2-6-pve | 
| Boot Mode | UEFI |

VM's and Container's 
As of 10/26/26, the homelab currently contains two virtual machines and one container. Below are the systems and their purposes.

| ID | Name | Type | Purpose |
| -- | ---- | ---- | ------- | 
| 100 | Minecraft | VM | Minecraft Server Hosting |
| 101 | Docker01 | VM | Docker Environment |
| 102 | NetBird | LXC | VPN Remote access to homelab | 

Network Architecture
--------------------
The homelab is configured on network bridge (vmbr0) to provide network connectivity between the host, virtual machines, and Linux containers. 

More details to Network Architecture are found in [architecture](/architecture)

Storage Management 
------------------
Proxmox provides central storage management for virtual machine management, ISO images, and backup. 

More details to Storage Management are found in [placeholder]

System Maintenance 
------------------
Managing VM resources, monitoring resource utilization, troubleshooting services, and configuring resources are all configured through the Proxmox web interface and Linux Shell.

More details to System Management are found in [placeholder]



