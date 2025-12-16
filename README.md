# 🎯 Web Hacking Learning Guide

> A comprehensive, structured roadmap to master web application penetration testing from zero to professional level.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

## 📋 Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Learning Phases](#learning-phases)
- [Resources](#resources)
- [Practice Platforms](#practice-platforms)
- [Tools](#tools)
- [Certifications](#certifications)
- [Bug Bounty](#bug-bounty)
- [Community](#community)
- [Contributing](#contributing)

---

<a id="introduction"></a>
## 🌟 Introduction

This repository provides a **realistic, structured learning path** for web application penetration testing. Unlike scattered tutorials or overwhelming resources, this guide follows industry-standard methodologies and focuses on practical skills that employers and bug bounty programs value.

### What You'll Learn

- Web application fundamentals (HTTP, APIs, authentication)
- Common vulnerabilities (OWASP Top 10 and beyond)
- Manual exploitation techniques
- Security testing tools (Burp Suite, OWASP ZAP)
- Real-world attack methodologies
- Professional reporting and documentation

### Who This Is For

- **Beginners**: No prior hacking experience required
- **Developers**: Looking to understand security from an attacker's perspective
- **IT Professionals**: Transitioning into cybersecurity
- **Students**: Building practical security skills
- **Bug Bounty Hunters**: Starting their journey

---
<a id="prerequisites"></a>
## 📚 Prerequisites

### Required Knowledge

Before starting, you should have:

1. **Basic Linux Skills**
   - Command line navigation
   - File permissions
   - Basic networking commands
   - Package management

2. **Networking Fundamentals**
   - TCP/IP basics
   - DNS, HTTP/HTTPS protocols
   - Understanding of ports and services

3. **Programming Basics** (at least one language)
   - Python (recommended)
   - JavaScript
   - Bash scripting

### Recommended Setup

- **Operating System**: Linux (Kali Linux, Ubuntu, or ParrotOS)
- **RAM**: Minimum 8GB (16GB recommended)
- **Tools**: Burp Suite Community Edition, Firefox, Terminal
- **Virtual Machines**: VirtualBox or VMware (for lab environments)

---
<a id="learning-phases"></a>
## 🎓 Learning Phases

This guide is divided into **four progressive phases**, each building on the previous one. Complete each phase before moving to the next.

### [Phase 0: Foundation (2-3 weeks)](docs/phase-0-foundation.md)

**Goal**: Understand how the web works

- HTTP/HTTPS protocol deep dive
- Request/response anatomy
- Cookies, sessions, and authentication
- Same-Origin Policy (SOP) and CORS
- Web application architecture
- RESTful APIs and JSON

**Resources**: 
- [PortSwigger Web Security Academy - HTTP Basics](https://portswigger.net/web-security/getting-started)
- [MDN Web Docs - HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

---

### [Phase 1: Core Vulnerabilities (8-12 weeks)](docs/phase-1-core-vulnerabilities.md)

**Goal**: Master OWASP Top 10 vulnerabilities

#### Week 1-2: SQL Injection
- Understanding database queries
- Error-based, Union-based, Blind SQLi
- Exploiting different database systems
- SQLMap basics (after manual exploitation)

#### Week 3-4: Cross-Site Scripting (XSS)
- Reflected, Stored, and DOM-based XSS
- Context-aware payloads
- XSS filter bypasses
- Content Security Policy (CSP)

#### Week 5: Authentication & Access Control
- Broken authentication mechanisms
- Session management flaws
- IDOR (Insecure Direct Object References)
- Horizontal and vertical privilege escalation

#### Week 6: Server-Side Vulnerabilities
- File upload vulnerabilities
- Command injection
- Path traversal
- Server-Side Request Forgery (SSRF)

#### Week 7: Logic Flaws & Business Logic
- Understanding application logic
- Race conditions
- Payment manipulation
- Workflow bypasses

#### Week 8+: Advanced Topics
- XXE (XML External Entities)
- Deserialization attacks
- CSRF (Cross-Site Request Forgery)
- JWT vulnerabilities

**Primary Resource**: [PortSwigger Web Security Academy](https://portswigger.net/web-security/all-topics) (FREE)

---

### [Phase 2: Tools & Automation (4-6 weeks)](docs/phase-2-tools-automation.md)

**Goal**: Master professional security tools

#### Burp Suite Mastery
- Proxy and intercepting requests
- Repeater for manual testing
- Intruder for automated attacks
- Extensions (Logger++, Turbo Intruder)

#### Reconnaissance & Discovery
- Subdomain enumeration
- Directory brute-forcing (ffuf, gobuster)
- Technology fingerprinting
- Google Dorking

#### Automation with Python
- Writing custom exploits
- HTTP requests library
- Parsing responses
- Automated vulnerability scanners

**Practice**: Build your own vulnerability scanner

---

### [Phase 3: Real-World Application (8-12 weeks)](docs/phase-3-real-world.md)

**Goal**: Apply skills in realistic scenarios

#### Penetration Testing Methodology
1. Reconnaissance
2. Enumeration & Discovery
3. Vulnerability Identification
4. Exploitation
5. Post-Exploitation
6. Reporting

#### Lab Platforms
- **HackTheBox**: Realistic machines and challenges
- **TryHackMe**: Guided paths and rooms
- **PentesterLab**: Web-focused exercises
- **VulnHub**: Downloadable vulnerable VMs

#### Capture The Flag (CTF)
- CTFtime.org for competitions
- PicoCTF, OverTheWire
- Practice time-bound challenges

---

### [Phase 4: Specialization & Career (Ongoing)](docs/phase-4-specialization.md)

**Goal**: Develop expertise and professional profile

#### Choose Your Path
- **Bug Bounty Hunting**: Finding vulnerabilities in real applications
- **Penetration Testing**: Professional security assessments
- **Application Security**: Secure code review and development
- **Security Research**: Discovering new vulnerability types

#### Build Your Portfolio
- Public write-ups (with permission)
- GitHub repositories
- Blog posts and tutorials
- Conference talks

---

<a id="resources"></a>
## 📖 Resources

### Free Learning Platforms

| Platform | Focus | Level | Cost |
|----------|-------|-------|------|
| [PortSwigger Web Security Academy](https://portswigger.net/web-security) | Web vulnerabilities | Beginner-Advanced | FREE |
| [TryHackMe](https://tryhackme.com) | Guided learning paths | Beginner-Intermediate | Free/Paid |
| [HackTheBox Academy](https://academy.hackthebox.com) | Structured courses | All levels | Free/Paid |
| [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/) | Testing methodology | Intermediate | FREE |

### Books

- **The Web Application Hacker's Handbook** (2nd Edition) - Dafydd Stuttard & Marcus Pinto
- **Real-World Bug Hunting** - Peter Yaworski
- **Bug Bounty Bootcamp** - Vickie Li
- **Web Security Testing Cookbook** - Paco Hope & Ben Walther

### YouTube Channels

- [STÖK](https://www.youtube.com/@STOKfredrik) - Bug bounty tips
- [LiveOverflow](https://www.youtube.com/@LiveOverflow) - Technical deep dives
- [IppSec](https://www.youtube.com/@ippsec) - HackTheBox walkthroughs
- [PwnFunction](https://www.youtube.com/@PwnFunction) - Vulnerability explanations
- [John Hammond](https://www.youtube.com/@_JohnHammond) - CTF and security

### Blogs & Writeups

- [PortSwigger Research](https://portswigger.net/research)
- [Pentest-Tools Blog](https://pentest-tools.com/blog)
- [HackerOne Hacktivity](https://hackerone.com/hacktivity)
- [Bugcrowd Crowdstream](https://bugcrowd.com/crowdstream)

---

<a id="practice-platforms"></a>
## 🎮 Practice Platforms

### Vulnerable Web Applications (Local Practice)

| Name | Description | Focus |
|------|-------------|-------|
| [DVWA](https://github.com/digininja/DVWA) | Damn Vulnerable Web App | OWASP Top 10 |
| [bWAPP](http://www.itsecgames.com/) | Buggy Web Application | 100+ vulnerabilities |
| [OWASP Juice Shop](https://owasp.org/www-project-juice-shop/) | Modern web app | API, XSS, SQLi |
| [WebGoat](https://owasp.org/www-project-webgoat/) | Guided lessons | Interactive tutorials |
| [HackThisSite](https://www.hackthissite.org/) | Basic challenges | Beginner-friendly |

### Online CTF Platforms

- **[CTFtime](https://ctftime.org/)** - CTF calendar and ratings
- **[PicoCTF](https://picoctf.org/)** - Educational CTF
- **[Root-Me](https://www.root-me.org/)** - 400+ challenges
- **[pwn.college](https://pwn.college/)** - University-level courses

---
<a id="tools"></a>
## 🛠 Tools

### Essential Tools (Install First)

```bash
# Burp Suite Community Edition
sudo apt install burpsuite

# Network scanning
sudo apt install nmap

# Directory bruteforcing
go install github.com/ffuf/ffuf@latest

# SQL injection
sudo apt install sqlmap

# Web proxy
sudo apt install zaproxy
```

### Recommended Browser Extensions

- **FoxyProxy** - Proxy management
- **Wappalyzer** - Technology detection
- **Cookie-Editor** - Session manipulation
- **Hack-Tools** - Quick reference

### Scripting & Automation

- **Python** - requests, beautifulsoup4, selenium
- **Bash** - for automation scripts
- **Go** - for tool development

See [Tools Documentation](docs/tools.md) for detailed setup and usage.

---

## 🎖 Certifications

### Beginner to Intermediate

| Certification | Provider | Focus | Cost |
|---------------|----------|-------|------|
| **BSCP** | PortSwigger | Burp Suite skills | ~$99 |
| **eJPT** | INE | Junior pentester | ~$249 |
| **PWPA** | TCM Security | Web pentesting | ~$299 |
| **PNPT** | TCM Security | Practical pentesting | ~$399 |

### Advanced

- **OSCP** (Offensive Security) - Industry standard, challenging
- **OSWE** (Offensive Security) - Advanced web exploitation
- **eWPT/eWPTX** (INE) - Web pentesting focused
- **GWAPT** (GIAC) - Web application testing

See [Certifications Guide](docs/certifications.md) for preparation tips.

---

<a id="bug-bounty"></a>
## 💰 Bug Bounty

### Getting Started

Bug bounty programs allow ethical hackers to find and report security vulnerabilities in exchange for monetary rewards. Major platforms include HackerOne, Bugcrowd, and Intigriti, which connect security researchers with organizations seeking to improve their security posture.

### Major Platforms

1. **[HackerOne](https://www.hackerone.com/)** - Largest community, 1.5M+ hackers
2. **[Bugcrowd](https://www.bugcrowd.com/)** - Structured learning with Bugcrowd University
3. **[Intigriti](https://www.intigriti.com/)** - European leader, great community
4. **[YesWeHack](https://www.yeswehack.com/)** - Ranking system, training programs
5. **[Synack](https://www.synack.com/)** - Invite-only, vetted researchers
6. **[Open Bug Bounty](https://www.openbugbounty.org/)** - Free, non-profit, great for beginners

### Before You Start Bug Bounty

⚠️ **You should NOT start bug bounties until:**

- You can manually exploit OWASP Top 10 without tools
- You understand web application architecture deeply
- You can explain WHY vulnerabilities work, not just HOW
- You've completed at least 50+ labs on PortSwigger/HTB

### Tips for Success

1. **Read the Program Scope Carefully** - Respect boundaries
2. **Focus on Quality Over Quantity** - One critical > ten lows
3. **Learn to Write Professional Reports** - Clear POC and impact
4. **Start with Small Programs** - Less competition
5. **Specialize** - Master one vulnerability class deeply
6. **Stay Legal and Ethical** - Always

See [Bug Bounty Guide](docs/bug-bounty.md) for detailed strategies.

---

<a id="community"></a>
## 🤝 Community

### Forums & Discord

- **[PortSwigger Forum](https://forum.portswigger.net/)**
- **[HackTheBox Forums](https://forum.hackthebox.com/)**
- **Reddit**: r/netsec, r/bugbounty, r/AskNetsec
- **Discord**: Bug Bounty World, The Cyber Mentor, HackTheBox

### Twitter/X Security Community

Follow: @stokfredrik, @BBAC_Community, @Bugcrowd, @HackerOne, @PortSwigger, @NahamSec

### Conferences

- **DEF CON** - Largest hacker conference
- **Black Hat** - Professional security conference
- **OWASP AppSec** - Application security focused
- **BSides** - Community-driven events (worldwide)

---

## 📝 Study Tips

### The 90-Minute Rule

```
25 min: Learn concept
5 min: Break
25 min: Do lab
5 min: Break
25 min: Take notes/write-up
STOP - Even if motivated
```

### Daily Consistency Beats Intensity

- **30-90 minutes daily** > 10 hours once a week
- Focus on ONE vulnerability per day
- Every session must produce output (notes, exploit, write-up)

### When You Get Stuck

1. Read error messages carefully
2. Check the hint (if available)
3. Google the specific error
4. Ask in forums (show what you tried)
5. Take a break and return later
6. Move on and come back with fresh perspective

---

## 🗺 30-Day Quickstart Plan

**Can't follow a long roadmap? Start here:**

### Week 1: HTTP & Basics
- Days 1-3: HTTP protocol, cookies, sessions
- Days 4-7: Burp Suite basics, PortSwigger HTTP labs

### Week 2: SQL Injection
- Days 8-14: SQL Injection theory → labs → manual exploitation

### Week 3: XSS & Authentication
- Days 15-18: XSS (reflected, stored, DOM)
- Days 19-21: Authentication & access control flaws

### Week 4: Real Application
- Days 22-28: Complete 3-5 beginner CTF challenges
- Days 29-30: Review and document everything learned

See [30-Day Plan](docs/30-day-plan.md) for daily breakdown.

---

## 📊 Progress Tracking

Track your learning journey:

- [ ] Completed Phase 0 (Foundation)
- [ ] Solved 50+ PortSwigger labs
- [ ] Exploited all OWASP Top 10 manually
- [ ] Mastered Burp Suite core features
- [ ] Completed 10+ CTF challenges
- [ ] First bug bounty submission
- [ ] First valid bug bounty
- [ ] Earned certification
- [ ] Wrote 5+ public write-ups

---

<a id="contributing"></a>
## 🤝 Contributing

Contributions are welcome! Please read our [Contributing Guidelines](CONTRIBUTING.md).

Ways to contribute:
- Fix typos or improve documentation
- Add new resources or tools
- Share learning tips
- Create example write-ups
- Translate content

---

## ⚖️ Legal Disclaimer

**IMPORTANT**: Always practice ethical hacking.

✅ **Legal**:
- Authorized practice platforms
- Your own systems
- Bug bounty programs (within scope)
- CTF competitions

❌ **Illegal**:
- Testing systems without permission
- Accessing data you shouldn't
- Causing damage or disruption
- Violating terms of service

**Unauthorized access to computer systems is illegal in most countries.** This guide is for educational purposes only. The authors are not responsible for misuse.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🌟 Star This Repo

If you find this guide helpful, please star ⭐ this repository and share it with others!

---

**Made with ❤️ by the security community**

*Last updated: December 2025*
