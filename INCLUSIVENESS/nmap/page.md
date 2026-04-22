::: page
# nmap {#nmap .title}

\

Starting Nmap 7.99 ( <https://nmap.org> ) at 2026-04-22 08:12 -0400

Nmap scan report for 192.168.56.111

Host is up (0.00040s latency).

Not shown: 65532 closed tcp ports (reset)

PORT STATE SERVICE VERSION

21/tcp open ftp vsftpd 3.0.3

\| ftp-anon: Anonymous FTP login allowed (FTP code 230)

\|\_drwxrwxrwx 2 0 0 4096 Feb 08 2020 pub \[NSE: writeable\]

\| ftp-syst:

\| STAT:

\| FTP server status:

\| Connected to ::ffff:192.168.56.1

\| Logged in as ftp

\| TYPE: ASCII

\| No session bandwidth limit

\| Session timeout in seconds is 300

\| Control connection is plain text

\| Data connections will be plain text

\| At session startup, client count was 3

\| vsFTPd 3.0.3 - secure, fast, stable

\|\_End of status

22/tcp open ssh OpenSSH 7.9p1 Debian 10+deb10u1 (protocol 2.0)

\| ssh-hostkey:

\| 2048 06:1b:a3:92:83:a5:7a:15:bd:40:6e:0c:8d:98:27:7b (RSA)

\| 256 cb:38:83:26:1a:9f:d3:5d:d3:fe:9b:a1:d3:bc:ab:2c (ECDSA)

\|\_ 256 65:54:fc:2d:12:ac:e1:84:78:3e:00:23:fb:e4:c9:ee (ED25519)

80/tcp open http Apache httpd 2.4.38 ((Debian))

\|\_http-title: Apache2 Debian Default Page: It works

\|\_http-server-header: Apache/2.4.38 (Debian)

MAC Address: 08:00:27:64:B3:32 (Oracle VirtualBox virtual NIC)

Device type: general purpose

Running: Linux 3.X\|4.X

OS CPE: cpe:/o:linux:linux_kernel:3 cpe:/o:linux:linux_kernel:4

OS details: Linux 3.2 - 4.14

Network Distance: 1 hop

Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE

HOP RTT ADDRESS

1 0.40 ms 192.168.56.111

OS and Service detection performed. Please report any incorrect results
at <https://nmap.org/submit/> .

Nmap done: 1 IP address (1 host up) scanned in 9.04 seconds
:::
