# Powershell

Remove Programm:
```powershell
Get-WmiObject Win32_Product | Where-Object {$_.Name -like "*programm_name*"} | % {$_.Uninstall} 
```

Get Partition size:
```powershell
Get-Partition | ? {$_.DiskPath -like "*disk_vendor*"} | Select-Object -Property DiskPath, AccessPaths, @{Name = "Size"; Expression = {"{0:N}" -f [Math]::Round($_.Size / 1Gb, 2)}} | Format-List
```

Directory size
```powershell
"{0:N} Mb" -f ((Get-ChildItem -Recurse -Path .\Downloads\ -ErrorAction SilentlyContinue | Measure-Object -Property Length -Sum).Sum/1Mb)
```
