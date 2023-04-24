# Powershell

Uninstall Programm:
```powershell
Get-WmiObject Win32_Product | Where-Object {$_.Name -like "ESET*"} | % {$_.Uninstall} 
```

Get Partition size:
```powershell
Get-Partition | ? {$_.DiskPath -like "*ven_wdc_wd32*"} | Select-Object -Property DiskPath, AccessPaths, @{Name = "Size"; Expression = {"{0:N}" -f [math]::round($_.Size / 1Mb, 2)}}
```
