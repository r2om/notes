# Windows command line

Enable RDP:
```cmd
netsh firewall set service type = remotedesktop mode = enable
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fDenyTSConnections /t REG_DWORD /d 0 /f
```

Connect to RDP session:
```cmd
query session /server:<Servername>
Mstsc.exe /shadow:<Session ID> /control /noConsentPrompt /v:<Servername>
```

Enable admin$ share:
```cmd
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters" /v AutoShareWks /t REG_DWORD /d 1 /f
net stop lanmanserver && net start lanmanserver
```
