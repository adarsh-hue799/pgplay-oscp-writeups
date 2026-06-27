::: page
# nmap {#nmap .title}

\

┌──(root㉿kali)-\[/home/adarsh\]

└─# nmap -p- -A -T4 192.168.56.123

Starting Nmap 7.99 ( <https://nmap.org> ) at 2026-06-26 12:50 -0400

Nmap scan report for 192.168.56.123

Host is up (0.00042s latency).

Not shown: 65534 closed tcp ports (reset)

PORT STATE SERVICE VERSION

80/tcp open http Apache httpd 2.4.29 ((Ubuntu))

\|\_http-title: Site doesn\'t have a title (text/html; charset=UTF-8).

\|\_http-server-header: Apache/2.4.29 (Ubuntu)

MAC Address: 08:00:27:65:EC:11 (Oracle VirtualBox virtual NIC)

Device type: general purpose

Running: Linux 4.X\|5.X

OS CPE: cpe:/o:linux:linux_kernel:4 cpe:/o:linux:linux_kernel:5

OS details: Linux 4.15 - 5.19, OpenWrt 21.02 (Linux 5.4)

Network Distance: 1 hop

TRACEROUTE

HOP RTT ADDRESS

1 0.42 ms 192.168.56.123

OS and Service detection performed. Please report any incorrect results
at <https://nmap.org/submit/> .

Nmap done: 1 IP address (1 host up) scanned in 8.84 seconds
:::
