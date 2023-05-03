# Nmap

### No port scan
```bash
nmap -sn 192.168.0.0/24
```
The default host discovery done with -sn consists of an ICMP echo request, TCP SYN to port 443, TCP ACK to port 80, and an ICMP timestamp request by default.
