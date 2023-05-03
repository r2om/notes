# Nmap

### No port scan
```bash
nmap -sn 192.168.0.0/24
```
The default host discovery done with -sn consists of an ICMP echo request, TCP SYN to port 443, TCP ACK to port 80, and an ICMP timestamp request by default.

### No ping
```bash
nmap -Pn 192.168.0.0/24
```
Disabling host discovery with -Pn causes Nmap to attempt the requested scanning functions against every target IP address specified.
