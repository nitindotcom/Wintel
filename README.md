## Wintel

## Tips
- [**CMD Tips and Tricks**](Sections/CMD_Tricks.md)
-  [**RUN Tips and Tricks**](Sections/RUN_Tricks.md)
  
## [Scripts](Sections/Scripts.md)

###                   CPU / Memory Issue

We get these type of incidents when CPU (or) Memory utilization is high (Both should be <90%). 
 
Title:- " perfmon="" counter="" process-="">% PROCESSOR TIME->JAVA(PID=5128) has breached threshold 90 for 30 minutes. 
 
Sol: 
  - Login to the server
  - Open task manager
  - In Processes tab check the Cpu\Memory utilization based on title→Monitor for 5 min→
  - If the utilization is below threshold Close the incident→
   -Else take screenshot of processes which utilizes more & send mail to respective ADM / SG and ask to engage with respective team
    - **if the process is related to wintel then ask for reboot Approval**


###                      How to find MultiPathOutPutLogs?

Log in to that server 
Open CMD as Administrator 
> **Run the below command**
> 
> "mpclaim -s -d "

Then right click and select all then hit enter 

Save the file to jump server "xyz" as .txt
Then To import that file to ur local machine , Take rdp of that jump (xyx) server then directly copy paste on your local server 

###                                  Service Related Incident
 
Title : - Service (s):> 'APEX ONE NT REAL TIME SCAN' not running !
 
**NOTE : - Only start the services whose startup type is ''Automatic''**
 
Steps to resolve :
- Login to the Server 
- Open run (WIN+r) -> give " services.msc " command and click ok
- Search For the required Service -> right click and click on "start" to start the Service
- Make sure the service is in started or Running State.
Now ,
Close the Inclident By giving Solutions 

