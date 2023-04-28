# Powershell

### Remove Programm
```powershell
Get-WmiObject Win32_Product | Where-Object {$_.Name -match "Programname"} | % {$_.Uninstall} 
```

### Get Partition size
```powershell
Get-Partition | ? {$_.DiskPath -match "wdc480"} | Select-Object -Property DiskPath, AccessPaths, @{Name = "Size"; Expression = {"{0:N}" -f [Math]::Round($_.Size / 1Gb, 2)}} | Format-List
```

### Directory size
```powershell
"{0:N} Mb" -f ((Get-ChildItem -Recurse -Path .\Downloads\ -ErrorAction SilentlyContinue | Measure-Object -Property Length -Sum).Sum/1Mb)
```

### Administrator access check
```powershell
[bool]([Security.Principal.WindowsIdentity]::GetCurrent().Groups -match 'S-1-5-32-544')
```
### Recursive search
```powershell
Get-ChildItem -Path C:\Windows\System32 -Recurse -ErrorAction SilentlyContinue | select FullName | ? {$_.FullName -match "user32.dll"}
```
```powershell
Get-ChildItem -Path C:\Windows\System32\* -Include user32.dll
```
When the Include parameter is used, the Path parameter needs a trailing asterisk (*) wildcard to specify the directory's contents. For example, -Path C:\Test\*.
