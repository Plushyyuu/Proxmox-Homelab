NetBird VPN
===========

Overview
--------
NetBird is used in my Proxmox host server to provide secure remote access to my home server from external networks. 

The purpose of this project is to configure a VPN connection that allows me to remotely access and manage my Proxmox VE without exposing the interface to the public internet.

NetBird runs on a Linux LXC container in my Proxmox host server. 

Why NetBird? 
------------
I needed a lightweight VPN that was open-source. My first option was Tailscale. However, the reason why I did not go with Tailscale because even it is more "simpler" to use than NetBird, is that Tailscale is not fully self-hostable. Tailscale is properietary and data is still managed by Tailscale cloud servers. I wanted something to be more private where I know my data is kept only to my Proxmox server. Thus I found NetBird more trustworthy and even if it was "less" beginner-friendly. I learned how to use NetBird in the end. 

Platforms Used
------------
| Technology | Purpose |
| ---------- | ------- | 
| Proxmox VE | VM Platform | 
| Linux LXC | Hosting the NetBird VPN |
| NetBird | Remote VPN access and peer management |
| Windows | Testing remote access to server client via desktop device | 
| iOS | Testing remote access to server client via smartphone device | 

LXC Configuration
-----------------
| Component | Configuration | 
| --------- | ------------- | 
| Container ID | 102 | 
| Hostname | NetBird | 
| Arch | amd64 | 
| OS | Ubuntu | 
| CPU Cores | 1 |
| Memory | 1.00 Gib | 
| Storage | 7.78 Gib |
| Network Bridge | vmbr0 | 
| LAN Interface | eth0 |
| VPN Interface | wt0 |
| VPN Software | NetBird 0.77.0 | 

NetBird Service Configuration
-----------------------------

| Component | Configuration | 
| --------- | ------------- |
| Service | netbird.service |
| Status | active (running) |
| aaaa | aaaa |

Remote Access Testing
---------------------
To verify remote access, I connected my Windows computer to my university's eduroam Wi-Fi network, outside of my home local network. 

I enabled NetBird and tested connectivity to my Proxmox host server. 

Further documented details for Remote Access Testing can be found here [Remote Access Testing Documentation](./remote-access-testing.md)

NetBird Installation Process
----------------------------
NetBird installation details can be found on [NetBird Installation Process](./netbird-installation.md)

VPN Objectives
--------------
- To use NetBird authentication and access controls.
- To avoid publicly exposing the Proxmox interface.
- Keep VPN updated and Linux container updated.
- Only allow VPN access to personal devices I trust as authorized.

