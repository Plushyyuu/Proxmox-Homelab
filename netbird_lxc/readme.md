Work-in-progress

A docemntation of remote access to the host server from outside the local network. A demonstration of accessing the server externally will be recorded.

NetBird VPN
===========

Overview
--------
NetBird is used in my Proxmox host server to provide secure remote access to my home server from external networks. 

The purpose of this project is to configure a VPN connection that allows me to remotely access and manage my Proxmox VE without exposing the interface to the public internet.

NetBird runs on a Linux LXC container in my Proxmox host server. 

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
| ID | 102 | 
| Hostname | NetBird | 
| Arch | amd64 | 
| OS | Ubuntu | 
| CPU Cores | 1 |
| Memory | 1.00 Gib | 
| Storage | 7.78 Gib |
| Network Bridge | vmbr0 | 
| VPN Software | NetBird | 

Remote Access Testing
---------------------
To verify remote access, I connected my Windows computer to my university's eduroam Wi-Fi network, outside of my home local network. 

I enabled NetBird and tested connectivity to my Proxmox host server. 

Further documented details for Remote Access Testing can be found here [Remote Access Testing Documentation](./netbird-screenshots/remote-access-testing.md)

