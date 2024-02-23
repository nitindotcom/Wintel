Here is the code to fetch the details for DEV)/CLM tickets.
## Task 1: Check if subscriptionmanager is added in the regedit path

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
