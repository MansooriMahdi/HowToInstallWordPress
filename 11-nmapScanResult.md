### nmap scan result: ###
**1. nmap mahdimansoori.ir**
```
Starting Nmap 7.92 ( https://nmap.org ) at 2023-04-02 21:16 +0330
Nmap scan report for mahdimansoori.ir (185.126.10.135)
Host is up (0.30s latency).
Not shown: 995 filtered tcp ports (no-response)
PORT     STATE  SERVICE
22/tcp   closed ssh
53/tcp   open   domain
80/tcp   open   http
443/tcp  open   https
8022/tcp open   oa-system

Nmap done: 1 IP address (1 host up) scanned in 28.12 seconds
```

**2. nmap -sV mahdimansoori.ir**
```
Starting Nmap 7.92 ( https://nmap.org ) at 2023-04-02 21:49 +0330
Nmap scan report for mahdimansoori.ir (185.126.10.135)
Host is up (0.38s latency).
Not shown: 996 filtered tcp ports (no-response)
PORT    STATE  SERVICE  VERSION
22/tcp  closed ssh
53/tcp  open   domain   (unknown banner: [NONE])
80/tcp  open   http     nginx
443/tcp open   ssl/http nginx
1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :
SF-Port53-TCP:V=7.92%I=7%D=4/2%Time=6429C773%P=x86_64-pc-linux-gnu%r(DNSVe
SF:rsionBindReqTCP,33,"\x001\0\x06\x85\0\0\x01\0\x01\0\0\0\0\x07version\x0
SF:4bind\0\0\x10\0\x03\xc0\x0c\0\x10\0\x03\0\0\0\0\0\x07\x06\[NONE\]");

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 67.78 seconds
```