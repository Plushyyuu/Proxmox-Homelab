NetBird Installation
====================
The purpose of this document is to showcase the process of installing the NetBird VPN in an LXC container on Proxmox VE. 


| Commands | Summary |
| -------- | ------- |
| apt update | Refeshes list of available software | 
| apt upgrade -y | Upgrades current installed packages to new versions |
| apt install curl -y | Installs curl to prepare for NetBird installation |
| curl -fsSL `http://pkgs.netbird.io/install.sh` \| sh | Downlads NetBird and executes the program | 
| netbird up - setup-key <setup_key> | Registers and connects the LXC container to the NetBird network |
| netbird version | Displays the current NetBird version |
| netbird status | Displays VPN connection status | 
| netbird status -d | Displays further VPN information with connections and peers | 
| systemctl status netbird | Checks the NetBird service status |
| systemctl is-enabled netbird | Checks if NetBird service is enabled automatically | 



Why NetBird? 
------------
I needed a lightweight VPN that was open-source. My first option was Tailscale. However, the reason why I did not go with Tailscale because even it is more "simpler" to use than NetBird, is that Tailscale is not fully self-hostable. Tailscale is properietary and data is still managed by Tailscale cloud servers. I wanted something to be more private where I know my data is kept only to my Proxmox server. Thus I found NetBird more trustworthy and even if it was "less" beginner-friendly. I learned how to use NetBird in the end. 

Preparing LXC Container 
-----------------------
The LXC Container was created first and configured with an OS and network connection.

More details and instructions are found on: [Creating an LXC Container](../proxmox/creating-lxc-container.md)
