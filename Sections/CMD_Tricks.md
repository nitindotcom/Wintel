## List of basic CMD COmmands 

1. **`systeminfo`**
   - Displays detailed configuration information about the computer's hardware and software.

2. **`hostname`**
   - Shows the name of the current host.

3. **`ipconfig`**
   - Provides detailed IP configuration information for all network adapters.

4. **`netstat`**
   - Displays active TCP connections, ports on which the computer is listening, Ethernet statistics, IPv4 statistics, and IPv6 statistics.

5. **`route print`**
   - Shows the IP routing table for both IPv4 and IPv6.

6. **`arp -a`**
   - Displays the ARP cache, which contains IP-to-physical address mappings.

7. **`ping`**
   - Tests connectivity to a specified host.

8. **`tracert`**
   - Displays the route taken by packets to a specified destination.

9. **`nslookup`**
   - Performs DNS lookups to query domain name servers.

10. **`whoami`**
    - Displays the username and group information for the current user.

11. **`tasklist`**
    - Lists all running processes on the computer.

12. **`tasklist /svc`**
    - Lists all running processes with their associated services.

13. **`driverquery`**
    - Displays a list of all installed device drivers and their properties.

14. **`ver`**
    - Displays the current Windows version.

15. **`ver | find "Version"`**
    - Extracts and displays only the Windows version from the `ver` command output.

16. **`systeminfo | find "Boot Time"`**
    - Shows the system boot time.

17. **`systeminfo | find "System Up Time"`**
    - Displays the system uptime.

18. **`wmic qfe list`**
    - Lists all installed Windows updates.

19. **`wmic qfe get`**
    - Retrieves detailed information about installed Windows updates.

20. **`driverquery /FO list /v`**
    - Lists detailed information about installed device drivers.

21. **`net view`**
    - Lists available network resources.

22. **`net user`**
    - Shows information about user accounts.

23. **`net localgroup`**
    - Lists local groups on the computer.

24. **`net group`**
    - Shows information about global groups on the domain.

25. **`net share`**
    - Displays information about shared resources.

26. **`net session`**
    - Lists information about sessions established on the computer.

27. **`net statistics workstation`**
    - Provides statistics for the workstation service.

28. **`net use`**
    - Shows information about mapped network drives and connections.

29. **`net accounts`**
    - Displays information about user account policies.

30. **`net config workstation`**
    - Shows configuration information for the workstation service.

31. **`net time`**
    - Shows the current date and time on the network.

32. **`net localgroup administrators`**
    - Lists members of the local Administrators group.

33. **`net localgroup "Remote Desktop Users"`**
    - Lists members of the Remote Desktop Users group.

34. **`net localgroup "Power Users"`**
    - Lists members of the Power Users group.

35. **`net localgroup "Backup Operators"`**
    - Lists members of the Backup Operators group.

36. **`net localgroup "Users"`**
    - Lists members of the Users group.

37. **`net localgroup "Guests"`**
    - Lists members of the Guests group.

38. **`net localgroup "Print Operators"`**
    - Lists members of the Print Operators group.

39. **`net localgroup "Replicator"`**
    - Lists members of the Replicator group.

40. **`net localgroup "Account Operators"`**
    - Lists members of the Account Operators group.

41. **`net localgroup "Performance Log Users"`**
    - Lists members of the Performance Log Users group.

42. **`net localgroup "Performance Monitor Users"`**
    - Lists members of the Performance Monitor Users group.

43. **`net localgroup "Distributed COM Users"`**
    - Lists members of the Distributed COM Users group.

44. **`net localgroup "Event Log Readers"`**
    - Lists members of the Event Log Readers group.

45. **`net session`**
    - Lists information about sessions established on the computer.

46. **`net statistics workstation`**
    - Provides statistics for the workstation service.

47. **`net statistics server`**
    - Provides statistics for the server service.

48. **`net accounts`**
    - Displays information about user account policies.

49. **`net computer`**
    - Lists information about computers in the domain.

50. **`net time /querysntp`**
    - Displays the configured Network Time Protocol (NTP) server.

These commands offer valuable insights into various aspects of system administration and network management without altering any settings or configurations.
