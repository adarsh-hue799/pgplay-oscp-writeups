::: page
# nmap {#nmap .title}

\

Starting Nmap 7.99 ( <https://nmap.org> ) at 2026-05-18 08:24 -0400

Nmap scan report for 192.168.56.116

Host is up (0.00047s latency).

Not shown: 65532 closed tcp ports (reset)

PORT STATE SERVICE VERSION

22/tcp open ssh OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)

\| ssh-hostkey:

\| 2048 9c:fe:0b:8b:8d:15:e7:72:7e:3c:23:e5:86:55:51:2d (RSA)

\| 256 fe:eb:ef:5d:40:e7:06:67:9b:63:67:f8:d9:7e:d3:e2 (ECDSA)

\|\_ 256 35:83:68:2c:33:8b:b4:6c:24:21:20:0d:52:ed:cd:16 (ED25519)

80/tcp open http Apache httpd 2.4.38 ((Debian))

\|\_http-title: Did not follow redirect to <http://sunset-midnight/>

\|\_http-server-header: Apache/2.4.38 (Debian)

\| http-robots.txt: 1 disallowed entry

\|\_/wp-admin/

3306/tcp open mysql MariaDB 5.5.5-10.3.22

\| mysql-info:

\| Protocol: 10

\| Version: 5.5.5-10.3.22-MariaDB-0+deb10u1

\| Thread ID: 13

\| Capabilities flags: 63486

\| Some Capabilities: Support41Auth, Speaks41ProtocolOld,
IgnoreSpaceBeforeParenthesis, IgnoreSigpipes,
DontAllowDatabaseTableColumn, ODBCClient, SupportsTransactions,
ConnectWithDatabase, InteractiveClient, SupportsLoadDataLocal,
SupportsCompression, LongColumnFlag, FoundRows, Speaks41ProtocolNew,
SupportsMultipleResults, SupportsMultipleStatments, SupportsAuthPlugins

\| Status: Autocommit

\| Salt: \*}\[1}D{aQQ#YxoDElokK

\|\_ Auth Plugin Name: mysql_native_password

MAC Address: 08:00:27:29:E1:CC (Oracle VirtualBox virtual NIC)

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

1 0.47 ms 192.168.56.116

OS and Service detection performed. Please report any incorrect results
at <https://nmap.org/submit/> .

Nmap done: 1 IP address (1 host up) scanned in 9.37 seconds
:::
