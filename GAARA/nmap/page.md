::: page
# nmap {#nmap .title}

\

Starting Nmap 7.99 ( <https://nmap.org> ) at 2026-04-28 11:10 -0400

Nmap scan report for 192.168.56.113

Host is up (0.00064s latency).

Not shown: 65533 closed tcp ports (reset)

PORT STATE SERVICE VERSION

22/tcp open ssh OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)

\| ssh-hostkey:

\| 2048 3e:a3:6f:64:03:33:1e:76:f8:e4:98:fe:be:e9:8e:58 (RSA)

\| 256 6c:0e:b5:00:e7:42:44:48:65:ef:fe:d7:7c:e6:64:d5 (ECDSA)

\|\_ 256 b7:51:f2:f9:85:57:66:a8:65:54:2e:05:f9:40:d2:f4 (ED25519)

80/tcp open http Apache httpd 2.4.38 ((Debian))

\|\_http-server-header: Apache/2.4.38 (Debian)

\|\_http-title: Gaara

MAC Address: 08:00:27:84:44:FD (Oracle VirtualBox virtual NIC)

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

1 0.63 ms 192.168.56.113

OS and Service detection performed. Please report any incorrect results
at <https://nmap.org/submit/> .

Nmap done: 1 IP address (1 host up) scanned in 8.85 seconds
:::
