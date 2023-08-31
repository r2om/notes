### Zabbix
```bash
zabbix_get -s 192.168.0.251 -k service.discovery --tls-connect psk --tls-psk-identity fs-gt --tls-psk-file ./fs-gt.psk
```
