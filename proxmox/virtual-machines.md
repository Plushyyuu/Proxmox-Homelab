VM and Container Configuration
=============================

| Category | Minecraft | Docker01 | NetBird | 
| -------- | --------- | -------- | ------- |
| ID | 100 | 101 | 102 |
| Type | VM | VM | LXC | 
| CPU Cores | 4 | 2 | 1 |
| RAM | 20 Gib | 4 Gib | 1 Gib |
| Disk Allocation | 100 Gib | 50 Gib | 7.78 Gib |
| Storage Backend | local-lvm | local-lvm | local-lvm |
| Network Bridge | vmbr 0 | vmbr0 | vmbr0
| Network Type | virtIO | virtIO | veth |
OS | Ubuntu Server 26.04 LTS | Ubuntu Server 26.04 LTS | Ubuntu 26.04 LTS | 

OS Command Line Operations
-----------------------
The following commands found below were used in both the pve, vm's and lxc using Shell to obtain operating system information.

| Location |Command | Purpose |
| ------- | ------- | ------- |
| pve | qm agent <id> get-osinfo | Used for obtaining OS information from a guest VM |
| pve | pct agent <id> get-osinfo | Used for obtaining OS information from a guest container |
| VM 100, 101 & LXC 102 | sudo apt update | Used to obtain online OS repositories for the latest available software versions and patches |
| VM 100, 101 & LXC 102 | sudo apt install qemu-guest-agent -y | installing a respository to establish a communication between guest OS and host hypervisor |
