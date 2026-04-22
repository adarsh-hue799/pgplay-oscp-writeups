::: page
# nmap {#nmap .title}

\

Starting Nmap 7.98 ( <https://nmap.org> ) at 2026-04-04 17:01 -0400

Nmap scan report for 192.168.56.101

Host is up (0.00062s latency).

Not shown: 65531 closed tcp ports (reset)

PORT STATE SERVICE VERSION

22/tcp open ssh OpenSSH 6.0p1 Debian 4+deb7u7 (protocol 2.0)

\| ssh-hostkey:

\| 1024 c4:d6:59:e6:77:4c:22:7a:96:16:60:67:8b:42:48:8f (DSA)

\| 2048 11:82:fe:53:4e:dc:5b:32:7f:44:64:82:75:7d:d0:a0 (RSA)

\|\_ 256 3d:aa:98:5c:87:af:ea:84:b8:23:68:8d:b9:05:5f:d8 (ECDSA)

80/tcp open http Apache httpd 2.2.22 ((Debian))

\|\_http-title: Welcome to Drupal Site \| Drupal Site

\|\_http-generator: Drupal 7 (<http://drupal.org>)

\|\_http-server-header: Apache/2.2.22 (Debian)

\| http-robots.txt: 36 disallowed entries (15 shown)

\| /includes/ /misc/ /modules/ /profiles/ /scripts/

\| /themes/ /CHANGELOG.txt /cron.php /INSTALL.mysql.txt

\| /INSTALL.pgsql.txt /INSTALL.sqlite.txt /install.php /INSTALL.txt

\|\_/LICENSE.txt /MAINTAINERS.txt

111/tcp open rpcbind 2-4 (RPC #100000)

\| rpcinfo:

\| program version port/proto service

\| 100000 2,3,4 111/tcp rpcbind

\| 100000 2,3,4 111/udp rpcbind

\| 100000 3,4 111/tcp6 rpcbind

\| 100000 3,4 111/udp6 rpcbind

\| 100024 1 34930/tcp status

\| 100024 1 52542/udp status

\| 100024 1 56265/udp6 status

\|\_ 100024 1 59391/tcp6 status

34930/tcp open status 1 (RPC #100024)

MAC Address: 08:00:27:27:DF:79 (Oracle VirtualBox virtual NIC)

Device type: general purpose

Running: Linux 3.X

OS CPE: cpe:/o:linux:linux_kernel:3

OS details: Linux 3.2 - 3.16

Network Distance: 1 hop

Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE

HOP RTT ADDRESS

1 0.62 ms 192.168.56.101

OS and Service detection performed. Please report any incorrect results
at <https://nmap.org/submit/> .

Nmap done: 1 IP address (1 host up) scanned in 15.41 seconds
:::
