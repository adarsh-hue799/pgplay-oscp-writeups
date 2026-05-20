::: page
# nmap {#nmap .title}

\

Starting Nmap 7.99 ( <https://nmap.org> ) at 2026-05-20 11:50 -0400

Nmap scan report for 192.168.56.118

Host is up (0.00037s latency).

Not shown: 65527 closed tcp ports (reset)

PORT STATE SERVICE VERSION

21/tcp open ftp vsftpd 3.0.3

22/tcp open ssh OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)

\| ssh-hostkey:

\| 2048 1b:f2:5d:cd:89:13:f2:49:00:9f:8c:f9:eb:a2:a2:0c (RSA)

\| 256 31:5a:65:2e:ab:0f:59:ab:e0:33:3a:0c:fc:49:e0:5f (ECDSA)

\|\_ 256 c6:a7:35:14:96:13:f8:de:1e:e2:bc:e7:c7:66:8b:ac (ED25519)

80/tcp open http Apache httpd 2.4.38 ((Debian))

\|\_http-server-header: Apache/2.4.38 (Debian)

\|\_http-title: Geisha

3389/tcp open http nginx 1.14.2

\|\_http-server-header: nginx/1.14.2

\|\_http-title: Seppuku

7080/tcp open ssl/http LiteSpeed httpd

\| tls-alpn:

\| h2

\| spdy/3

\| spdy/2

\|\_ http/1.1

\| ssl-cert: Subject:
commonName=geisha/organizationName=webadmin/countryName=US

\| Not valid before: 2020-05-09T14:01:34

\|\_Not valid after: 2022-05-09T14:01:34

\|\_http-title: Geisha

\|\_http-server-header: LiteSpeed

\|\_ssl-date: TLS randomness does not represent time

7125/tcp open http nginx 1.17.10

\|\_http-title: Geisha

\|\_http-server-header: nginx/1.17.10

8088/tcp open http LiteSpeed httpd

\|\_http-server-header: LiteSpeed

\|\_http-title: Geisha

9198/tcp open http SimpleHTTPServer 0.6 (Python 2.7.16)

\|\_http-server-header: SimpleHTTP/0.6 Python/2.7.16

\|\_http-title: Geisha

MAC Address: 08:00:27:DB:E4:91 (Oracle VirtualBox virtual NIC)

Device type: general purpose\|router

Running: Linux 4.X\|5.X, MikroTik RouterOS 7.X

OS CPE: cpe:/o:linux:linux_kernel:4 cpe:/o:linux:linux_kernel:5
cpe:/o:mikrotik:routeros:7 cpe:/o:linux:linux_kernel:5.6.3

OS details: Linux 4.15 - 5.19, OpenWrt 21.02 (Linux 5.4), MikroTik
RouterOS 7.2 - 7.5 (Linux 5.6.3)

Network Distance: 1 hop

Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE

HOP RTT ADDRESS

1 0.37 ms 192.168.56.118

OS and Service detection performed. Please report any incorrect results
at <https://nmap.org/submit/> .

Nmap done: 1 IP address (1 host up) scanned in 31.08 seconds
:::
