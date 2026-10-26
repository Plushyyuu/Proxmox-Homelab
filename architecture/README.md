VM Infrastructure
=================
My homelab uses a Proxmox Virtual Environment (VE) to manage virtual machiens and linux containers on one physical server. The network is configured using a virtual Linux bridge to connect the Proxmox host, virtual systems, and to my local home network. 

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

