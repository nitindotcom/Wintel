Here is the code to fetch the details for DEV)/CLM tickets.
## Task 1: Check if subscriptionmanager is added in the regedit path
#### the command checks whether the SubscriptionManager key exists under the specified registry path and displays any relevant information if it does.

#### If the specified registry key does not exist, you can expect to see a message indicating that the key was not found. The exact error message would depend on the version of Windows and the specific context in which the command is executed.
```plaintext
   ERROR: The system was unable to find the specified registry key or value.

```

```plaintext
reg query "HKLM\SOFTWARE\Policies\Microsoft\Windows\EventLog\EventForwarding\SubscriptionManager"
```

## Task 2: Check if "NETWORK SERVICE" is added in "Event Log Readers" in local group

```plaintext
net localgroup "Event Log Readers"
```

## Task 3: Run the below commands

```plaintext
%systemroot%\system32\klist.exe -lh 0 -li 0x3e4 purge
net stop winrm
net start winrm
```
