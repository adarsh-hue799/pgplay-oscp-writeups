::: page
# nmap {#nmap .title}

\

Starting Nmap 7.99 ( <https://nmap.org> ) at 2026-05-26 16:33 -0400

Nmap scan report for 192.168.56.119

Host is up (0.00030s latency).

Not shown: 65531 closed tcp ports (reset)

PORT STATE SERVICE VERSION

80/tcp open http Apache httpd 2.4.18 ((Ubuntu))

\|\_http-title: Photographer by v1n1v131r4

\|\_http-server-header: Apache/2.4.18 (Ubuntu)

139/tcp open netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)

445/tcp open netbios-ssn Samba smbd 4.3.11-Ubuntu (workgroup: WORKGROUP)

8000/tcp open http Apache httpd 2.4.18 ((Ubuntu))

\|\_http-server-header: Apache/2.4.18 (Ubuntu)

\|\_http-generator: Koken 0.22.24

\|\_http-title: daisa ahomi

MAC Address: 08:00:27:1C:52:33 (Oracle VirtualBox virtual NIC)

Device type: general purpose

Running: Linux 3.X\|4.X

OS CPE: cpe:/o:linux:linux_kernel:3 cpe:/o:linux:linux_kernel:4

OS details: Linux 3.2 - 4.14

Network Distance: 1 hop

Service Info: Host: PHOTOGRAPHER

Host script results:

\|\_clock-skew: mean: 1h19m58s, deviation: 2h18m34s, median: -2s

\| smb2-security-mode:

\| 3.1.1:

\|\_ Message signing enabled but not required

\| smb-security-mode:

\| account_used: guest

\| authentication_level: user

\| challenge_response: supported

\|\_ message_signing: disabled (dangerous, but default)

\| smb2-time:

\| date: 2026-05-26T20:33:17

\|\_ start_date: N/A

\|\_nbstat: NetBIOS name: PHOTOGRAPHER, NetBIOS user: \<unknown\>,
NetBIOS MAC: \<unknown\> (unknown)

\| smb-os-discovery:

\| OS: Windows 6.1 (Samba 4.3.11-Ubuntu)

\| Computer name: photographer

\| NetBIOS computer name: PHOTOGRAPHER\\x00

\| Domain name: \\x00

\| FQDN: photographer

\|\_ System time: 2026-05-26T16:33:19-04:00

TRACEROUTE

HOP RTT ADDRESS

1 0.30 ms 192.168.56.119

OS and Service detection performed. Please report any incorrect results
at <https://nmap.org/submit/> .

Nmap done: 1 IP address (1 host up) scanned in 16.78 seconds
:::
