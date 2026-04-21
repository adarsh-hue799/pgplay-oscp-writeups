# 🎯 OffSec Proving Grounds Play — OSCP Prep Writeups

Structured writeups of OffSec Proving Grounds Play machines — all sourced from VulnHub and hosted on the OffSec platform. Documented with full enumeration, exploitation, and privilege escalation steps.

![Status](https://img.shields.io/badge/Status-Active-brightgreen) ![Machines](https://img.shields.io/badge/Machines_Rooted-3-blue) ![Platform](https://img.shields.io/badge/Platform-PG_Play-orange) ![Focus](https://img.shields.io/badge/Focus-OSCP_Prep-darkred)

*Full process documented — recon to root, including what failed and why.*

---

## 🖥️ Machines

| Machine | OS | Difficulty | Author | Key Techniques |
|---------|-----|------------|--------|----------------|
| [Katana](./KATANA) | Linux (Debian) | Easy | SunCSR Team | Web enumeration, CMS default creds, file upload bypass, Python capabilities privesc |
| [DC-1](./DC-1) | Linux (Debian) | Easy | DCAU | Drupal CMS, Drupalgeddon2, SUID exploitation |
| [DC-2](./DC-2) | Linux (Debian) | Easy | DCAU | WordPress, WPScan, CeWL, rbash escape, sudo git |

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

Machines I plan to work through (all 49 from the official OffSec walkthrough playlist):

| Machine | Status |
|---------|--------|
| Katana | ✅ Done |
| DC-1 | ✅ Done |
| DC-2 | ✅ Done |
| DC-4 | ⏳ Pending |
| DC-6 | ⏳ Pending |
| DC-9 | ⏳ Pending |
| BBSCute | ⏳ Pending |
| Blogger1 | ⏳ Pending |
| Born2root | ⏳ Pending |
| BossPlayersCTF | ⏳ Pending |
| BTRSys2.1 | ⏳ Pending |
| Covfefe | ⏳ Pending |
| Dawn | ⏳ Pending |
| Dawn2 | ⏳ Pending |
| Election1 | ⏳ Pending |
| EvilBox-One | ⏳ Pending |
| FunBox | ⏳ Pending |
| FunBoxEasy | ⏳ Pending |
| FunBoxEasyEnum | ⏳ Pending |
| FunboxRookie | ⏳ Pending |
| Gaara | ⏳ Pending |
| Geisha | ⏳ Pending |
| GlasgowSmile | ⏳ Pending |
| HackerFest2019 | ⏳ Pending |
| ICMP | ⏳ Pending |
| Inclusiveness | ⏳ Pending |
| JISCTF | ⏳ Pending |
| LemonSqueezy | ⏳ Pending |
| My-CMSMS | ⏳ Pending |
| NoName | ⏳ Pending |
| OnSystemShellDredd | ⏳ Pending |
| Photographer | ⏳ Pending |
| Potato | ⏳ Pending |
| PyExp | ⏳ Pending |
| Samurai | ⏳ Pending |
| Seppuku | ⏳ Pending |
| SoSimple | ⏳ Pending |
| SunsetDecoy | ⏳ Pending |
| SunsetMidnight | ⏳ Pending |
| SunsetNoontide | ⏳ Pending |
| SunsetTwilight | ⏳ Pending |
| Tre | ⏳ Pending |
| Wpwn | ⏳ Pending |

---

## ⚠️ Disclaimer

All machines documented here are **intentionally vulnerable systems** hosted on OffSec Proving Grounds Play and VulnHub.
These techniques are practiced strictly for educational purposes in an isolated lab environment.
Never test systems without explicit authorization.

---

*Adarsh Dubey · Cybersecurity Student*
