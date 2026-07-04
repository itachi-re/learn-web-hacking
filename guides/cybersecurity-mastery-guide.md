# 🛡️ The Complete Cybersecurity Mastery Guide (2026 Edition)
### From Zero to Job-Ready — No Degree Required

> *"Security is always excessive until it's not enough."* — Robbie Sinclair

---

## Table of Contents

1. [Why Cybersecurity in 2026](#1-why-cybersecurity-in-2026)
2. [The Honest Truth Before You Start](#2-the-honest-truth-before-you-start)
3. [The Full Roadmap at a Glance](#3-the-full-roadmap-at-a-glance)
4. [Phase 1 — Foundations](#4-phase-1--foundations-months-16)
5. [Phase 2 — Core Security Concepts](#5-phase-2--core-security-concepts-months-710)
6. [Phase 3 — Ethical Hacking & Penetration Testing](#6-phase-3--ethical-hacking--penetration-testing-months-1115)
7. [Phase 4 — Reverse Engineering & Binary Exploitation](#7-phase-4--reverse-engineering--binary-exploitation-months-1524)
8. [Certifications Roadmap](#8-certifications-roadmap)
9. [Practice Platforms & Labs](#9-practice-platforms--labs)
10. [Daily & Weekly Study Routine](#10-daily--weekly-study-routine)
11. [Building Your Portfolio](#11-building-your-portfolio)
12. [Job Hunting Strategy (No Degree)](#12-job-hunting-strategy-no-degree)
13. [Essential Books](#13-essential-books)
14. [Communities & Networking](#14-communities--networking)
15. [Tools Arsenal](#15-tools-arsenal)
16. [Common Mistakes to Avoid](#16-common-mistakes-to-avoid)

---

## 1. Why Cybersecurity in 2026

The cybersecurity talent shortage is not hype — it is a structural, decade-long crisis. There are currently **3.4 million unfilled cybersecurity positions globally** (ISC2 Workforce Study). The World Economic Forum and Accenture found that among organizations with low cyber resilience, **85% cited missing critical skills** as the root cause — not lack of budget or technology.

This creates a rare professional opportunity: the field actively needs you, and it does not require a computer science degree to enter. Self-taught professionals compete directly with graduates because the industry prizes demonstrable skills over credentials.

Key trends shaping the field right now:
- **AI integration** — 60% of hiring managers cite finding candidates with AI + cybersecurity skills as their single greatest recruiting challenge (Fortinet 2026 Global Skills Report)
- **Cloud security** — no longer optional; it is a baseline expectation
- **Zero Trust architecture** — the dominant enterprise security model being deployed everywhere
- **91% of IT decision-makers** prefer candidates who hold technology-focused certifications when hiring

---

## 2. The Honest Truth Before You Start

Before the roadmap, internalize these realities:

**What will work for you:**
- Cybersecurity is a meritocracy. Your GitHub, your writeups, your CTF rank, and your certs speak louder than your degree status.
- Self-taught people in this field routinely outperform graduates because the field rewards curiosity and consistent practice above all else.
- You can get an entry-level job ($50–80K+ range) within 18–24 months of focused self-study. Remote-international contracts available from Bangladesh/South Asia can pay 3–5× local rates at senior levels.

**What will challenge you:**
- The depth of knowledge required for specialized roles (especially reverse engineering) is genuinely hard. Plan for 2+ years, not 6 months.
- Consistency beats intensity. Two hours every day beats twelve hours on a Sunday.
- Imposter syndrome is endemic in this field. Push through it by doing more labs, not by reading more theory.

**The law is not optional:**
- Only test systems you own, control, or have **explicit written permission** to test.
- CTF platforms, HackTheBox, and TryHackMe VPN environments are your safe practice ground.
- Bug bounty programs provide legal scope for testing real systems. Respect it absolutely.

---

## 3. The Full Roadmap at a Glance

```
PHASE 1: FOUNDATIONS              (Months 1–6)
├── Linux & Command Line
├── Networking Fundamentals
├── Windows Administration
└── Python Scripting

PHASE 2: CORE SECURITY            (Months 7–10)
├── Security Concepts & Frameworks
├── Network Security
├── Web Application Security
└── First CTF Competitions

PHASE 3: ETHICAL HACKING & PENTEST (Months 11–15)
├── Penetration Testing Methodology
├── Active Directory Attacks
├── Web App Hacking (Advanced)
├── Bug Bounty Hunting
└── OSCP Preparation

PHASE 4: REVERSE ENGINEERING      (Months 15–24+)
├── Assembly Language (x86/x64)
├── Binary Analysis (Static & Dynamic)
├── Malware Analysis
├── Binary Exploitation
└── Specialized Tools (Ghidra, IDA, x64dbg)

CERTIFICATION TRACK (Overlaps throughout)
├── ISC2 CC           → Month 3
├── eJPT              → Month 9
├── CompTIA Security+ → Month 11
├── OSCP              → Month 18+
└── GREM / OSED       → Month 24+
```

---

## 4. Phase 1 — Foundations (Months 1–6)

This phase is non-negotiable. Trying to learn penetration testing before understanding networking is like studying surgery before anatomy. Do not skip this phase.

---

### 4.1 Linux & Command Line (Month 1–2)

Linux is the language of hacking. Kali Linux runs on it. Most servers you will ever attack run on it. Become fluent.

**What to learn:**
- File system hierarchy (`/`, `/etc`, `/var`, `/tmp`, `/home`, `/proc`)
- File permissions (`chmod`, `chown`, `umask`)
- Process management (`ps`, `top`, `kill`, `systemctl`)
- Networking commands (`ip`, `ss`, `netstat`, `curl`, `wget`, `nc`)
- Text manipulation (`grep`, `awk`, `sed`, `cut`, `sort`, `uniq`)
- Shell scripting in Bash (loops, conditionals, functions)
- Package management (apt, dnf, pacman)
- SSH, SCP, rsync

**Resources (Free):**
- **OverTheWire: Bandit** — bandit.overthewire.org — the best Linux CLI game. Do all 34 levels.
- **The Linux Command Line** by William Shotts — free PDF at linuxcommand.org
- **TryHackMe: Linux Fundamentals** (3-part room series) — free
- **explainshell.com** — paste any command and get it explained, great for self-checking

**Milestone:** You can navigate the filesystem, write a basic Bash script, and manage files/processes without Googling every command.

---

### 4.2 Networking Fundamentals (Month 2–3)

Every attack traverses a network. You cannot exploit what you do not understand.

**What to learn:**
- OSI model and where each attack targets which layer
- TCP/IP — the three-way handshake, flags, states
- DNS — how name resolution works (and how to abuse it)
- HTTP/HTTPS — requests, responses, methods, status codes, headers
- ARP, DHCP, NAT, routing basics
- Subnetting and CIDR notation
- Firewalls, proxies, VPNs at a conceptual level
- Common ports (80, 443, 22, 21, 25, 53, 3306, 3389, etc.)
- Packet analysis with **Wireshark**

**Resources (Free):**
- **Professor Messer's CompTIA Network+ Course** — free on YouTube, one of the best free resources in existence
- **TryHackMe: Pre-Security** learning path — networking section
- **Practical Packet Analysis** by Chris Sanders (book)
- **Wireshark documentation** + practice with sample pcap files at CloudShark

**Milestone:** You can read a Wireshark capture, explain what happens when you type a URL in a browser end-to-end, and subnet a /24 network.

---

### 4.3 Windows Administration (Month 3–4)

Most enterprise environments run Windows. Active Directory is in almost every corporate network you will ever pentest.

**What to learn:**
- Windows filesystem structure and registry
- User and group management, NTFS permissions
- PowerShell basics — cmdlets, scripting, remoting
- Active Directory concepts (domains, forest, trust, GPO, OU)
- Windows services, scheduled tasks, event logs
- Windows Defender, UAC, and security architecture basics

**Resources (Free):**
- **TryHackMe: Windows Fundamentals** (3-part room series)
- **Microsoft Learn** — free Windows Server and Active Directory modules
- **TCM Security — Windows Privilege Escalation for Beginners** (YouTube, free)

---

### 4.4 Python for Security (Month 4–6)

You do not need to become a developer. You need to read, modify, and write scripts that automate reconnaissance, parsing, and exploitation.

**What to learn:**
- Variables, data types, control flow, functions
- File I/O — reading and writing files, JSON, CSV
- `requests` library — making HTTP requests programmatically
- `socket` library — basic networking scripts
- Regular expressions (`re` module)
- `subprocess` — running system commands from Python
- Basic script to automate tasks: port scanner, subdomain brute-forcer, log parser

**Resources (Free):**
- **Automate the Boring Stuff with Python** — free at automatetheboringstuff.com
- **Python for Everybody** (Coursera — free to audit)
- **TryHackMe: Python Basics** room
- **HackerRank Python track** — for practice problems

**Milestone:** You can write a 50-line Python script to scan a list of IPs, make HTTP requests, and save results to a file.

---

## 5. Phase 2 — Core Security Concepts (Months 7–10)

Now that you have foundations, start thinking like a security professional.

---

### 5.1 Security Frameworks & Concepts (Month 7)

**What to learn:**
- **CIA Triad** — Confidentiality, Integrity, Availability
- **OWASP Top 10** — the ten most critical web application security risks (memorize all ten)
- **MITRE ATT&CK Framework** — how adversaries operate (tactics, techniques, procedures)
- **NIST Cybersecurity Framework** — how defenders structure security programs
- **Threat modeling** basics — STRIDE, PASTA
- **Defense-in-depth** and the principle of least privilege
- Cryptography basics: symmetric/asymmetric, hashing, PKI, TLS handshake

**Resources:**
- **OWASP.org** — free, official documentation
- **MITRE ATT&CK Navigator** — free, interactive framework exploration
- **TryHackMe: Jr Penetration Tester** path (start this path now)

---

### 5.2 Network Security & Scanning (Month 7–8)

**Tools to master:**
- **Nmap** — the king of port scanning. Learn every major flag.
  - `-sV` (service version), `-sC` (default scripts), `-A` (aggressive), `-p-` (all ports), `-oN` (output to file)
- **Nessus Essentials** (free for personal use) — vulnerability scanner
- **Netcat** (`nc`) — the Swiss Army knife of networking
- **tcpdump** — CLI packet capture

**What to practice:**
- Network enumeration against your own home lab or TryHackMe machines
- Reading and interpreting Nmap output
- Identifying open services and known vulnerabilities from version numbers

---

### 5.3 Web Application Security (Month 8–10)

Web hacking is the single most accessible entry point into the field and has the richest bug bounty ecosystem.

**The OWASP Top 10 — Learn Each One Deeply:**

| Vulnerability | What It Is | Where to Practice |
|---|---|---|
| Injection (SQLi, Command Injection) | User input executed as code | PortSwigger, DVWA |
| Broken Authentication | Weak session management, credentials | TryHackMe |
| IDOR (Broken Access Control) | Accessing others' data by manipulating IDs | PortSwigger, HackTheBox |
| XSS (Cross-Site Scripting) | Injecting JavaScript into pages | PortSwigger Web Academy |
| Security Misconfiguration | Default credentials, exposed admin panels | TryHackMe |
| SSRF | Server-Side Request Forgery | PortSwigger |
| XXE | XML External Entity Injection | PortSwigger |
| Insecure Deserialization | Manipulating serialized objects | HackTheBox |
| CSRF | Cross-Site Request Forgery | PortSwigger |
| Sensitive Data Exposure | Unencrypted data, leaked secrets | Multiple |

**Primary Tool — Burp Suite Community:**
- Intercept and modify HTTP requests
- Repeater — resend and tweak requests
- Intruder — brute-force and fuzzing (rate-limited on free tier)
- Decoder — base64, URL encoding, etc.
- Learn Burp Suite inside out. It will be your companion for years.

**Resources (Free):**
- **PortSwigger Web Security Academy** — the best free web hacking course on the internet. 250+ labs. Do every single one.
- **DVWA (Damn Vulnerable Web Application)** — run locally for safe practice
- **HackTheBox: Starting Point** — free web-themed machines
- **TryHackMe: Web Fundamentals** path

**Milestone:** You can manually exploit SQLi, XSS, and IDOR on a practice lab without using automated tools.

---

### 5.4 Your First CTF Competitions (Month 9–10)

CTFs (Capture The Flag) are competitive hacking challenges. They are the gym where you train your skills. Each solved challenge and published writeup becomes portfolio gold.

**CTF Categories:**
- **Web** — web vulnerabilities, logic flaws
- **Pwn/Binary** — binary exploitation (Phase 4 territory)
- **Reversing** — reverse engineering (Phase 4 territory)
- **Crypto** — cryptographic challenges
- **Forensics** — disk images, network captures, steganography
- **OSINT** — open source intelligence gathering
- **Misc** — anything else

**Start Here:**
- **picoCTF** — picoctf.org — designed for beginners. Hundreds of archived challenges. Start here.
- **TryHackMe CTF rooms** — guided, with hints
- **CTFtime.org** — the aggregator for all live CTF events worldwide. Follow it.

---

## 6. Phase 3 — Ethical Hacking & Penetration Testing (Months 11–15)

This is where it gets serious. You are now building the skills companies pay for.

---

### 6.1 Penetration Testing Methodology

Professional pentesters follow a structured methodology. Never skip phases.

```
1. RECONNAISSANCE
   ├── Passive: OSINT, Shodan, Google Dorking, WHOIS, certificate transparency
   └── Active: Nmap, DNS enumeration, subdomain discovery

2. SCANNING & ENUMERATION
   ├── Port scanning (TCP/UDP)
   ├── Service and version detection
   ├── Vulnerability scanning (Nessus, OpenVAS)
   └── Directory/file discovery (Gobuster, Feroxbuster, ffuf)

3. EXPLOITATION
   ├── Exploit known CVEs (Metasploit, manual)
   ├── Web application attacks
   └── Password attacks (Hydra, Hashcat, John)

4. POST-EXPLOITATION
   ├── Privilege escalation (Linux PE, Windows PE)
   ├── Pivoting and lateral movement
   ├── Persistence mechanisms
   └── Data exfiltration simulation

5. REPORTING
   ├── Document every finding with reproducible steps
   ├── Rate severity (CVSS scoring)
   └── Recommend mitigations
```

---

### 6.2 Essential Pentesting Tools

**Reconnaissance:**
- `theHarvester` — email, domain, IP gathering
- `Maltego` — visual OSINT mapping
- `Shodan` — search engine for internet-connected devices
- `Subfinder`, `Amass` — subdomain enumeration
- `Google Dorks` — advanced search operators for finding exposed data

**Exploitation Frameworks:**
- **Metasploit Framework** — the most widely known exploit framework. Learn `msfconsole`, modules, payloads, sessions.
- **Searchsploit / Exploit-DB** — offline database of public exploits

**Web Hacking:**
- **Burp Suite** — already covered, now go deeper
- **SQLmap** — automated SQLi detection and exploitation (learn manual first, then automate)
- `ffuf`, `gobuster` — web fuzzing and directory brute-forcing

**Password Attacks:**
- `Hashcat` — GPU-accelerated password cracking. Learn the attack modes (-a 0, -a 3, -a 6).
- `John the Ripper` — CPU-based password cracker
- `Hydra` — network service brute-forcer (SSH, FTP, HTTP)
- `rockyou.txt` — the standard wordlist you will use constantly

**Post-Exploitation:**
- `LinPEAS` / `WinPEAS` — automated privilege escalation enumeration scripts
- `BloodHound` — Active Directory attack path visualization
- `Mimikatz` — Windows credential dumping (run on your lab only)
- `CrackMapExec` — Swiss Army knife for Active Directory environments

---

### 6.3 Active Directory Attacks (Month 12–13)

Active Directory is in virtually every enterprise. AD attacks are the backbone of modern penetration testing.

**Key Attack Techniques:**
- **AS-REP Roasting** — attacking accounts without Kerberos pre-auth
- **Kerberoasting** — extracting service tickets for offline cracking
- **Pass-the-Hash** — using NTLM hashes without cracking them
- **Pass-the-Ticket** — forging Kerberos tickets
- **Golden Ticket** / **Silver Ticket** — long-term persistence via forged tickets
- **DCSync** — dumping domain hashes by mimicking a Domain Controller
- **BloodHound Attack Paths** — finding shortest paths to Domain Admin

**Resources:**
- **TCM Security: Practical Ethical Hacking Course** — best bang-for-buck paid course (~$30). Covers AD deeply.
- **TryHackMe: Active Directory Basics + Attacking Kerberos** rooms
- **HackTheBox: Windows machines** — many AD-focused machines in the labs
- **Lab Setup:** Use VirtualBox or VMware with a Windows Server VM (evaluation license is free) and Windows 10 VMs to build your own AD lab. This is mandatory.

---

### 6.4 Bug Bounty Hunting (Month 13–15)

Bug bounties let you hack real systems legally and get paid for it. It is the freelance side of offensive security.

**Getting Started:**
- **HackerOne** (hackerone.com) — the largest bug bounty platform. Many programs have no age or degree requirements.
- **Bugcrowd** (bugcrowd.com) — second largest platform
- **Intigriti** — European-focused, excellent for web targets

**Beginner Strategy:**
- Start with programs that have broad scope (entire wildcard domains)
- Hunt IDOR, XSS, and information disclosure first — lowest bar to entry
- Read disclosed reports on HackerOne to understand what good findings look like
- Focus on less-trafficked assets (mobile APIs, older subdomains) for less competition
- **Hacker101** (hackerone.com/hacker101) — free web security classes and CTF challenges specifically designed to onboard bug bounty hunters

**Report Writing:**
A bug bounty report must include:
- Clear title
- Severity rating (Low/Medium/High/Critical with justification)
- Reproduction steps (numbered, exact)
- Proof of concept (screenshot or video)
- Impact statement
- Suggested fix

Even a Low-severity finding on a real live program goes on your resume. It is worth more than a certificate.

---

## 7. Phase 4 — Reverse Engineering & Binary Exploitation (Months 15–24+)

This is the deepest, most technically demanding path in cybersecurity. It requires patience measured in months, not weeks.

---

### 7.1 Prerequisites Before Starting RE

Before touching a disassembler, you must be solid on:
- **C programming** — most compiled binaries are written in C. You must read and understand C code.
- **Computer architecture** — CPU, registers, memory (stack, heap, BSS, text segment)
- **Linux internals** — how programs load, how the kernel manages processes
- **Assembly language** — x86 and x86_64 (Intel syntax)

**Resources:**
- **CS:APP (Computer Systems: A Programmer's Perspective)** — the definitive textbook. Free CMU course materials available online.
- **The C Programming Language** by Kernighan & Ritchie (K&R) — read this even if you do not plan to write much C
- **OpenSecurityTraining2 (ost2.fyi)** — free, university-quality courses on x86 architecture, assembly, OS internals. One of the best free resources for this phase.

---

### 7.2 Assembly Language (Month 15–17)

Assembly is the lingua franca of reverse engineering. You do not write it much — you read it constantly.

**x86_64 Essentials:**
- **Registers:** RAX, RBX, RCX, RDX (general), RSP (stack pointer), RBP (base pointer), RIP (instruction pointer), and the 32/16/8-bit aliases
- **Instructions:** `mov`, `push`, `pop`, `call`, `ret`, `jmp` + conditional jumps (`je`, `jne`, `jl`, `jg`), `cmp`, `test`, `add`, `sub`, `lea`, `xor`
- **Calling conventions:** how function arguments are passed and return values are handled (System V ABI for Linux, Microsoft x64 ABI for Windows)
- **Stack frames:** how `call` and `ret` manage the return address; how local variables live on the stack
- **Memory addressing modes:** `[rsp+8]`, `[rbp-0x10]`, etc.

**Resources (Free):**
- **OpenSecurityTraining2: Architecture 1001 and 1002** — the definitive free courses
- **Introduction to Reverse Engineering with Ghidra** — free course on Hackaday.io. Goes through x86_64 assembly from a RE perspective.
- **pwn.college** — free, browser-based, structured binary exploitation challenges from ASU. One of the best RE/exploitation learning platforms available.

---

### 7.3 Reverse Engineering Tools & Methodology (Month 17–20)

**Static Analysis (no execution):**
- **Ghidra** — free, open-source, developed by the NSA. Rivals commercial tools. Your primary tool.
  - Disassembler, decompiler, scripting engine, patch diffing, collaborative features
  - Requires Java 17+. Available at github.com/NationalSecurityAgency/ghidra
- **IDA Free** — the free version of the industry standard IDA Pro. Limited but useful.
- **Binary Ninja** — modern, great for scripting (paid, but Cloud version has free tier)
- **Radare2 / Cutter** — open source, steep learning curve, very powerful

**Dynamic Analysis (with execution — use in isolated VM only):**
- **GDB + pwndbg** or **GDB + peda** — the Linux debugger extended for exploit development
- **x64dbg** — the best free debugger for Windows binaries
- **Strace / Ltrace** — trace system calls and library calls
- **Frida** — dynamic instrumentation toolkit, great for mobile RE

**File Analysis:**
- `file` — identify file type
- `strings` — extract printable strings from binary
- `objdump` — display binary information (Linux)
- `readelf` — inspect ELF binary structures
- `binwalk` — extract embedded files from firmware

**The RE Workflow:**
```
1. Static Triage
   └── file, strings, objdump → understand what the binary does at a high level

2. Load into Ghidra
   └── Rename functions, add comments, recover data types
   └── Trace control flow, identify key logic

3. Dynamic Analysis
   └── Run in GDB, set breakpoints at interesting functions
   └── Observe memory state, argument values, return values

4. Iterate
   └── Each tool gives you different information
   └── Combine static understanding with runtime behavior
```

---

### 7.4 Binary Exploitation (Month 20–24+)

This is the pinnacle of offensive security knowledge. It underpins modern vulnerability research.

**Core Techniques (learn in this order):**

**Stack-Based Buffer Overflow**
- How the stack works and how return addresses get overwritten
- Finding the offset to the return address (pattern creation with `cyclic` or `msf-pattern_create`)
- Controlling `RIP`/`EIP`
- Bypassing basic protections

**Format String Vulnerabilities**
- How `printf(user_input)` leaks memory
- Reading and writing arbitrary memory via format specifiers

**Return-Oriented Programming (ROP)**
- Bypassing NX (non-executable stack) by chaining existing code "gadgets"
- Finding gadgets with `ROPgadget`, `ropper`
- Building ROP chains to call `system("/bin/sh")`

**Heap Exploitation**
- How `malloc` and `free` work internally (glibc allocator)
- Heap overflow, use-after-free, double-free
- Tcache poisoning (modern glibc technique)

**Modern Protections to Learn to Bypass:**
- **ASLR** — Address Space Layout Randomization → bypassed via information leaks
- **NX/DEP** — Non-Executable stack → bypassed via ROP
- **Stack Canaries** — stack corruption detection → bypassed via format string or brute force
- **PIE** — Position Independent Executable → bypassed via information leaks to find base address

**Resources (Free):**
- **pwn.college** (pwn.college) — the absolute best free platform for learning binary exploitation. Structured modules from ASU's security lab. Start here.
- **Nightmare** (guyinatuxedo.github.io) — comprehensive free RE/exploitation course with solved CTF challenges as teaching material
- **LiveOverflow** — YouTube channel with excellent binary exploitation series
- **pwntools** — the Python library for writing exploits. Learn it well.

**Resources (Books):**
- *Hacking: The Art of Exploitation* by Jon Erickson — teaches C and assembly alongside exploitation. The foundational text.
- *Practical Binary Analysis* by Dennis Andriesse — modern, Linux-focused, excellent

---

### 7.5 Malware Analysis (Month 20–24+)

A sub-specialty of RE focused on understanding malicious software.

**Two Pillars:**
- **Static Analysis** — analyzing the binary without running it (strings, imports, Ghidra decompilation)
- **Dynamic Analysis** — running the malware in a controlled environment and observing behavior

**Tools:**
- **Cuckoo Sandbox** — open-source automated malware analysis system
- **Any.run** — online interactive malware sandbox (free tier available)
- **VirusTotal** — upload samples for multi-engine scanning
- **Process Monitor (ProcMon)** — Windows tool to watch file/registry/network activity
- **Wireshark** — capture malware's network communications
- **FLOSS** — FireEye Labs Obfuscated String Solver — extracts obfuscated strings from malware

**Resources:**
- *Practical Malware Analysis* by Sikorski & Honig — the industry bible. Non-negotiable reading.
- **Malware Unicorn RE101** — free hands-on workshop. Google it. Free materials + Discord community.
- **MalwareBazaar** (bazaar.abuse.ch) — free database of malware samples for analysis practice

---

## 8. Certifications Roadmap

Certifications are door-openers, not skill-builders. Pair every cert with hands-on practice.

---

### 8.1 The Honest Ranking

| Cert | Level | Cost | Study Time | Value |
|---|---|---|---|---|
| **ISC2 CC** | Beginner | FREE | 4–6 weeks | High — no barrier, builds vocabulary |
| **eJPT** (INE) | Beginner | ~$200 | 1–2 months | High — community-recommended first pentest cert |
| **CompTIA Security+** | Entry-Mid | ~$400 | 1–3 months | High — HR checkbox, DoD jobs requirement |
| **CompTIA Network+** | Entry | ~$350 | 1–2 months | Medium — useful if networking is weak |
| **OSCP** (OffSec) | Intermediate | ~$1,649 | 3–6 months prep | Very High — gold standard for pentesters |
| **BSCP** (Burp Suite Certified Practitioner) | Intermediate | ~$99 | 2–3 months | High — excellent for web app roles |
| **PNPT** (TCM Security) | Intermediate | ~$400 | 2–4 months | High — practical, affordable OSCP alternative |
| **GREM** (GIAC RE Malware) | Advanced | ~$2,500+ | 4–6 months | High — specifically validates RE skills |
| **OSED** (OffSec Exploit Developer) | Advanced | ~$1,649 | 4–6 months | Very High — Windows exploitation deep dive |
| **CISSP** | Management | ~$750 | 6+ months | Very High — senior/management roles (needs experience) |

---

### 8.2 Recommended Certification Order

**If your goal is Penetration Testing:**
```
ISC2 CC (free) → eJPT → CompTIA Security+ → PNPT or OSCP
```

**If your goal is Reverse Engineering / Malware:**
```
ISC2 CC (free) → CompTIA Security+ → (Build RE skills via pwn.college/CTFs) → GREM → OSED
```

**If your goal is SOC / Blue Team:**
```
ISC2 CC (free) → CompTIA Security+ → CompTIA CySA+ → GCIA or BTL1
```

---

### 8.3 Key Notes

- **OSCP** has no formal prerequisites but strongly recommends Linux CLI proficiency, TCP/IP basics, and Python/Bash scripting. Budget 3–6 months of dedicated prep.
- **OSCP does not expire** — unlike most certs that require renewal every 3 years.
- **CEH** — widely recognized by name, but the cybersecurity community considers it theory-heavy. OSCP beats CEH at similar cost for offensive roles.
- **eJPT** is cheap, practical, and genuinely excellent for true beginners. Do not skip it if you are new.

---

## 9. Practice Platforms & Labs

### Free Platforms

| Platform | Best For | URL |
|---|---|---|
| **TryHackMe** | Structured beginner learning, guided rooms | tryhackme.com |
| **HackTheBox** | Intermediate+ CTF-style machines | hackthebox.com |
| **PortSwigger Web Academy** | Web hacking — the best free web course | portswigger.net/web-security |
| **pwn.college** | Binary exploitation and RE — structured | pwn.college |
| **picoCTF** | Beginner CTF challenges, all categories | picoctf.org |
| **OverTheWire** | Linux skills, beginner-to-advanced wargames | overthewire.org |
| **VulnHub** | Download vulnerable VMs for offline practice | vulnhub.com |
| **OWASP WebGoat** | Deliberately insecure web app for practice | owasp.org |
| **CTFtime** | Live CTF event calendar and archives | ctftime.org |
| **crackmes.one** | Reverse engineering crackme challenges | crackmes.one |
| **Malware Unicorn** | Free malware analysis workshops | malwareunicorn.org |
| **OpenSecurityTraining2** | Deep architecture and RE courses | ost2.fyi |
| **Hacker101** | Bug bounty-focused web challenges | hacker101.com |

### Paid Platforms Worth Considering

| Platform | Cost | Best For |
|---|---|---|
| **TCM Security** | ~$30/course | Ethical hacking, AD attacks, best value |
| **INE** | $50/mo or $200 (eJPT bundle) | eJPT prep, network security |
| **HackTheBox Pro Labs** | $20–50/mo | Enterprise-simulated network labs |
| **Offensive Security PEN-200** | $1,649 | OSCP exam + lab access |

### Your Home Lab

Build a local virtualized lab. It is free and teaches you infrastructure skills.

**Minimum Setup:**
- **Hypervisor:** VirtualBox (free) or VMware Workstation Player (free)
- **Attacker:** Kali Linux or Parrot OS VM
- **Targets:** Metasploitable 2/3, DVWA, VulnHub machines
- **AD Lab:** Windows Server 2019 evaluation (free 180-day license) + 1–2 Windows 10 VMs

**Recommended Specs for Host Machine:**
- 16 GB RAM minimum (8 GB workable but painful)
- SSD storage — spinning hard drives make VMs agonizingly slow
- VT-x/AMD-V virtualization enabled in BIOS

> Since you run an AMD Ryzen 7 7700 with KDE Plasma on openSUSE Tumbleweed, you are already in an excellent position. KVM/QEMU via `virt-manager` will give you better performance than VirtualBox on Linux. Your existing Linux workflow gives you a head start most Windows users lack.

---

## 10. Daily & Weekly Study Routine

Consistency is everything. Here is a practical, sustainable daily schedule calibrated for someone studying part-time alongside other commitments.

---

### The 3-Hour Daily Routine (Weekdays)

```
BLOCK 1 — THEORY (45 minutes)
├── Read documentation, book chapter, or course video
├── Take notes (use Obsidian, Logseq, or plain Markdown)
└── No hands-on yet — absorb the concept first

BREAK (10 minutes)
├── Walk, stretch, drink water
└── No screen

BLOCK 2 — HANDS-ON LAB (90 minutes)
├── Apply what you learned in a lab environment
├── TryHackMe room / HackTheBox machine / PortSwigger lab
├── Keep notes of every command, its output, and why you ran it
└── Do not copy-paste. Type every command manually.

BLOCK 3 — DOCUMENTATION (30 minutes)
├── Write a brief note on what you learned today
├── Update your notes repo (Obsidian, GitHub, etc.)
└── Flag questions you could not answer — research them next day
```

---

### Weekly Structure

| Day | Focus |
|---|---|
| **Monday** | Theory heavy — read chapter, watch course, absorb concepts |
| **Tuesday** | Hands-on lab applying Monday's theory |
| **Wednesday** | CTF challenge (1–2 challenges on picoCTF or THM) |
| **Thursday** | Tool deep-dive — master one tool or technique |
| **Friday** | Write a short writeup or notes summary of the week |
| **Saturday** | Longer lab session (3–4 hours), attempt a machine root |
| **Sunday** | Light review, plan next week, community engagement |

---

### Monthly Milestones to Hit

| Month | Milestone |
|---|---|
| 1 | Complete OverTheWire Bandit level 1–20 |
| 2 | Run a full Nmap scan and interpret output confidently |
| 3 | Pass ISC2 CC exam. Complete THM Pre-Security path. |
| 4 | Complete PortSwigger SQLi, XSS, and IDOR labs |
| 5 | Compromise your first TryHackMe CTF machine from scratch |
| 6 | Burp Suite fluency — intercept, modify, repeat, attack |
| 7 | Complete 10 HackTheBox machines (Easy tier) |
| 8 | Complete all picoCTF beginner challenges |
| 9 | Pass eJPT exam |
| 10 | Root your first HackTheBox Medium machine |
| 11 | Pass CompTIA Security+ |
| 12 | Build a complete home AD lab and practice Kerberoasting |
| 15 | Submit first bug bounty report on HackerOne |
| 18 | Begin OSCP / PNPT prep |
| 20 | First assembly/RE challenge on pwn.college |
| 24 | Pwn your first binary exploitation challenge on pwn.college |

---

### Study Habits That Actually Work

- **Active recall over passive review.** After reading a chapter, close the book and write down everything you remember. Then check.
- **The Feynman Technique.** Explain what you learned as if teaching a beginner. If you cannot, you do not understand it yet.
- **Spaced repetition.** Use Anki for memorizing things like port numbers, attack techniques, and command flags.
- **Short focused blocks beat marathon sessions.** 45–90 minute focused blocks with breaks retain more than 4-hour unbroken grinds.
- **Sleep is not optional.** Memory consolidation happens during sleep. 7–9 hours is not a luxury when learning something technically dense.
- **Join a study group.** Discord communities (TryHackMe Discord, HackTheBox Discord, TCM Security Discord) have beginners and experts. Ask questions. Explain answers.

---

## 11. Building Your Portfolio

Your portfolio is your degree substitute. Without it, no cert will carry you across the finish line.

---

### 11.1 The CTF Writeup Blog

Every machine you compromise, document. Every CTF challenge you solve, publish a writeup. This is the single highest-ROI activity for your career.

**A Good Writeup Contains:**
- Machine name, platform, difficulty
- Initial reconnaissance: what ports and services were discovered
- Enumeration: what interesting paths were found
- Exploitation: exactly how you got in (commands, payloads)
- Privilege escalation: how you got from user to root
- Key lessons learned

**Hosting Options (Free):**
- **GitHub Pages** + Jekyll or Hugo (static site, free hosting)
- **Medium** — simple, widely read in the security community
- **Notion** — clean, easy to set up
- **Substack** — if you want newsletter-style distribution

---

### 11.2 GitHub Repository

Your GitHub should be active and professional.

**What to put there:**
- Your CTF tools and scripts (even simple ones)
- Security-focused projects (port scanner, password auditor, log analyzer)
- Automation scripts for recon or enumeration
- Notes repositories (like your `butex-notes` model, but for security)
- Documented home lab setup guide

**What employers actually look for:**
- Consistent commit history (not everything on one day)
- README files on every repo
- Code that is readable and commented
- Evidence of original thinking, not just cloned tutorial code

---

### 11.3 Bug Bounty Hall of Fame

Even a single Low-severity finding acknowledged by a company on HackerOne or Bugcrowd is tangible evidence that you found and responsibly disclosed a vulnerability in a real production system. Include it on your resume.

---

### 11.4 A Personal Security Lab Documentation

Document your home lab. What VMs you run, how the network is configured, what attacks you have practiced. This demonstrates initiative and systems-level thinking.

---

## 12. Job Hunting Strategy (No Degree)

---

### 12.1 Entry-Level Job Titles to Target First

| Role | What You Do | Required Skills |
|---|---|---|
| **SOC Analyst Tier 1** | Monitor alerts, triage events, escalate | Security+ level knowledge, log analysis |
| **Junior Penetration Tester** | Assist on pentest engagements | Security+, eJPT, TryHackMe/HTB portfolio |
| **Bug Bounty Hunter** | Find and report vulnerabilities | Web hacking skills, no employer needed |
| **Security Analyst** | Vulnerability management, scanning | Security+, Nessus, basic scripting |
| **Malware Analyst** | Analyze suspicious files | RE fundamentals, sandbox tools |
| **Junior Security Engineer** | Build/configure security tooling | Scripting, cloud basics, security concepts |

---

### 12.2 Resume Strategy Without a Degree

**Lead with:**
- Certifications (top of resume)
- Relevant skills section
- Projects and portfolio

**Never:**
- Put your degree (or lack of one) at the top
- Write "No degree" or draw attention to it
- Apply only to job listings that explicitly require a degree (many do not actually enforce this)

**Resume Formula:**
```
[Name] — [email] — [GitHub] — [Blog/Portfolio]

CERTIFICATIONS
• CompTIA Security+ (SY0-701) — Month Year
• eJPT — Month Year

TECHNICAL SKILLS
• Penetration Testing: Nmap, Metasploit, Burp Suite, SQLmap
• Operating Systems: Kali Linux, Ubuntu, Windows Server
• Programming: Python, Bash
• Platforms: HackTheBox (Top X%), TryHackMe (Top X%)

PROJECTS
• Compromised 50+ HackTheBox machines (link to writeup blog)
• Reported IDOR vulnerability on [Company] via HackerOne (Hall of Fame)
• Built home Active Directory lab for practicing Kerberoasting and Pass-the-Hash

[Only then list any education you have]
```

---

### 12.3 Remote Work Strategy for Bangladesh

The global nature of cybersecurity makes remote work highly viable from South Asia. The key is positioning yourself for international or remote-international contracts.

**Where to Look:**
- **LinkedIn** — filter by "Remote" + "Cybersecurity"
- **Bugcrowd** / **HackerOne** — platform-based, fully remote, earn per finding
- **Upwork** — security testing, auditing, and consulting gigs
- **Pentest contracting** — once OSCP-level, small-to-medium companies globally hire remote pentesters
- **Synack Red Team** — invite-only elite bug bounty platform with higher payouts

**Key Insight:** A CISSP or OSCP-certified security analyst in Bangladesh on a remote-international contract earns roughly 3–5× the local market rate. The cert + portfolio + remote positioning combination is the highest leverage play available.

---

### 12.4 The Interview Process

**Common Interview Formats:**
- Technical screen (knowledge questions on networking, security concepts)
- Take-home CTF challenge
- Practical pentest of a test environment
- Behavioral interview

**Prepare For:**
- Walk me through the TCP three-way handshake
- Explain SQL injection and how to prevent it
- What happens when you type google.com in a browser?
- Describe a time you solved a difficult technical problem
- Explain OWASP Top 10 at a high level
- What is the difference between symmetric and asymmetric encryption?
- What is a buffer overflow?

---

## 13. Essential Books

### Absolute Must-Reads

| Book | Why Read It |
|---|---|
| *The Web Application Hacker's Handbook* — Stuttard & Pinto | The conceptual foundation for web security. Read before any web cert. |
| *Hacking: The Art of Exploitation* — Jon Erickson | Teaches C, assembly, and exploitation together. The foundational exploitation text. |
| *Practical Malware Analysis* — Sikorski & Honig | The industry bible for malware analysis. Non-negotiable if you want RE. |
| *The Linux Command Line* — William Shotts | Free. Excellent. Read in Phase 1. |

### Strong Recommendations

| Book | Why Read It |
|---|---|
| *Penetration Testing* — Georgia Weidman | Practical, beginner-friendly pentesting introduction |
| *Practical Binary Analysis* — Dennis Andriesse | Modern, Linux-focused binary analysis. More approachable than Erickson for RE. |
| *The Art of Exploitation* (2nd Ed) — Erickson | Same as above — worth re-listing because it is that good |
| *Computer Systems: A Programmer's Perspective* (CS:APP) | Deep computer architecture understanding. Heavy but worth every page. |
| *Cybersecurity and Cyberwar* — Singer & Friedman | Context and history — useful for interviews and understanding the field's landscape |

---

## 14. Communities & Networking

Cybersecurity has one of the most generous knowledge-sharing cultures in tech. Use it.

### Discord Servers
- **TryHackMe Discord** — active help channels, study groups
- **HackTheBox Discord** — community for HTB machines
- **TCM Security Discord** — attached to course purchases, very supportive
- **Nahamsec's Bounty Hunters** — bug bounty focused community
- **pwn.college Discord** — binary exploitation learners

### Twitter / X Accounts to Follow
- **@NahamSec** (Ben Sadeghipour) — bug bounty, streaming
- **@LiveOverflow** — binary exploitation education
- **@GossiTheDog** — threat intelligence, UK security
- **@MalwareTechBlog** — Marcus Hutchins, malware analysis
- **@thegrugq** — operational security and tradecraft

### YouTube Channels
- **LiveOverflow** — RE and binary exploitation explained brilliantly
- **IppSec** — HackTheBox machine walkthroughs (a goldmine for learning methodology)
- **TCM Security** — free pentesting content
- **John Hammond** — CTF solutions and malware analysis
- **David Bombal** — networking and ethical hacking

### Reddit
- **r/netsec** — news, research, professional discussion
- **r/HowToHack** — beginner questions
- **r/bugbounty** — bug hunting community
- **r/ReverseEngineering** — RE-focused

---

## 15. Tools Arsenal

A quick-reference list of every tool mentioned in this guide, organized by category.

### Reconnaissance
`nmap` • `masscan` • `theHarvester` • `Shodan` • `Subfinder` • `Amass` • `whois` • `dig` • `gobuster` • `ffuf` • `feroxbuster`

### Web Application
`Burp Suite` • `SQLmap` • `nikto` • `wfuzz` • `OWASP ZAP` • `Postman`

### Exploitation
`Metasploit Framework` • `Searchsploit` • `pwntools` • `msfvenom`

### Password Attacks
`Hashcat` • `John the Ripper` • `Hydra` • `Medusa` • `CrackStation`

### Post-Exploitation
`LinPEAS` • `WinPEAS` • `BloodHound` • `SharpHound` • `Mimikatz` • `CrackMapExec` • `Evil-WinRM`

### Reverse Engineering
`Ghidra` • `IDA Free` • `x64dbg` • `GDB + pwndbg` • `Binary Ninja` • `Radare2/Cutter` • `Frida` • `FLOSS` • `binwalk` • `strings` • `file` • `readelf` • `objdump` • `strace` • `ltrace`

### Malware Analysis
`Cuckoo Sandbox` • `Any.run` • `VirusTotal` • `Process Monitor` • `Wireshark` • `FakeNet-NG`

### Network Analysis
`Wireshark` • `tcpdump` • `Netcat` • `socat`

---

## 16. Common Mistakes to Avoid

**Skipping fundamentals to get to "the cool hacking stuff"**
There is no shortcut. A pentest is only as good as the enumeration behind it. Network and Linux fundamentals are the foundation everything else stands on.

**Collecting certifications without practical skills**
A cert on paper with zero labs behind it fools no one in a technical interview. Always pair certification study with real lab work on TryHackMe and HackTheBox.

**Passive learning only**
Watching YouTube videos about hacking is not the same as hacking. The ratio should be 30% watching/reading, 70% doing.

**Hacking without authorization**
One unauthorized scan of an IP you do not own can be a criminal offense in most jurisdictions. All practice goes inside authorized lab environments. No exceptions, no grey areas.

**Giving up after hitting a wall**
Every professional hacker has spent days stuck on a single machine. Struggling is the learning. When you are stuck: enumerate more, Google the service version + "exploit," read documentation, and as a last resort, look at a hint or writeup — but ensure you fully understand the solution before moving on.

**Ignoring the blue team perspective**
Even if your goal is red team / offensive, understanding how defenders detect attacks makes you a dramatically better attacker. Study SIEM tools, log analysis, and threat hunting.

**Not documenting as you go**
The writeup is not optional. The act of writing forces you to understand what you did. And the portfolio that accumulates becomes your most powerful job application asset.

---

## Appendix: Quick Reference — Phase Checklist

### ✅ Phase 1 Complete When:
- [ ] Completed OverTheWire Bandit levels 0–25
- [ ] Can write a Bash script to automate a simple task
- [ ] Can subnet a /24 network confidently
- [ ] Can capture and read a Wireshark trace
- [ ] Can write a Python script to make HTTP requests and parse responses
- [ ] Passed ISC2 CC exam

### ✅ Phase 2 Complete When:
- [ ] Completed PortSwigger Web Academy SQLi and XSS modules
- [ ] Can manually exploit IDOR and SQLi on DVWA without tools
- [ ] Fluent with Burp Suite interceptor, Repeater, and Decoder
- [ ] Completed TryHackMe Jr Penetration Tester path
- [ ] Solved first 10 picoCTF beginner challenges
- [ ] Passed eJPT

### ✅ Phase 3 Complete When:
- [ ] Rooted 20+ HackTheBox machines independently
- [ ] Built and attacked own Active Directory home lab
- [ ] Submitted at least one bug bounty report (any severity)
- [ ] Published at least 5 CTF/machine writeups
- [ ] Passed CompTIA Security+

### ✅ Phase 4 (RE) Underway When:
- [ ] Comfortable reading x86_64 assembly in Ghidra
- [ ] Completed at least 20 pwn.college challenges
- [ ] Solved a binary exploitation CTF challenge (buffer overflow)
- [ ] Completed Malware Unicorn RE101 workshop
- [ ] Analyzed at least 3 malware samples in a sandbox

---

*Last updated: June 2026 — This guide reflects the current state of the cybersecurity field, available certifications, and platform offerings as of this date. The field moves fast; always verify certification costs and platform features at the source.*
