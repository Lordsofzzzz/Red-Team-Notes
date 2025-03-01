# Reconnaissance 

## 📌 Introduction
Reconnaissance (Recon) is the first phase of an attack where information about the target is gathered. It is crucial for identifying potential attack vectors.

## 🛠 Types of Reconnaissance
- **🔹 Passive Recon**: Gathering information without directly interacting with the target.
- **🔹 Active Recon**: Engaging with the target to extract data.

---

## 🔍 Passive Reconnaissance
**🎯 Goal:** Collect information without alerting the target.

### 🛠 Techniques:
- **🕵️‍♂️ OSINT (Open-Source Intelligence):**
  - 🔍 Google Dorking: `site:target.com filetype:pdf`
  - 🌐 WHOIS lookup: `whois target.com`
  - 📢 Social Media profiling (LinkedIn, Twitter, etc.)
  - 🖼 Reverse Image Search (Google, TinEye)
  - 🔎 Shodan: `shodan search target.com`
  - 🔥 Censys: `censys search target.com`
  - 📄 FOCA: Metadata analysis for documents
  - 🕸 Maltego: Graph-based OSINT tool
  - 📚 GHDB (Google Hacking Database) for advanced search queries
  - 🔗 OSINT Framework: `https://osintframework.com/`
  - 🔐 Check Breached Data: `Have I Been Pwned (HIBP)` API
  - 📧 Email harvesting: `hunter.io`, `theHarvester`
- **🌍 Subdomain Enumeration:**
  - 🏷 `crt.sh`: `https://crt.sh/?q=target.com`
  - 🖥 `Sublist3r`: `python sublist3r.py -d target.com`
  - 🛠 `Amass`: `amass enum -d target.com`
- **🖼 Metadata Extraction:**
  - 🏷 `exiftool` for image metadata
  - 📜 `strings` command for document analysis
  - 🔎 `FOCA` for bulk metadata extraction

---

## 🚀 Active Reconnaissance
**🎯 Goal:** Probe the target to gather technical data.

### 🛠 Techniques:
- **🖥 Port Scanning:**
  - 🎯 `nmap -sV -A target.com`
  - 🚀 `masscan -p1-65535 --rate=10000 target.com`
  - ⚡ `rustscan -a target.com`
- **🌐 DNS Enumeration:**
  - 🖥 `dig axfr @ns1.target.com`
  - 🛠 `dnsrecon -d target.com`
  - 🔍 `fierce -dns target.com`
  - 🏷 `knockpy target.com`
  - 📡 `dnscan -d target.com`
  - 🔍 `nslookup -type=any target.com`
  - 🖥 `host -a target.com`
  - 🔎 `recon-ng` (DNS modules)
  - 🛠 `enumall.sh target.com` (Combines multiple DNS enumeration tools)
- **📡 Network Mapping:**
  - 🌍 `traceroute target.com`
  - 🔎 `netdiscover -r 192.168.1.0/24`
  - 🛠 `arp-scan -l`
  - 📡 `hping3 -S target.com -p 80`
  - 🔍 `mtr target.com`
  - 🏷 `ip route show`
  - 🚀 `nmap --traceroute target.com`
  - 🖥 `pathping target.com` (Windows)
  - 🛠 `ss -tuln` (List open ports on Linux)
  - 📜 `netstat -an` (Windows alternative for ss)
- **🌐 Web Reconnaissance:**
  - 🔎 `whatweb target.com`
  - 📂 `gobuster dir -u target.com -w wordlist.txt`
  - 🏛 `waybackurls target.com`
  - 📡 `dirsearch -u target.com`
  - 🛠 `wfuzz -c -z file,wordlist.txt --hc 404 target.com/FUZZ`
  - 🔍 `nikto -h target.com`
  - 🏷 `wappalyzer -target.com`
  - 🚀 `arjun -u target.com -m GET`
  - 📂 `ffuf -u http://target.com/FUZZ -w wordlist.txt`
- **📧 Email & Credential Harvesting:**
  - 🕵️‍♂️ `holehe target_email`
  - 📡 `hunter.io`
  - 🔐 `Have I Been Pwned (HIBP)` API

---

## 🔧 Recon Tools
| 🏷 Category       | 🛠 Tool            | ⚡ Command Example |
|----------------|----------------|-----------------|
| OSINT         | theHarvester    | `theHarvester -d target.com -b google` |
| OSINT         | Shodan          | `shodan search target.com` |
| OSINT         | Censys          | `censys search target.com` |
| OSINT         | Maltego         | Graph-based OSINT tool |
| OSINT         | FOCA            | Metadata extraction |
| OSINT         | OSINT Framework | `https://osintframework.com/` |
| Subdomains    | Sublist3r       | `sublist3r -d target.com` |
| Subdomains    | Amass           | `amass enum -d target.com` |
| Port Scanning | Nmap            | `nmap -sC -sV -A target.com` |
| Port Scanning | RustScan        | `rustscan -a target.com` |
| Network Scan  | Netdiscover     | `netdiscover -r 192.168.1.0/24` |
| DNS Enum      | DNSRecon        | `dnsrecon -d target.com` |
| Web Recon     | WhatWeb         | `whatweb target.com` |
| Web Recon     | Gobuster        | `gobuster dir -u target.com -w wordlist.txt` |
| Web Recon     | Nikto           | `nikto -h target.com` |
| Email Recon   | Holehe          | `holehe target_email` |
| Email Recon   | Hunter.io       | Web-based search |

---

## 🎯 Final Thoughts
Reconnaissance is a critical step in ethical hacking and penetration testing. Using both passive and active recon techniques effectively helps in crafting a better attack strategy while remaining undetected. Keeping up with the latest tools and methodologies enhances effectiveness in information gathering. 🛡

