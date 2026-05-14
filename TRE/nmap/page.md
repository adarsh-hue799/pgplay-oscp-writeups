::: page
# nmap {#nmap .title}

\

Starting Nmap 7.99 ( <https://nmap.org> ) at 2026-05-14 09:01 -0400

Nmap scan report for 192.168.56.115

Host is up (0.00058s latency).

Not shown: 65532 closed tcp ports (reset)

PORT STATE SERVICE VERSION

22/tcp open ssh OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)

\| ssh-hostkey:

\| 2048 99:1a:ea:d7:d7:b3:48:80:9f:88:82:2a:14:eb:5f:0e (RSA)

\| 256 f4:f6:9c:db:cf:d4:df:6a:91:0a:81:05:de:fa:8d:f8 (ECDSA)

\|\_ 256 ed:b9:a9:d7:2d:00:f8:1b:d3:99:d6:02:e5:ad:17:9f (ED25519)

80/tcp open http Apache httpd 2.4.38 ((Debian))

\|\_http-title: Tre

\|\_http-server-header: Apache/2.4.38 (Debian)

8082/tcp open http nginx 1.14.2

\|\_http-title: Tre

\|\_http-server-header: nginx/1.14.2

MAC Address: 08:00:27:8A:FF:DE (Oracle VirtualBox virtual NIC)

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

1 0.58 ms 192.168.56.115

OS and Service detection performed. Please report any incorrect results
at <https://nmap.org/submit/> .

Nmap done: 1 IP address (1 host up) scanned in 8.95 seconds
:::
