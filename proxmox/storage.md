Storage Configurion
-------------------

My Proxmox server currently uses a Samsung 970 EVO Plus 1TB NVMe SSD to store the Proxmox OS, virtual machine disks, Linux container storage, and other system files. 
The storage is seperated into divided volumes to organize the available space using a GUID Partition Table (GPT). The server uses Logical Volume Manager (LVM) and LVM Thin to manage and allocate storage between the OS and virtual systems. An HDD will be installed in the server in the near future to expand the homelab with new VM's for speccialized purposes.


Physical Storage
----------------
| Component | Configuration |
| --------- | ------------- |
| Model | Samsung SSD 970 EVO Plus |
| Type | NVMe SSD | 
| Estimated Capacity | 1 TB | 
| Detected Capacity | 931.51 GiB | 
| Partition Table | GPT (GUID Parition Table) |
| Logical Sector Size | 512 bytes | 
| Volume Group | pve | 
| Storage Management | LVM/LVM-Thin |
| Root Filesystem | ext4 |

