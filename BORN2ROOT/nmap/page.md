::: page
# nmap {#nmap .title}

\

Starting Nmap 7.99 ( <https://nmap.org> ) at 2026-05-19 10:48 -0400

Nmap scan report for 192.168.56.117

Host is up (0.00053s latency).

Not shown: 65531 closed tcp ports (reset)

PORT STATE SERVICE VERSION

22/tcp open ssh OpenSSH 6.7p1 Debian 5+deb8u3 (protocol 2.0)

\| ssh-hostkey:

\| 1024 3d:6f:40:88:76:6a:1d:a1:fd:91:0f:dc:86:b7:81:13 (DSA)

\| 2048 eb:29:c0:cb:eb:9a:0b:52:e7:9c:c4:a6:67:dc:33:e1 (RSA)

\| 256 d4:02:99:b0:e7:7d:40:18:64:df:3b:28:5b:9e:f9:07 (ECDSA)

\|\_ 256 e9:c4:0c:6d:4b:15:4a:58:4f:69:cd:df:13:76:32:4e (ED25519)

80/tcp open http Apache httpd 2.4.10 ((Debian))

\| http-robots.txt: 2 disallowed entries

\|\_/wordpress-blog /files

\|\_http-server-header: Apache/2.4.10 (Debian)

\|\_http-title: Secretsec Company

111/tcp open rpcbind 2-4 (RPC #100000)

\| rpcinfo:

\| program version port/proto service

\| 100000 2,3,4 111/tcp rpcbind

\| 100000 2,3,4 111/udp rpcbind

\| 100000 3,4 111/tcp6 rpcbind

\| 100000 3,4 111/udp6 rpcbind

\| 100024 1 48621/udp6 status

\| 100024 1 52385/tcp6 status

\| 100024 1 56044/udp status

\|\_ 100024 1 57723/tcp status

57723/tcp open status 1 (RPC #100024)

MAC Address: 08:00:27:34:29:A9 (Oracle VirtualBox virtual NIC)

Device type: general purpose

Running: Linux 3.X\|4.X

OS CPE: cpe:/o:linux:linux_kernel:3 cpe:/o:linux:linux_kernel:4

OS details: Linux 3.2 - 4.14

Network Distance: 1 hop

Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE

HOP RTT ADDRESS

1 0.54 ms 192.168.56.117

OS and Service detection performed. Please report any incorrect results
at <https://nmap.org/submit/> .

Nmap done: 1 IP address (1 host up) scanned in 14.12 seconds
:::
