Minecraft VM -- Server Management 
=================================
Summary
-------
This Ubuntu Server VM hosts multiple Minecraft server instanced managed throug AMP (Application Management Panel). 

Table of Contents
1. AMP (Application Management Panel)
2. Service Behavior
3. AMP Instances
4. Table Understanding
5. AMP Commands
6. journalctl Understanding


AMP (Application Management Panel)
----------------------------------
AMP is used to create and manage Minecraft instances to configure server setting and monitor operations.

| Component | Configurations |
| --------- | -------------- | 
| Software | CubeCoders AMP |
| AMP Version | 2.8.0.4 |
| Stream | Mainline / Release |
| systemmd service | ampinstmgr.service |
| Service file | /etc/systemmd/system/ampinstmgr.service |
| Startup | Enabled at boot | 
| Service Behavior | active (exited) |
| Startup Command | /opt/cubecoders/amp/ampinstmgr startboot true |
| AMP directory | /home/amp/.ampdata/instances/ |

Service Behavior
----------------
ampinstmgr.service starts the AMP instances during boot and exits successfully. The active (exited) status doesn't mean that AMP has stopped, but that the service output confirms that the instances started and shows them as up on the statuses.

AMP Instances 
-------------

| Name | Friendly Name | Module | Web interface binding | AMP web port | AMP Instance Status | 
| ---- | ------------- | ------ | --------------------- | ------------ | ------------------- |
| ADS01 | ADS01 | ADS | 0.0.0.0 | 8080 | Up |
| DeceasedCraft01 | DeceasedCraft | Minecraft | 127.0.0.1 | 8083 | Up | 
| Homestead01 | Homestead | Minecraft | 127.0.0.1 | 8082 | Up | 
| PlushServer01 | Vanilla Server | Minecraft | 127.0.0.1 | 8081 | Up | 

AMP Instances Table Understanding 
-------------------
ADS01 is responsible for creating and managing the other server instances. Not just for Minecraft, but for hosting other instances for different games. ASD01 on interface 0.0.0.0 means AMP listens on all available IPv4 network interfaces. 

The 127.0.0.1 interface for the rest of the instances means that the interface listens to the Ubuntu VM only using local connections for AMP to manage the instances. ADS01 on port 8080 means it manages to multiple instances through the central interface on port 8080. Each instance, 8081 to 8083 are seperate management ports. Each seperate port is for server administration.

AMP Commands 
------------
The following commands were used to verify the AMP configs in the Ubuntu VM shell 

| Commands | Purpose | 
| -------- | ------- |
| systemctl | Used for identifying the name of the AMP services |
| sudo systemctl status ampinstmgr | For inspecting the AMP startup service | 
| systemctl is-enabled ampinstmgr | Verifying the automatic starup for AMP servies | 
| sudo -iu amp ampinstmgre --version | For verifying the AMP instance manager version |
| sudo -iu amp ampinstmgr --ShowInstancesTable | Listing the AMP instances, ports, statuses |
| sudo journalctl -u ampinstmgr -n 30 --no-pager | Reviewing the service logs | 

journalctl Understanding
----------
Upon reviewing the service logs, journalctl recorded the last two days. Some logs included "Waiting for instance to stop..." and "instance was shut down gracefully". The messages indicate that the log for each instance for shutting down gracefully meant each instance was safely shut down. 

Upon the next day, when booting up the instance, some messages included "Waiting for AMP instance to start..." and "AMP instance ADS01 is now running". These message indicates that the instances successfully booted up and is now waiting for my manual inputs in the AMP interface manager to start running the servers. 
