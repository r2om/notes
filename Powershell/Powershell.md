# Powershell

Uninstall Programm:
```
Get-WmiObject Win32_Product | Where-Object {$_.Name -like "ESET*"} | % {$_.Uninstall} 
```
