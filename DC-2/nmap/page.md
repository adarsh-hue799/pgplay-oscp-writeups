::: page
# nmap {#nmap .title}

\

Starting Nmap 7.98 ( <https://nmap.org> ) at 2026-04-05 10:33 -0400

Nmap scan report for 192.168.56.102

Host is up (0.00051s latency).

Not shown: 65533 closed tcp ports (reset)

PORT STATE SERVICE VERSION

80/tcp open http Apache httpd 2.4.10 ((Debian))

\|\_http-server-header: Apache/2.4.10 (Debian)

\|\_http-title: Did not follow redirect to <http://dc-2/>

7744/tcp open ssh OpenSSH 6.7p1 Debian 5+deb8u7 (protocol 2.0)

\| ssh-hostkey:

\| 1024 52:51:7b:6e:70:a4:33:7a:d2:4b:e1:0b:5a:0f:9e:d7 (DSA)

\| 2048 59:11:d8:af:38:51:8f:41:a7:44:b3:28:03:80:99:42 (RSA)

\| 256 df:18:1d:74:26:ce:c1:4f:6f:2f:c1:26:54:31:51:91 (ECDSA)

\|\_ 256 d9:38:5f:99:7c:0d:64:7e:1d:46:f6:e9:7c:c6:37:17 (ED25519)

MAC Address: 08:00:27:BE:D8:27 (Oracle VirtualBox virtual NIC)

Device type: general purpose

Running: Linux 3.X\|4.X

OS CPE: cpe:/o:linux:linux_kernel:3 cpe:/o:linux:linux_kernel:4

OS details: Linux 3.2 - 4.14, Linux 3.8 - 3.16

Network Distance: 1 hop

Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE

HOP RTT ADDRESS

1 0.51 ms 192.168.56.102

OS and Service detection performed. Please report any incorrect results
at <https://nmap.org/submit/> .

Nmap done: 1 IP address (1 host up) scanned in 9.88 seconds
:::
