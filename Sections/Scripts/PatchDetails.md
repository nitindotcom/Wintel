## Patch Details

**With help of below script u get Patch details for last 45 days with count and C drive percentage , Boot time , OS , Memory , CPU and automatic services which are not started yet.**
    
    # Get installed patches (KB names) in the last 45 days

 

    #$installedPatches = (Get-HotFix | Where-Object { $_.InstalledOn -gt (Get-Date).AddDays(-45) } | Select-Object -Property HotFixID, InstalledOn | ForEach-Object { "$($_.HotFixID)-$($_.InstalledOn.ToString("dd/MM/yy HH:mm"))" }) -join ", "
    $installedPatches1 = Get-HotFix | Where-Object { $_.InstalledOn -gt (Get-Date).AddDays(-45) } | Select-Object -Property HotFixID
    #$installedPatches = (Get-HotFix | Where-Object { $_.InstalledOn -gt (Get-Date).AddDays(-45) } | Select-Object -Property HotFixID, InstalledOn, Description | ForEach-Object { "$($_.HotFixID) -$($_.InstalledOn.ToString("dd/MM/yy HH:mm")) -$($_.Description)" }) -join ", "

 

    $installedPatches = (Get-HotFix | Where-Object { $_.InstalledOn -gt (Get-Date).AddDays(-45) } |
    Select-Object -Property HotFixID, InstalledOn, Description, InstalledBy |
    ForEach-Object {
        "$($_.HotFixID) -$($_.InstalledOn.ToString("dd/MM/yy")) -$($_.Description) -$($_.InstalledBy)"
    } ) -join ", "

 

    #$installedPatches -join ", "

 

    # Get total patch count installed in the last 45 days
    $totalPatchCount = $installedPatches1.Count

 

    # Get C drive percentage
    $diskSpace = Get-WmiObject -Class Win32_LogicalDisk | Where-Object { $_.DeviceID -eq 'C:' }
    $cDrivePercentage = "{0:N2}%" -f (($diskSpace.FreeSpace / $diskSpace.Size) * 100)

 

    # Get reboot time in the "DD/MM/YY HH:MM" format
    $lastBootTime = (Get-WmiObject -Class Win32_OperatingSystem).LastBootUpTime
    $lastBootTimeFormatted = [Management.ManagementDateTimeConverter]::ToDateTime($lastBootTime).ToString("dd/MM/yy HH:mm")

 


     # Get OS version

 

     $osVersion = (Get-WmiObject -Class Win32_OperatingSystem).Caption

 


     # Get automatic services that are not started
     $automaticServices = Get-Service | Where-Object { $_.StartType -eq 'Automatic' -and $_.Status -ne 'Running' } | Select-Object -Property Name

 

       # Get memory percentage
       $memoryUsage = (Get-WmiObject -Class Win32_OperatingSystem).FreePhysicalMemory
       $totalMemory = (Get-WmiObject -Class Win32_ComputerSystem).TotalPhysicalMemory
       $memoryPercentage = "{0:N2}%" -f ((($totalMemory - $memoryUsage) / $totalMemory) * 100)

 

       # Get CPU percentage
      $cpuUsage = Get-Counter -Counter "\Processor(_Total)\% Processor Time" | Select-Object -ExpandProperty CounterSamples | Select-Object -ExpandProperty CookedValue

 

      # Create the formatted output

 

    $output = "Installed Patches (last 45 days): $installedPatches "," | Total Patch Count (last 45 days): $totalPatchCount | C Free space%: $cDrivePercentage | Server UPTime: $lastBootTimeFormatted |OS Version: $osVersion | Automatic Services Not Started: $($automaticServices.Name -join ', ') | Memory%: $memoryPercentage | CPU %: $cpuUsage% "

 

    # Output the formatted results
    Write-Host $output
