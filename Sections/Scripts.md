# Basic Scripts for wintel Team 
Hey ! here u can find basic scipts for wintel team.

 Basic Scripts and their usages  
 
 ![image](https://github.com/nitindotcom/Wintel/assets/71180362/b90689bf-3209-4809-a70a-c1ddd416dbe0)

# Table of Content
- [C Drive cleanup](Scripts/Cdrive.md)
  
    - This script will perform basic clenup on c drive , it clears Recycle bin , CCMCache folder

- [To Check Uptime](Scripts/UpTime.md)
  
    - It will help you to get to uptime of the server/ computer.

- [To Get Patch details](Scripts/PatchDetails.md)

   -Simplifies the process of obtaining patch details, facilitating efficient management of system updates.

- [To fix event flow alerts](Scripts/OVOagentRestart.md)

   - Addresses event flow alerts swiftly, ensuring smooth operation of systems by restarting OVO Agents.


- [To Get Vendor details of any server](Scripts/VendorDetailComp.md)

   - Quickly fetches vendor details for any specified server, enhancing vendor management processes.

- [To Get Eventflow logs using Date as var](Scripts/logsByDate.md)

   - Facilitates the retrieval of event flow logs using a specified date as a variable, aiding in troubleshooting and analysis.


- [To Get basic server details](Scripts/ServerDetails.md)

    - Retrieves fundamental information about servers, providing a comprehensive overview of system configurations.

- [To get basic details of a particular service](Scripts/ServiceDetail.md)

    - Obtains basic details of a particular service, assisting in service management and troubleshooting.

- [Health Check](Scripts/HealthCheck.md)

    - Performs a thorough health check of servers, identifying potential issues and ensuring optimal performance.

- [To fetch Cluster node details](Scripts/ClusterNodeDetails.md)

    - Retrieves essential details of cluster nodes, aiding in the management and monitoring of clustered environments.

-[DEVO/CLM Stale endpoints (Non-Compliant):](Scripts/Devo_clm.md)
- 
        1.         Check if subscriptionmanager is added in the regedit path below.

              HKLM\SOFTWARE\Policies\Microsoft\Windows\EventLog\EventForwarding\SubscriptionManager 

              Example: "Server=http://CB2574138.ad.cibc.com:5985/wsman/SubscriptionManager/WEC,Refresh=900" 

        2.         Check if "NETWORK SERVICE" is added in "Event Log Readers" in local group

        3.         Run the below commands.

             %systemroot%\system32\klist.exe -lh 0 -li 0x3e4 purge
             net stop winrm
             net start winrm
