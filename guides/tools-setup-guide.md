# 🛠 Tools Setup & Usage Guide

> Essential tools for web application penetration testing

---

## 📋 Tool Categories

1. [Proxy Tools](#proxy-tools) - Intercept and modify traffic
2. [Reconnaissance](#reconnaissance) - Gather information
3. [Vulnerability Scanners](#vulnerability-scanners) - Automated testing
4. [Exploitation](#exploitation) - Exploit vulnerabilities
5. [Custom Scripts](#custom-scripts) - Automation

---

## 🔧 Essential Setup

### Operating System

**Recommended**: Linux (Kali, Parrot, or Ubuntu)

**Install Kali Linux:**
```bash
# Download from: https://www.kali.org/get-kali/
# Or run in VM:
# VirtualBox: https://www.virtualbox.org/
# VMware: https://www.vmware.com/
```

**For Windows Users:**
```bash
# Install WSL2 (Windows Subsystem for Linux)
wsl --install -d kali-linux
```

---

## 🌐 Proxy Tools

### Burp Suite Community Edition ⭐ MOST IMPORTANT

**Installation:**
```bash
# Kali Linux (pre-installed)
burpsuite

# Ubuntu/Debian
sudo apt update
sudo apt install burpsuite

# Manual download
# https://portswigger.net/burp/communitydownload
```

**Initial Setup:**

1. **Configure Browser Proxy**
```
Settings → Network → Manual Proxy Configuration
HTTP Proxy: 127.0.0.1
Port: 8080
☑ Use this proxy for HTTPS
```

2. **Install CA Certificate**
```
1. Open browser with proxy on
2. Visit: http://burpsuite
3. Download CA Certificate
4. Browser Settings → Privacy & Security → Certificates
5. Import burpsuite certificate as trusted
```

**Essential Features:**

| Feature | Shortcut | Purpose |
|---------|----------|---------|
| Proxy | Ctrl+Shift+P | Intercept requests |
| Repeater | Ctrl+R | Replay requests |
| Intruder | Ctrl+I | Automated attacks |
| Decoder | Ctrl+Shift+D | Encode/decode |
| Comparer | Ctrl+Shift+C | Compare responses |

**Burp Suite Workflow:**
```
1. Intercept → Capture request
2. Forward to Repeater → Test manually
3. Forward to Intruder → Automate attack
4. Analyze → Document findings
```

**Pro Tips:**
```
- Use Target → Scope to filter traffic
- Enable "Intercept is off" by default
- Use Match/Replace for header manipulation
- Install extensions: Logger++, Turbo Intruder
```

---

### OWASP ZAP (Free Burp Alternative)

**Installation:**
```bash
# Kali Linux
sudo apt install zaproxy

# Manual download
# https://www.zaproxy.org/download/
```

**Quick Start:**
```bash
# Launch ZAP
zaproxy

# Automated scan
zap-cli quick-scan -s all http://target.com

# Spider + Active scan
zap-cli spider http://target.com
zap-cli active-scan http://target.com
```

**When to use ZAP vs Burp:**
- ZAP: Automated scanning, quick audits
- Burp: Manual testing, complex attacks

---

## 🔍 Reconnaissance Tools

### Nmap - Network Scanner

**Installation:**
```bash
sudo apt install nmap
```

**Basic Usage:**
```bash
# Quick scan
nmap target.com

# Full port scan
nmap -p- target.com

# Service version detection
nmap -sV target.com

# OS detection
nmap -O target.com

# Aggressive scan
nmap -A target.com

# Save results
nmap -oA scan_results target.com
```

**Web-specific scans:**
```bash
# HTTP methods
nmap -p 80,443 --script http-methods target.com

# Check for common vulnerabilities
nmap -p 80,443 --script http-vuln-* target.com

# SSL/TLS info
nmap -p 443 --script ssl-enum-ciphers target.com
```

---

### Sublist3r - Subdomain Enumeration

**Installation:**
```bash
git clone https://github.com/aboul3la/Sublist3r.git
cd Sublist3r
pip install -r requirements.txt
```

**Usage:**
```bash
# Basic subdomain enumeration
python sublist3r.py -d target.com

# With bruteforce
python sublist3r.py -d target.com -b

# Output to file
python sublist3r.py -d target.com -o subdomains.txt
```

---

### ffuf - Web Fuzzer

**Installation:**
```bash
# Go installation required
go install github.com/ffuf/ffuf@latest
```

**Usage:**
```bash
# Directory fuzzing
ffuf -u https://target.com/FUZZ -w wordlist.txt

# Parameter fuzzing
ffuf -u https://target.com/page?FUZZ=value -w params.txt

# POST data fuzzing
ffuf -u https://target.com/login -X POST \
     -d "username=admin&password=FUZZ" \
     -w passwords.txt

# Filter by status code
ffuf -u https://target.com/FUZZ -w wordlist.txt -fc 404

# Match by size
ffuf -u https://target.com/FUZZ -w wordlist.txt -fs 0
```

**Common Wordlists:**
```bash
# Directories
/usr/share/wordlists/dirb/common.txt
/usr/share/seclists/Discovery/Web-Content/common.txt

# Parameters
/usr/share/seclists/Discovery/Web-Content/burp-parameter-names.txt

# Subdomains
/usr/share/seclists/Discovery/DNS/subdomains-top1million-5000.txt
```

---

### Gobuster - Directory Brute Forcer

**Installation:**
```bash
sudo apt install gobuster
```

**Usage:**
```bash
# Directory bruteforce
gobuster dir -u https://target.com -w wordlist.txt

# Virtual host discovery
gobuster vhost -u https://target.com -w vhosts.txt

# DNS subdomain enumeration
gobuster dns -d target.com -w subdomains.txt

# With extensions
gobuster dir -u https://target.com -w wordlist.txt \
        -x php,html,js,txt
```

---

### WhatWeb - Technology Detection

**Installation:**
```bash
sudo apt install whatweb
```

**Usage:**
```bash
# Basic scan
whatweb target.com

# Aggressive mode
whatweb -a 3 target.com

# Output to JSON
whatweb target.com --log-json=output.json
```

---

## 💉 Exploitation Tools

### SQLMap - SQL Injection Tool

**Installation:**
```bash
# Kali (pre-installed)
sqlmap

# Manual
git clone https://github.com/sqlmapproject/sqlmap.git
```

**Usage:**

⚠️ **IMPORTANT**: Only use AFTER manual SQL injection

```bash
# Basic injection test
sqlmap -u "https://target.com/page?id=1"

# POST request
sqlmap -u "https://target.com/login" --data="user=admin&pass=test"

# From Burp request file
sqlmap -r request.txt

# Enumerate databases
sqlmap -u "URL" --dbs

# Enumerate tables
sqlmap -u "URL" -D database_name --tables

# Dump table
sqlmap -u "URL" -D db -T users --dump

# Get shell (dangerous!)
sqlmap -u "URL" --os-shell
```

**SQLMap Flags:**
```bash
--batch              # Never ask for user input
--threads=10         # Speed up scan
--level=5            # Aggression level (1-5)
--risk=3             # Risk level (1-3)
--tamper=space2comment  # Bypass WAF
--random-agent       # Random User-Agent
```

---

### XSStrike - XSS Detection

**Installation:**
```bash
git clone https://github.com/s0md3v/XSStrike.git
cd XSStrike
pip install -r requirements.txt
```

**Usage:**
```bash
# Basic XSS scan
python xsstrike.py -u "https://target.com/search?q=test"

# Crawl and scan
python xsstrike.py -u "https://target.com" --crawl
```

---

### Commix - Command Injection

**Installation:**
```bash
# Kali (pre-installed)
commix

# Manual
git clone https://github.com/commixproject/commix.git
```

**Usage:**
```bash
# Basic command injection test
commix -u "https://target.com/page?cmd=test"

# From file
commix -r request.txt
```

---

## 🐍 Python for Pentesting

### Essential Libraries

**Installation:**
```bash
# HTTP requests
pip install requests

# Beautiful Soup (HTML parsing)
pip install beautifulsoup4

# Selenium (browser automation)
pip install selenium

# JWT manipulation
pip install pyjwt
```

### Custom Exploit Template

```python
#!/usr/bin/env python3
import requests
from urllib.parse import urljoin

# Configuration
TARGET_URL = "https://target.com"
EXPLOIT_PARAM = "id"
PAYLOAD = "' OR 1=1--"

def exploit():
    """
    Exploit template for SQL injection
    """
    session = requests.Session()
    
    # Set custom headers
    headers = {
        "User-Agent": "Mozilla/5.0 (Custom)",
        "Content-Type": "application/x-www-form-urlencoded"
    }
    
    # Build exploit URL
    params = {EXPLOIT_PARAM: PAYLOAD}
    
    try:
        response = session.get(
            TARGET_URL,
            params=params,
            headers=headers,
            timeout=10
        )
        
        # Check for success indicators
        if "Welcome" in response.text:
            print(f"[+] Exploit successful!")
            print(f"[+] Payload: {PAYLOAD}")
            return True
        else:
            print("[-] Exploit failed")
            return False
            
    except requests.exceptions.RequestException as e:
        print(f"[!] Error: {e}")
        return False

if __name__ == "__main__":
    print("[*] Starting exploit...")
    exploit()
```

---

## 📱 Browser Extensions

### FoxyProxy

**Install**: [Firefox](https://addons.mozilla.org/en-US/firefox/addon/foxyproxy-standard/) | [Chrome](https://chrome.google.com/webstore/detail/foxyproxy/gcknhkkoolaabfmlnjonogaaifnjlfnp)

**Configuration:**
```
1. Add proxy
2. Title: Burp Suite
3. Proxy Type: HTTP
4. Proxy IP: 127.0.0.1
5. Port: 8080
6. Save
```

### Wappalyzer

**Install**: Browser extension store

**Usage**: Automatically detects technologies on websites

### Cookie-Editor

**Install**: Browser extension store

**Usage**: Quick cookie manipulation for session testing

---

## 🔨 Tool Installation Script

```bash
#!/bin/bash
# Web Pentesting Tools Setup Script

echo "[*] Updating system..."
sudo apt update && sudo apt upgrade -y

echo "[*] Installing essential tools..."
sudo apt install -y \
    burpsuite \
    nmap \
    gobuster \
    nikto \
    sqlmap \
    whatweb \
    zaproxy \
    git \
    curl \
    wget \
    python3 \
    python3-pip \
    golang-go

echo "[*] Installing Python libraries..."
pip3 install requests beautifulsoup4 selenium pyjwt

echo "[*] Installing ffuf..."
go install github.com/ffuf/ffuf@latest

echo "[*] Installing Sublist3r..."
git clone https://github.com/aboul3la/Sublist3r.git ~/tools/Sublist3r
pip3 install -r ~/tools/Sublist3r/requirements.txt

echo "[*] Downloading SecLists..."
git clone https://github.com/danielmiessler/SecLists.git ~/wordlists/SecLists

echo "[+] Installation complete!"
echo "[*] Tools installed in ~/tools/"
echo "[*] Wordlists in ~/wordlists/"
```

**Save and run:**
```bash
chmod +x setup_tools.sh
./setup_tools.sh
```

---

## 📚 Wordlists

### SecLists (Essential)

**Download:**
```bash
git clone https://github.com/danielmiessler/SecLists.git
cd SecLists
```

**Most Used Lists:**
```bash
# Directories
Discovery/Web-Content/directory-list-2.3-medium.txt
Discovery/Web-Content/common.txt

# Parameters
Discovery/Web-Content/burp-parameter-names.txt

# Usernames
Usernames/Names/names.txt

# Passwords
Passwords/Common-Credentials/10-million-password-list-top-1000.txt

# Subdomains
Discovery/DNS/subdomains-top1million-5000.txt

# Fuzzing
Fuzzing/SQL-Injection-Payloads.txt
Fuzzing/XSS-Attacks-master.txt
```

---

## 💻 Useful Commands Cheat Sheet

### Burp Suite
```bash
# Start Burp
burpsuite

# With custom memory
burpsuite --config-file=config.json -Xmx4g
```

### Quick Web Enumeration
```bash
# Full recon workflow
nmap -sV -p 80,443 target.com
whatweb target.com
sublist3r -d target.com -o subs.txt
ffuf -u https://target.com/FUZZ -w common.txt
nikto -h https://target.com
```

### Quick SQL Injection Test
```bash
# Manual test first, then:
sqlmap -u "URL" --batch --dbs
```

---

## 🎯 Tool Usage Priority

### Phase 0-1 (Beginner)
1. ✅ Burp Suite (Manual testing only)
2. ✅ Browser DevTools
3. ✅ curl / Python requests

### Phase 2 (Intermediate)
1. ✅ Burp Suite (All features)
2. ✅ Nmap (Service enumeration)
3. ✅ ffuf / Gobuster
4. ✅ Sublist3r / Amass

### Phase 3 (Advanced)
1. ✅ All tools above
2. ✅ SQLMap (after manual testing)
3. ✅ Custom Python scripts
4. ✅ Metasploit (specific modules)

---

## ⚠️ Important Reminders

1. **Manual First, Tools Later**: Understand before automating
2. **Understand Output**: Don't blindly trust tool results
3. **Rate Limiting**: Don't DOS target servers
4. **Authorization**: Only test systems you have permission for
5. **Update Regularly**: Keep tools and wordlists current

```bash
# Update tools
sudo apt update && sudo apt upgrade
go install github.com/ffuf/ffuf@latest
git -C ~/tools/SecLists pull
```

---

[← Back to Main Guide](../README.md)