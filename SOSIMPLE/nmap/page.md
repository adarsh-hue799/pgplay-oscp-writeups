::: page
# nmap {#nmap .title}

\

Starting Nmap 7.99 ( <https://nmap.org> ) at 2026-04-28 15:00 -0400

Nmap scan report for 192.168.56.114

Host is up (0.00052s latency).

Not shown: 65533 closed tcp ports (reset)

PORT STATE SERVICE VERSION

22/tcp open ssh OpenSSH 8.2p1 Ubuntu 4ubuntu0.1 (Ubuntu Linux; protocol
2.0)

\| ssh-hostkey:

\| 3072 5b:55:43:ef:af:d0:3d:0e:63:20:7a:f4:ac:41:6a:45 (RSA)

\| 256 53:f5:23:1b:e9:aa:8f:41:e2:18:c6:05:50:07:d8:d4 (ECDSA)

\|\_ 256 55:b7:7b:7e:0b:f5:4d:1b:df:c3:5d:a1:d7:68:a9:6b (ED25519)

80/tcp open http Apache httpd 2.4.41 ((Ubuntu))

\|\_http-title: So Simple

\|\_http-server-header: Apache/2.4.41 (Ubuntu)

MAC Address: 08:00:27:49:E6:56 (Oracle VirtualBox virtual NIC)

Device type: general purpose\|router

Running: Linux 4.X\|5.X, MikroTik RouterOS 7.X

OS CPE: cpe:/o:linux:linux_kernel:4 cpe:/o:linux:linux_kernel:5
cpe:/o:mikrotik:routeros:7 cpe:/o:linux:linux_kernel:5.6.3

OS details: Linux 4.15 - 5.19, OpenWrt 21.02 (Linux 5.4), MikroTik
RouterOS 7.2 - 7.5 (Linux 5.6.3)

Network Distance: 1 hop

Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE

HOP RTT ADDRESS

1 0.52 ms 192.168.56.114

OS and Service detection performed. Please report any incorrect results
at <https://nmap.org/submit/> .

Nmap done: 1 IP address (1 host up) scanned in 8.87 seconds
:::
