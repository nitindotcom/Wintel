## Health Check 

**With Help of below script you can fetch the Health Check report instantly**

    # Get C drive percentage
    $diskSpace = Get-WmiObject -Class Win32_LogicalDisk | Where-Object { $_.DeviceID -eq 'C:' }
    $cDrivePercentage = "{0:N2}%" -f (($diskSpace.FreeSpace / $diskSpace.Size) * 100)

 

    # Get reboot time in the "DD/MM/YY HH:MM" format
    $lastBootTime = (Get-WmiObject -Class Win32_OperatingSystem).LastBootUpTime
    $lastBootTimeFormatted = [Management.ManagementDateTimeConverter]::ToDateTime($lastBootTime).ToString("dd/MM/yy HH:mm")
 

    # Get memory percentage
    $memoryUsage = (Get-WmiObject -Class Win32_OperatingSystem).FreePhysicalMemory
    $totalMemory = (Get-WmiObject -Class Win32_ComputerSystem).TotalPhysicalMemory
    $memoryPercentage = "{0:N2}%" -f ((($totalMemory - $memoryUsage) / $totalMemory) * 100)

 

    # Get CPU percentage
    $cpuUsage = Get-Counter -Counter "\Processor(_Total)\% Processor Time" | Select-Object -ExpandProperty     CounterSamples | Select-Object -ExpandProperty CookedValue

 

    # Create the formatted output

 

    $output = "| C Free space%: $cDrivePercentage | Server UPTime: $lastBootTimeFormatted |Memory%: $memoryPercentage | CPU %: $cpuUsage% "|

 

    # Output the formatted results
    Write-Host $output
