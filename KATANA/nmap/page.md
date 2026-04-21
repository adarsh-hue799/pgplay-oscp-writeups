::: page
# nmap {#nmap .title}

\

nmap -p- -A -T4 192.168.56.109

Starting Nmap 7.99 ( <https://nmap.org> ) at 2026-04-21 11:44 -0400

Nmap scan report for 192.168.56.109

Host is up (0.00047s latency).

Not shown: 65527 closed tcp ports (reset)

PORT STATE SERVICE VERSION

21/tcp open ftp vsftpd 3.0.3

22/tcp open ssh OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)

\| ssh-hostkey:

\| 2048 89:4f:3a:54:01:f8:dc:b6:6e:e0:78:fc:60:a6:de:35 (RSA)

\| 256 dd:ac:cc:4e:43:81:6b:e3:2d:f3:12:a1:3e:4b:a3:22 (ECDSA)

\|\_ 256 cc:e6:25:c0:c6:11:9f:88:f6:c4:26:1e:de:fa:e9:8b (ED25519)

80/tcp open http Apache httpd 2.4.38 ((Debian))

\|\_http-title: Katana X

\|\_http-server-header: Apache/2.4.38 (Debian)

139/tcp open netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)

445/tcp open netbios-ssn Samba smbd 4.9.5-Debian (workgroup: WORKGROUP)

7080/tcp open ssl/http LiteSpeed httpd

\| tls-alpn:

\| h2

\| spdy/3

\| spdy/2

\|\_ http/1.1

\|\_ssl-date: TLS randomness does not represent time

\|\_http-title: Katana X

\| ssl-cert: Subject:
commonName=katana/organizationName=webadmin/countryName=US

\| Not valid before: 2020-05-11T13:57:36

\|\_Not valid after: 2022-05-11T13:57:36

\|\_http-server-header: LiteSpeed

8088/tcp open http LiteSpeed httpd

\|\_http-server-header: LiteSpeed

\|\_http-title: Katana X

8715/tcp open http nginx 1.14.2

\|\_http-title: 401 Authorization Required

\| http-auth:

\| HTTP/1.1 401 Unauthorized\\x0D

\|\_ Basic realm=Restricted Content

\|\_http-server-header: nginx/1.14.2

MAC Address: 08:00:27:65:68:6F (Oracle VirtualBox virtual NIC)

Device type: general purpose\|router

Running: Linux 4.X\|5.X, MikroTik RouterOS 7.X

OS CPE: cpe:/o:linux:linux_kernel:4 cpe:/o:linux:linux_kernel:5
cpe:/o:mikrotik:routeros:7 cpe:/o:linux:linux_kernel:5.6.3

OS details: Linux 4.15 - 5.19, OpenWrt 21.02 (Linux 5.4), MikroTik
RouterOS 7.2 - 7.5 (Linux 5.6.3)

Network Distance: 1 hop

Service Info: Host: KATANA; OSs: Unix, Linux; CPE:
cpe:/o:linux:linux_kernel

Host script results:

\| smb-os-discovery:

\| OS: Windows 6.1 (Samba 4.9.5-Debian)

\| Computer name: katana

\| NetBIOS computer name: KATANA\\x00

\| Domain name: \\x00

\| FQDN: katana

\|\_ System time: 2026-04-21T11:45:16-04:00

\| smb2-time:

\| date: 2026-04-21T15:45:16

\|\_ start_date: N/A

\|\_clock-skew: mean: 1h19m58s, deviation: 2h18m34s, median: -2s

\|\_nbstat: NetBIOS name: KATANA, NetBIOS user: \<unknown\>, NetBIOS
MAC: \<unknown\> (unknown)

\| smb-security-mode:

\| account_used: guest

\| authentication_level: user

\| challenge_response: supported

\|\_ message_signing: disabled (dangerous, but default)

\| smb2-security-mode:

\| 3.1.1:

\|\_ Message signing enabled but not required

TRACEROUTE

HOP RTT ADDRESS

1 0.47 ms 192.168.56.109

OS and Service detection performed. Please report any incorrect results
at <https://nmap.org/submit/> .

Nmap done: 1 IP address (1 host up) scanned in 30.88 seconds
:::
