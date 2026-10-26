VM Infrastructure
=================
My homelab uses a Proxmox Virtual Environment (VE) to manage virtual machines and Linux containers on one physical server. The network is configured using a virtual Linux bridge to connect the Proxmox host, virtual systems, and my local home network. 

Network Configuration (pve)
---------------------------
| Component | Configuration |
| --------- | ------------- |
| Hypervisor | Proxmox VE 9.2.0 |
| Hostname | pve |
| Physical Network | nic0 |
| Virtual Network | vmbr0 |
| IPv4 Address | 192.168.1.181/24 |
| Subnet | 192.168.1.0 |
| Default Gateway | 192.168.1.1 |
| Assignment | Static | 

Netork Topology
---------------
The physical network interface (nic0) is connected to the virtual network Linux bridge (vmbr0) to provide connectivity between the Proxmox host, VM's, and containers. The Proxmox host is on a static IP address at 192.168.1.181/24 with a default gateway; 192.168.1.1. 

Virtual Infrastructure
----------------------
As of 10/16/2026, the Proxmox host currently contains two virtual machines and one Linux container. 

| ID | Name | Type | Network Bridge | Purpose |
| -- | ---- | ---- | -------------- | ------- | 
| 100 | Minecraft | VM | vmbr0 | Minecraft server hosting |
| 101 | Docker 01 | VM | vmbr0 | Docker environment | 
| 102 | NetBird | LXC | vmbr0 | VPN remote access |

