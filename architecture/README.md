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
| 101 | Docker01 | VM | vmbr0 | Docker environment | 
| 102 | NetBird | LXC | vmbr0 | VPN remote access |


VM 100 - Minecraft
------------------
VM 100 is a VM used for hosting Minecraft servers using an Ubuntu environment. It is configured with a VirtIO network adapter connected to vmbr0.

VM 101 - Docker01
-----------------
VM 101 is a VM used for Docker-based applications. It is also configured with a VirtIO network adpater connected to vmbr0.

LXC 102 - NetBird
-----------------
LXC 102 currently runs in a unprivileged Ubuntu container.It is also configured with a VirtIO network adpater connected to vmbr0. LXC 102 uses DHCP and was assigned to 192.168.1.190/24. The container is used for VPN connectivety to remotely access the Proxmox host from outside my local network. 

Network Commands
----------------
The commands found below were used to identify the configuration settings of the Proxmox host, VM's, and container. 

| Command | Purpose |
| ------- | ------- |
| ip -br addr | Used to display the network interfaces and ip addresses |
| ip route | Used to display the host routing table | 
| ip link show | For inspecting the network interfaces | 
| bridge link show | For identifying the bridge connected interfaces | 
| qm config 100 | Inspecting the Minecraft VM configuration settings | 
| qm config 101 | Inspecting the Docker01 VM configuration settings | 
| pct config 102 | Inspecting the NetBird container configuration settings |
| pct exec 102 ip addr | Inspecting the Netbird container IP configurations | 
| pct exec 102 -- ip a | Inspecting the network interfaces in Netbird container | 
