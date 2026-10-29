Storage Configurion
-------------------

My Proxmox server currently uses a Samsung 970 EVO Plus 1TB NVMe SSD to store the Proxmox OS, virtual machine disks, Linux container storage, and other system files. 
The storage is seperated into divided volumes to organize the available space using a GUID Partition Table (GPT). The server uses Logical Volume Manager (LVM) and LVM Thin to manage and allocate storage between the OS and virtual systems. 

A large volume HDD will be installed in the server in the near future to expand the homelab with new VM's for specialized purposes such as a backup storage system.


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

The NVMe SSD uses three partitions for system booting and storage management. The largest partition is used by LVM to manage logical volumes for the Proxmox host and its virtual systems. 

Active Storage 
--------------
| Storage | Type | Capacity | Used | Available | 
| ------- | ---- | -------- | ---- | --------- |
| local | Directory | 93.94 GiB | 9.13 Gib | 79.99 Gib | 
| local-lvm | LVM-Thin | 794.30 Gib | 34.47 Gib | 759.83 GiB |


Disk Partitioning 
-----------------
The Samsung NVMe SSD uses GPT with three partitions.

Disk partitioning table was verified using fdisk -l /dev/nvme0n1.

| Paritition | Size | Type | Purpose |
| ---------- | ---- | ---- | ------- |
| nvme0n1 | 1007 Kib | BIOS Boot | For BIOS bootloader support | 
| nvme0n2 | 1 Gib | EFI System | EFI Boot partition on /boot/efi | 
| nvme0n3 | 930.5 Gib | Linux LVM | Proxmox LVM physical volume |

SMART Health Results 
--------------------

The NVMe SSD health status was reviewed using smartctl.

Review on 10/29/2026

| Attribute | Record |
| --------- | ------ |
| Device | Samsung SSD 970 EVO Plus |
| Assessment | PASSED |
| Critical Warning | 0x00 | 
| SSD Temp | 36 C |
| Available Space | 100% | 
| Percentage Used | 1% |
| Data Read | 85.6 TB |
| Data Written | 25.0 TB |
| Power-On Hours | 9,438 Hours | 
| Unsafe Shutdowns | 223 | 
| Integrity Errors | 0 | 
| Error Information Log Entries | 13,389 |

The Samsung NVMe SSD was used for originally for a Windows 11 desktop for 2 years before being reused for the Proxmox host server. The SSD passed the overall SMART Health Assessment with no critical warning at 0x00 indicating the SSD was used carefully to prevent wear and tear. 

However, when investigating further, the SSD experienced 223 unsafe shutdowns and 13,389 error information log entries. The entries will be investigated to determine if the logs have any purpose. 











