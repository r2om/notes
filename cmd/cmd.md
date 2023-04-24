# Windows command line

Enable RDP
```cmd
netsh firewall set service type = remotedesktop mode = enable
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fDenyTSConnections /t REG_DWORD /d 0 /f
```

Connect to session
```cmd
QUERY SESSION /SERVER:SERVER.GT.RU
Mstsc.exe /shadow:<ID> /control /noConsentPrompt /v:<Servername>
```
