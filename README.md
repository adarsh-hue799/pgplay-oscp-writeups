# 🎯 OffSec Proving Grounds Play — OSCP Prep Writeups

Structured writeups of OffSec Proving Grounds Play machines — all sourced from VulnHub and hosted on the OffSec platform. Documented with full enumeration, exploitation, and privilege escalation steps.

![Status](https://img.shields.io/badge/Status-Active-brightgreen) ![Machines](https://img.shields.io/badge/Machines_Rooted-15-blue) ![Platform](https://img.shields.io/badge/Platform-PG_Play-orange) ![Focus](https://img.shields.io/badge/Focus-OSCP_Prep-darkred)

*Full process documented — recon to root, including what failed and why.*

---

## 🖥️ Machines

| Machine | OS | Difficulty | Author | Key Techniques |
|---------|-----|------------|--------|----------------|
| [Katana](./KATANA) | Linux (Debian) | Easy | SunCSR Team | Web enumeration, CMS default creds, file upload bypass, Python capabilities privesc |
| [DC-1](./DC-1) | Linux (Debian) | Easy | DCAU | Drupal CMS, Drupalgeddon2, SUID exploitation |
| [DC-2](./DC-2) | Linux (Debian) | Easy | DCAU | WordPress, WPScan, CeWL, rbash escape, sudo git |
| [Inclusiveness](./INCLUSIVENESS) | Linux (Debian) | Easy | h4sh5 & Richard Lee | LFI, FTP, PATH hijacking, SUID |
| [Funbox: Rookie](./FUNBOXROOKIE) | Linux (Debian) | Easy | 0815R2d2 | ZIP cracking, rbash escape |
| [JIS_CTF](./JIS_CTF) | Linux (Debian) | Easy | Mohammad Khreesha | File upload bypass, Lateral movement |
| [Gaara](./GAARA) | Linux (Debian) | Easy | 0xJin | Enumeration, gdb privesc |
| [So Simple](./SOSIMPLE) | Linux (Ubuntu) | Intermediate | roel | Social Warfare RCE |
| [TRE: 1](./TRE) | Linux (Debian) | Intermediate | SunCSR Team | Adminer, cron job abuse |
| [SUNSET: MIDNIGHT](./SUNSETMIDNIGHT) | Linux (Debian) | Intermediate | whitecr0wz | MySQL credential abuse |
| [BORN2ROOT](./BORN2ROOT) | Linux (Debian) | Intermediate | Hadi Mene | SSH key exploitation, cronjob abuse |
| [Geisha: 1](./GEISHA) | Linux (Debian) | Easy | SunCSR Team | Web enumeration |
| [Photographer](./PHOTOGRAPHER) | Linux (Ubuntu) | Intermediate | v1n1v131r4 | KOKEN CMS exploitation |
| [DC-4](./DC-4) | Linux (Debian) | Intermediate | DCAU | Command Injection |
| [NoName](./NoName) | Linux (Ubuntu) | Intermediate | haclabs | web exploitation |

---

## ⚙️ Methodology

Every machine follows the same structured approach:

    Reconnaissance     →  passive info gathering
           ↓
    Enumeration        →  nmap, gobuster, wpscan, nikto
           ↓
    Vulnerability      →  manual analysis, CVE lookup
    Discovery
           ↓
    Exploitation       →  metasploit / manual
           ↓
    Privilege          →  linpeas, SUID, sudo -l, capabilities, GTFOBins
    Escalation
           ↓
    Post Exploitation  →  flags, loot

---

## 🔍 Machine Summaries

### Katana

A beginner-friendly boot2root machine built by the SunCSR Team. Runs multiple web services across different ports. Initial access gained through default credentials (`admin:admin`) on a CMS admin panel, followed by exploiting a file upload feature to achieve remote code execution. Privilege escalation achieved via a Linux capability misconfiguration on Python2.7.

- **Ports:** 21 (FTP), 22 (SSH), 80 (HTTP), 7080 (LiteSpeed), 8088 (HTTP), 8715 (HTTP)
- **Exploit:** CMS admin panel default creds → malicious file upload → reverse shell
- **PrivEsc:** `cap_setuid+ep` on `/usr/bin/python2.7` → `os.setuid(0)` → root shell

---

### DC-1

A purposely built vulnerable lab designed as a beginner-friendly boot2root challenge. Runs **Drupal 7** on Apache, exploitable via Drupalgeddon2. Privilege escalation achieved through a misconfigured SUID permission on `/usr/bin/find`. Contains 5 flags with the ultimate goal of reading the flag in root's home directory.

- **Ports:** 22 (SSH), 80 (HTTP - Drupal 7), 111 (RPCBind)
- **Exploit:** Drupalgeddon2 (CVE-2018-7600)
- **PrivEsc:** SUID on `/usr/bin/find` via GTFOBins

---

### DC-2

A follow-up to DC-1, also beginner-friendly. Runs **WordPress** on Apache. Requires generating a custom wordlist with CeWL, brute forcing credentials with WPScan, SSH login as Tom, escaping a restricted bash shell via Vi, switching to Jerry, then exploiting sudo git for root.

- **Ports:** 80 (HTTP - WordPress), 7744 (SSH)
- **Exploit:** WPScan brute force with CeWL wordlist
- **PrivEsc:** rbash escape via Vi, sudo git via GTFOBins

---

### Inclusiveness

A beginner-to-intermediate boot2root machine centered around web enumeration and Local File Inclusion (LFI). Initial access requires identifying a hidden robots.txt by spoofing a Googlebot user agent, discovering an LFI-vulnerable lang parameter, and leveraging anonymous FTP write access to upload a PHP webshell. The uploaded shell is then executed via the LFI parameter to achieve remote code execution. Privilege escalation exploits a PATH hijacking vulnerability in a SUID binary that calls whoami without an absolute path.

- **Ports:**  21 (FTP - anonymous write access), 22 (SSH), 80 (HTTP - Apache, robots.txt, LFI)
- **Exploit:**  Googlebot user agent → robots.txt → LFI via ?lang= parameter → FTP webshell upload → RCE as www-data
- **PrivEsc:** rootshell binary calls whoami without absolute path → fake whoami in /tmp → PATH hijack → root shell

---

### Funbox: Rookie

A beginner-friendly boot2root machine focused on credential discovery and restricted shell escape. Initial access involves anonymous FTP login to download multiple password-protected ZIP files, cracking them with fcrackzip and zip2john, and reusing discovered credentials to SSH into the machine as a restricted user. Privilege escalation achieved by discovering root credentials in a plaintext file within the user's home directory.

- **Ports:**  21 (FTP - anonymous login), 22 (SSH), 80 (HTTP - Apache default page)
- **Exploit:**  Anonymous FTP → download password protected ZIP files → crack with zip2john + John the Ripper → credential reuse for SSH access
- **PrivEsc:** Plaintext root credentials found in home directory file (.mysql_history) → su root → root shell

---

### JIS-CTF

A beginner-friendly boot2root machine focused on web enumeration and file upload exploitation. Initial access requires thorough source code review to discover hidden credentials, followed by authenticating to a restricted web area and exploiting an unrestricted file upload functionality to upload a PHP reverse shell. Lateral movement involves manual file system enumeration to discover a plaintext credentials file leading to SSH access as a privileged user.

- **Ports:**  22 (SSH), 80 (HTTP - Apache)
- **Exploit:**  Source code review → hidden credentials in HTML comments → authenticated file upload → PHP reverse shell → www-data shell
- **PrivEsc:** Manual enumeration → credentials.txt containing plaintext password → SSH as technawi → privileged user access and final flag

---

### Gaara

A beginner-friendly boot2root machine focused on web enumeration and file upload exploitation. Initial access requires thorough source code review to discover hidden directories, those directories were actually a rabbithole.Next step was hydra bruteforcing for the user 'gaara'. Then using linpeas to find the privesc vector which was the gdb suid bit set.Used GTFObins to get root.

- **Ports:**  22 (SSH), 80 (HTTP - Apache)
- **Exploit:**  Hydra Bruteforcing (gaara:iloveyou2)
- **PrivEsc:** Linpeas to find the privesc vector which was the gdb suid bit set

---

### So Simple

An intermediate boot2root machine running WordPress on Ubuntu with intentional rabbit holes. Initial enumeration reveals WordPress with user max — brute forcing credentials is a rabbit hole as the dashboard restricts shell uploads. The real attack path involves identifying Social Warfare plugin version 3.5.0 in page source, researching CVE-2019-9978, and manually crafting a Remote File Inclusion URL pointing to a hosted PHP payload to achieve RCE as www-data. Privilege escalation involves a multi-stage user chain across three accounts before reaching root.

- **Ports:**  22 (SSH), 80 (HTTP - Apache, WordPress 5.4.2, Social Warfare 3.5.0)
- **Exploit:**  CVE-2019-9978 (Social Warfare RFI) → manually crafted swp_url parameter pointing to hosted payload.txt → RCE as www-data → discovered hidden .ssh/id_rsa via LinPEAS → SSH as max
- **PrivEsc:** sudo -l as max → run service as steven via GTFOBins → sudo -l as steven → write reverse shell to /opt/tools/server-health.sh → execute with sudo → root shell

---

### TRE: 1

An intermediate boot2root machine with intentional rabbit holes including a decoy webpage. Initial enumeration reveals three open ports but all attack surface lies on port 80. Directory busting with a larger wordlist uncovers two critical endpoints — Adminer and MantisBT — while the SOL music page is a complete dead end. Enumerating MantisBT with ffuf reveals a config directory containing credentials that chain directly into database access and SSH. Privilege escalation abuses a writable cron job running every second, inserting a SUID bash binary to achieve root.

- **Ports:**  22 (SSH), 80 (HTTP), 8082 (HTTP — decoy SOL music page, rabbit hole)
- **Exploit:**  Directory bust with /usr/share/wordlists/dirb/big.txt → discovered adminer.php and mantisbt → ffuf enumeration of MantisBT → /mantisbt/config/a.txt → leaked database password → Adminer login → user table contains tre credentials → SSH as tre
- **PrivEsc:** LinPEAS yields nothing → pspy64 reveals cron job executing every second on a writable script → inserted chmod u+s /bin/bash → triggered on next cron run → /bin/bash -p → root shell

---

### SUNSET: MIDNIGHT

An intermediate boot2root machine running WordPress with an exposed MySQL port that becomes the primary attack vector. Initial enumeration reveals a WordPress site after domain resolution, with WPScan identifying an admin user. Direct SSH and WordPress brute force are bypassed entirely — the real path is through an unauthenticated MySQL root access on port 3306. Database manipulation allows WordPress admin takeover without cracking the hash, leading to RCE via a malicious plugin. Privilege escalation abuses a custom SUID binary with a relative path vulnerability — a clean PATH hijacking to root.

- **Ports:**  22 (SSH), 80 (HTTP — WordPress after resolving sunset-midnight), 3306 (MySQL — MariaDB)
- **Exploit:**  WPScan → identified admin user → MySQL root login confirmed via Hydra → accessed WordPress database → admin hash uncrackable → replaced hash with custom MD5 (admin) → WordPress admin login → malicious PHP reverse shell via plugin editor → navigated to uploads → caught reverse shell as www-data → found MySQL credentials in wp-config.php → su to jose
- **PrivEsc:**     unknown SUID binary /usr/bin/status → executes service without absolute path → created malicious service file containing /bin/sh in /tmp → exported /tmp to PATH → executed /usr/bin/status → root shell

---

### BORN2ROOT

A beginner-intermediate boot2root with multiple user pivots and a fun final escalation. Port 80 hosts a static SecretSec company page exposing three staff names — useful for username enumeration later. Directory busting uncovers an icons directory containing a hidden .txt file with an RSA private key. SSH requires a legacy algorithm flag due to outdated server configuration. The machine chains through two rabbit holes — a cron job pivot to jimmy yields nothing — before the real path reveals itself: custom wordlist generation using bopscrk based on exposed staff names to brute force the final user, who reuses credentials for root.

- **Ports:**   22 (SSH — legacy), 80 (HTTP — SecretSec static page), 111 (RPC), 57723 (RPC high port)
- **Exploit:**   Directory bust → /icons/ directory → .txt file containing RSA private key → SSH as martin using -oHostKeyAlgorithms=+ssh-rsa legacy flag → enumerated cron job running as jimmy → abused writable cron job → reverse shell as jimmy → dead end, no privesc path
- **PrivEsc:**     Identified staff names from port 80 → generated custom wordlist using bopscrk → brute forced SSH as hadi → credentials reused for su root → root shell

---

### Geisha: 1

A beginner machine with several rabbit holes including a LiteSpeed web server that leads nowhere. Multiple ports expose different services but the real attack surface is a poorly secured HTTP port exposing the system /etc/passwd file directly. Username extracted from passwd, SSH password obtained via brute force, and privilege escalation abuses a non-standard SUID binary to read root's private key — a clean and straightforward chain once the noise is filtered out.

- **Ports:**   Multiple open ports — LiteSpeed web server (rabbit hole), port 7125 (HTTP — exposes /etc/passwd directly)
- **Exploit:**  Retrieved /etc/passwd from port 7125 → extracted username geisha → brute forced SSH password using Hydra → credentials: geisha:letmein → initial shell as geisha
- **PrivEsc:**   Enumerated SUID binaries → found non-standard base32 with SUID bit set → used base32 to encode and read /root/.ssh/id_rsa → decoded and saved private key → SSH as root using stolen key → root shell

---

### Photographer

A beginner-intermediate machine that rewards thorough enumeration across multiple services. SMB enumeration uncovers a readable share containing an internal email that leaks both a username and a password hint. Port 8000 runs a Koken CMS instance with an admin panel — credentials obtained directly from the SMB loot. Initial file upload bypass via extension manipulation fails, but a searchsploit-identified exploit combined with Burp Suite interception achieves RCE. Privilege escalation is clean — a non-standard SUID PHP binary exploited via GTFOBins.

- **Ports:**   80 (HTTP — static, no findings), 139/445 (SMB), 8000 (HTTP — Koken CMS admin panel)
- **Exploit:**  SMB enumeration → sambashare share → mailsent.txt leaks username daisa and password hint babygirl → Koken CMS login on port 8000 → file upload restricted to image extensions → .php.jpg upload caught but unexecutable → searchsploit Koken CMS exploit → Burp Suite intercept → changed extension from .php.jpg to .php → forwarded request → shell uploaded → navigated to upload location → triggered file → caught reverse shell as www-data
- **PrivEsc:**   Enumerated SUID binaries → found php7.2 with SUID bit set → GTFOBins PHP SUID exploit → root shell

---

### DC-4

A beginner-intermediate machine with a non-standard web brute force challenge and a multi-stage user pivot chain. Port 80 hosts an admin login page with no visible error messages — ruling out Hydra directly and requiring wfuzz with response filtering to identify valid credentials. The admin panel executes system commands, providing a clean path to RCE via Burp Suite parameter manipulation. Post-exploitation reveals a password list that drives the next pivot, followed by a mail-based credential leak, and a creative sudo privilege escalation using teehee to directly modify /etc/passwd.

- **Ports:**   22 (SSH), 80 (HTTP — admin login panel)
- **Exploit:**  Login page brute force — Burp and Hydra failed due to no error message, redirect to index.php → wfuzz with -hw 17 to filter baseline responses → password: happy → logged in → admin panel executing ls -l → intercepted POST request in Burp → replaced command with reverse shell payload → caught shell as www-data
- **PrivEsc:**   Enumerated filesystem → found password list → identified 3 users → SSH brute force with Hydra → valid credentials for jim → checked /var/mail/jim → email contained plaintext password for charles → su charles → sudo -l reveals teehee with no password → GTFOBins: appended passwordless root user to /etc/passwd using teehee → su to new user → root shell

---

## 📌 About PG Play

OffSec Proving Grounds Play is a **free** lab platform by Offensive Security. All machines are sourced from the VulnHub community and hosted on the OffSec platform — meaning no local VM setup required, just VPN in and hack.

- ✅ Free tier — 3 hours/day per machine
- ✅ Linux only
- ✅ All machines mirror VulnHub originals
- ✅ Ideal for OSCP preparation

> PG Play machines are the same boxes available on VulnHub. The platform simply makes them easier to access without needing to configure VirtualBox/VMware locally.

---

## 🛠️ Tools Used

![Nmap](https://img.shields.io/badge/-Nmap-blue) ![Gobuster](https://img.shields.io/badge/-Gobuster-lightgrey) ![Linpeas](https://img.shields.io/badge/-Linpeas-yellow) ![GTFOBins](https://img.shields.io/badge/-GTFOBins-black) ![Nikto](https://img.shields.io/badge/-Nikto-green) ![Netcat](https://img.shields.io/badge/-Netcat-red) ![WPScan](https://img.shields.io/badge/-WPScan-red) ![CeWL](https://img.shields.io/badge/-CeWL-orange) ![msfvenom](https://img.shields.io/badge/-msfvenom-blueviolet) ![Metasploit](https://img.shields.io/badge/-Metasploit-purple)

---

## 📁 Each Machine Folder Contains

- Full notes with commands and actual output
- Reasoning behind every step taken
- Screenshots of key findings
- Dead ends — what didn't work and why

---

## 🗺️ Roadmap

Working through 32 machines from the official OffSec PG Play playlist (49 total — 12 skipped as too similar to previously completed machines, 5 excluded as newer additions):

### ✅ Completed (15/32)

| Machine | Difficulty | Key Techniques |
|---------|------------|----------------|
| [Katana](./KATANA) | Easy | File upload, Python capabilities |
| [DC-1](./DC-1) | Easy | Drupalgeddon2, SUID find |
| [DC-2](./DC-2) | Easy | WPScan, CeWL, rbash, sudo git |
| [Inclusiveness](./INCLUSIVENESS) | Easy | LFI, FTP, PATH hijacking, SUID |
| [Funbox: Rookie](./FUNBOXROOKIE) | Easy | ZIP crack, rbash escape |
| [JIS_CTF](./JIS_CTF) | Easy | File upload bypass, Lateral movement |
| [Gaara](./GAARA) | Easy | Enumeration, gdb privesc |
| [So Simple](./SOSIMPLE) | Intermediate | Social Warfare RCE |
| [TRE: 1](./TRE) | Intermediate | Adminer, cron job abuse |
| [SUNSET: MIDNIGHT](./SUNSETMIDNIGHT) | Intermediate | MYSQL credential abuse |
| [BORN2ROOT](./BORN2ROOT) | Intermediate | SSH key exploitation, cronjob abuse |
| [Geisha: 1](./GEISHA) | Easy | Web Enumeration |
| [Photographer](./PHOTOGRAPHER) | Intermediate | KOKEN CMS exploitation |
| [DC-4](./DC-4) | Intermediate | Command Injection |
| [NoName](./NoName) | Intermediate | Web exploitation |

---

### 🟢 Phase 1 

| Machine | Difficulty | Status | Key Focus |
|---------|------------|--------|-----------|
| [Inclusiveness](./INCLUSIVENESS) | Easy | ✅ Done | LFI, FTP, PATH hijacking, SUID |
| [Funbox: Rookie](./FUNBOXROOKIE) | Easy | ✅ Done | ZIP cracking, rbash escape |
| [JIS_CTF](./JIS_CTF) | Easy | ✅ Done | File upload bypass |
| [Gaara](./GAARA) | Easy | ✅ Done | Enumeration, privesc |
| [Geisha](./GEISHA) | Easy | ✅ Done | Web enumeration |
| NoName | Easy | ✅ Done | Web exploitation |
| Wpwn | Easy | ⏳ Pending | WordPress, privesc chain |
| BBSCute | Easy | ⏳ Pending | BBS exploitation |
| EvilBox-One | Easy | ⏳ Pending | Web, chaining techniques |
| Dawn | Easy | ⏳ Pending | Service exploitation |

---

### 🟡 Phase 2

| Machine | Difficulty | Status | Key Focus |
|---------|------------|--------|-----------|
| [So Simple](./SOSIMPLE) | Intermediate | ✅ Done | Social Warfare RCE |
| [Tre: 1](./TRE) | Intermediate | ✅ Done | Adminer, cron job abuse |
| [Sunset: Midnight](./SUNSETMIDNIGHT) | Intermediate | ✅ Done | MySQL credential abuse |
| [Born2Root](./BORN2ROOT) | Intermediate |  ✅ Done | SSH key exploitation |
| [Photographer](./PHOTOGRAPHER) | Intermediate | ✅ Done | KOKEN CMS exploitation |
| Blogger1 | Intermediate | ⏳ Pending | WordPress exploitation |
| Election1 | Intermediate | ⏳ Pending | PHP exploitation |
| LemonSqueezy | Intermediate | ⏳ Pending | WordPress, privilege abuse |
| PyExp | Intermediate | ⏳ Pending | Python exploitation |
| My-CMSMS | Intermediate | ⏳ Pending | CMS exploitation |
| OnSystemShellDredd | Intermediate | ⏳ Pending | Advanced exploitation |

---

### 🔴 Phase 3 — Active Directory

| Machine | Difficulty | Status | Key Focus |
|---------|------------|--------|-----------|
| [DC-4](./DC-4) | Intermediate | ✅ Done | Command injection |
| DC-6 | Intermediate | ⏳ Pending | WordPress, advanced privesc |
| DC-9 | Intermediate | ⏳ Pending | SQLi, port knocking |
| Seppuku | Hard | ⏳ Pending | Complex chaining |
| Samurai | Hard | ⏳ Pending | Advanced techniques |
| ICMP | Hard | ⏳ Pending | Networking, deep exploitation |
| Potato | Hard | ⏳ Pending | Advanced privesc |
| GlasgowSmile | Hard | ⏳ Pending | Hard difficulty chaining |
| Dawn2 | Hard | ⏳ Pending | Advanced service exploitation |
| BTRSys2.1 | Intermediate | ⏳ Pending | Multi-vector attack |
| BossPlayersCTF | Easy | ⏳ Pending | CTF techniques |
| SunsetDecoy | Intermediate | ⏳ Pending | Hash cracking, chkrootkit |
| SunsetNoontide | Intermediate | ⏳ Pending | Web exploitation |
| SunsetTwilight | Intermediate | ⏳ Pending | Advanced chaining |
| Covfefe | Intermediate | ⏳ Pending | Service exploitation |
| HackerFest2019 | Intermediate | ⏳ Pending | CTF techniques |
| FunBox | Easy | ⏳ Pending | WordPress, FTP |
| FunBoxEasy | Easy | ⏳ Pending | Basic exploitation |
| FunBoxEasyEnum | Easy | ⏳ Pending | Enumeration focus |

---

## ⚠️ Disclaimer

All machines documented here are **intentionally vulnerable systems** hosted on OffSec Proving Grounds Play and VulnHub.
These techniques are practiced strictly for educational purposes in an isolated lab environment.
Never test systems without explicit authorization.

---

*Adarsh Dubey · Cybersecurity Student*
