::: page
# nmap {#nmap .title}

\

Starting Nmap 7.99 ( <https://nmap.org> ) at 2026-04-26 09:14 -0400

Nmap scan report for 192.168.56.112

Host is up (0.00060s latency).

Not shown: 65533 closed tcp ports (reset)

PORT STATE SERVICE VERSION

22/tcp open ssh OpenSSH 7.2p2 Ubuntu 4ubuntu2.1 (Ubuntu Linux; protocol
2.0)

\| ssh-hostkey:

\| 2048 af:b9:68:38:77:7c:40:f6:bf:98:09:ff:d9:5f:73:ec (RSA)

\| 256 b9:df:60:1e:6d:6f:d7:f6:24:fd:ae:f8:e3:cf:16:ac (ECDSA)

\|\_ 256 78:5a:95:bb:d5:bf:ad:cf:b2:f5:0f:c0:0c:af:f7:76 (ED25519)

80/tcp open http Apache httpd 2.4.18 ((Ubuntu))

\|\_http-server-header: Apache/2.4.18 (Ubuntu)

\| http-robots.txt: 8 disallowed entries

\| / /backup /admin /admin_area /r00t /uploads

\|\_/uploaded_files /flag

\| http-title: Sign-Up/Login Form

\|\_Requested resource was login.php

MAC Address: 08:00:27:6F:1D:15 (Oracle VirtualBox virtual NIC)

Device type: general purpose

Running: Linux 3.X\|4.X

OS CPE: cpe:/o:linux:linux_kernel:3 cpe:/o:linux:linux_kernel:4

OS details: Linux 3.2 - 4.14, Linux 3.8 - 3.16

Network Distance: 1 hop

Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE

HOP RTT ADDRESS

1 0.60 ms 192.168.56.112

OS and Service detection performed. Please report any incorrect results
at <https://nmap.org/submit/> .

Nmap done: 1 IP address (1 host up) scanned in 8.97 seconds
:::
