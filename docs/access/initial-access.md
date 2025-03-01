# Initial Access Notes

## 📌 Introduction
Initial access is the phase where an attacker gains a foothold in the target system or network. It involves exploiting vulnerabilities, using stolen credentials, or leveraging social engineering tactics.

## 🛠 Techniques for Initial Access

### 🔹 Phishing Attacks
- **Spear Phishing (Email-based)**: Sending targeted emails with malicious attachments or links.
  - Tools: `GoPhish`, `Evilginx2`, `Modlishka`
  - Payloads: Malicious macros, HTA files, embedded links
  - Common Techniques:
    - Spoofed emails with fake sender addresses
    - Credential harvesting using fake login pages
    - Malicious attachments exploiting Office macros
    - Embedded links leading to malware-hosting sites
- **Spear Phishing (SMS & Voice Phishing - Smishing & Vishing)**: Using SMS or phone calls to trick users into revealing credentials.
  - Tools: `Modlishka`, `EvilURL`, `Seeker`
  - Techniques:
    - Fake customer support calls impersonating banks or IT teams
    - Sending SMS with malicious links to fake login portals
    - Caller ID spoofing to appear legitimate
- **Clone Phishing**: Resending a previously sent legitimate email but replacing links or attachments with malicious ones.
- **Phishing through Social Media**:
  - Impersonating trusted sources on LinkedIn, Twitter, or Facebook
  - Using fake job offers with malicious attachments
  - Sending direct messages with phishing links
- **Compromised Accounts for Internal Phishing**:
  - Using previously breached email accounts to send phishing emails within an organization
- **HTML Smuggling**:
  - Embedding malicious scripts inside HTML attachments to bypass email security filters
  - `Example:` `<a download='malware.html' href='data:text/html;base64,...'>Click Here</a>`

### 🔹 Exploiting Public-Facing Applications
- Targeting vulnerable web applications, APIs, or services.
  - Tools: `Metasploit`, `SQLmap`, `Burp Suite`, `Fuff`, `Dirb`, `Dirbuster`, `Nikto`, `Wfuzz`
  - Exploits:
    - **SQL Injection (SQLi)**: Extracting data by injecting malicious SQL queries.
      - Command: `sqlmap -u 'http://target.com?id=1' --dbs`
    - **Remote Code Execution (RCE)**: Exploiting vulnerable applications to execute commands.
      - Command: `msfconsole -x 'use exploit/multi/http/struts2_code_exec'`
    - **Command Injection**: Running unauthorized commands on a system.
      - Example Payload: `; cat /etc/passwd`
    - **Path Traversal**: Accessing restricted files by manipulating file paths.
      - Example Payload: `../../../../etc/passwd`
    - **Cross-Site Scripting (XSS)**: Injecting malicious JavaScript to steal cookies or hijack sessions.
      - Example: `<script>alert('XSS')</script>`

### 🔹 Physical & Insider Threats
- **USB Drops & HID Attacks**: Using malicious USB devices to execute unauthorized scripts.
  - Tools: `Rubber Ducky`, `Bash Bunny`, `OMG Cable`
- **Rogue Wi-Fi Access Points**: Setting up fake Wi-Fi networks to steal credentials.
  - Tools: `WiFi Pineapple`, `Airgeddon`, `Bettercap`
- **Badge Cloning & RFID Attacks**: Cloning RFID access cards to gain unauthorized entry.
  - Tools: `Proxmark3`, `Flipper Zero`, `ChameleonMini`
- **Social Engineering (On-Site Attacks)**: Impersonation, tailgating, and convincing employees to reveal sensitive information.
- **Hidden Cameras & Keyloggers**: Placing hidden cameras or installing hardware keyloggers to capture keystrokes.
  - Tools: `KeyGrabber`, `Spy Cameras`, `WiFi Keyloggers`

### 🔹 Command Reference Table
| Technique | Command |
|-----------|---------|
| **SQL Injection** | `sqlmap -u 'http://target.com?id=1' --dbs` |
| **Remote Code Execution (RCE)** | `msfconsole -x 'use exploit/multi/http/struts2_code_exec'` |
| **Command Injection** | `; cat /etc/passwd` |
| **Path Traversal** | `../../../../etc/passwd` |
| **Brute Forcing FTP** | `hydra -L users.txt -P passwords.txt ftp://target.com` |
| **Brute Forcing SMB** | `crackmapexec smb target.com -u userlist.txt -p passlist.txt` |
| **Enumerating SMB Shares** | `smbmap -H target.com -u user -p pass` |
| **Enumerating Linux RPC Services** | `rpcclient -U "" target.com` |
| **Intercepting Traffic (MITM)** | `ettercap -T -M arp:remote /target_ip/ /gateway_ip/` |
| **Evil Twin Attack (Wi-Fi Hijacking)** | `airgeddon` |

## 🎯 Final Thoughts
Initial access is the first major step in an attack chain. Using a combination of social engineering, exploitation, and misconfiguration abuse, attackers can gain a foothold. Defensive measures like MFA, patching, network segmentation, and user awareness training are crucial to mitigate these threats. 🛡

