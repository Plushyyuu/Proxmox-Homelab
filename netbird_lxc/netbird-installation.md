NetBird Installation
====================


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
