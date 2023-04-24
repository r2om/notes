# Windows command line

Enable RDP
```cmd
netsh firewall set service type = remotedesktop mode = enable
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fDenyTSConnections /t REG_DWORD /d 0 /f
```

Connect to session
```cmd
query session /server:<Servername>
Mstsc.exe /shadow:<Session ID> /control /noConsentPrompt /v:<Servername>
```

Enable admin$ share
```cmd
# Admin$ Share
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters
Устанавливаем параметру типа REG_DWORD «AutoShareServer» для сервера или параметру «AutoShareWks» для рабочей станции значение «1».
Если же необходимо удалить админские шары, то необходимо установить значения «0» для вышеуказанных параметров.
net stop lanmanserver && net start lanmanserver
```
