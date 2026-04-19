# 🎯 Attack Vectors - How Attacks Happen

The various ways attackers can compromise systems.

## 📊 Common Attack Vectors

```
┌─────────────────────────────────────────────────────────────────┐
│               ATTACK SURFACE                                  │
├─────────────────────────────────────────────────────────────────┤
│                                                         │
│    ┌───────┐  ┌───────┐  ┌───────┐  ┌───────┐          │
│    │ Email │  │  Web  │  │Network│  │Physical│          │
│    └──┬───┘  └──┬───┘  └──┬───┘  └──┬───┘          │
│       │         │         │         │                    │
│       └─────────┴─────────┴─────────┘                    │
│                    │                                    │
│              ┌────▼────┐                              │
│              │Malware │                              │
│              │ Exploits│                              │
│              │   +    │                              │
│              │Social  │                              │
│              │Engineering                           │
│              └─────────┘                              │
└─────────────────────────────────────────────────────────────────┘
```

## 🌐 Network Attack Vectors

### 1. Port Scanning

```bash
# TCP Connect Scan
nmap -sT target.com

# SYN Scan (requires root)
nmap -sS target.com

# Service Version Detection
nmap -sV target.com

# Aggressive Scan
nmap -A target.com
```

### 2. Man-in-the-Middle (MITM)

**What it is:** Intercepting communication between two parties

**Examples:**
- ARP spoofing
- SSL stripping
- DNS hijacking

**Defense:** TLS, ARP validation, network segmentation

### 3. DDoS Attacks

**Types:**
| Type | Description |
|------|-------------|
| Volume-based | Traffic overload |
| Protocol | Server/resource exhaustion |
| Application | HTTP flood |

**Defense:** CDN, WAF, rate limiting

---

## 🌐 Web Attack Vectors

### Injection Attacks

```sql
-- SQL Injection
' OR '1'='1
'; DROP TABLE users; --
```

```python
# Command Injection
; cat /etc/passwd
| whoami
```

```xml
<!-- XXE Injection -->
<?xml version="1.0"?>
<!DOCTYPE foo [<!ENTITY xxe SYSTEM "file:///etc/passwd">]>
<foo>&xxe;</foo>
```

### Cross-Site Scripting (XSS)

```javascript
// Reflected XSS
<script>alert(document.cookie)</script>

// Stored XSS
<img src=x onerror=alert(1)>

// DOM-based
javascript:alert(document.domain)
```

### CSRF (Cross-Site Request Forgery)

**Defense:** CSRF tokens, SameSite cookies

---

## 📧 Email Attack Vectors

### Phishing

| Type | Description |
|------|-------------|
| Spear | Targeted, researched |
| Whaling | Executive targeting |
| Clone | Fake from real sender |

### Indicators
- Mismatched URLs
- Urgency language
- Suspicious attachments
- Grammar/errors

---

## 🔐 Credential Attacks

### Brute Force

```bash
# SSH Brute Force
hydra -l user -P passwords.txt ssh://target

# Web Login
hydra -l admin -P rockyou.txt http-post-form "/login:user=^USER^&pass=^PASS^"
```

### Credential Stuffing

**What:** Reusing leaked credentials across sites

**Defense:** Unique passwords, MFA

---

## 👤 Social Engineering

### Common Techniques

| Technique | Description |
|-----------|-------------|
| Pretexting | Creating false scenario |
| Baiting | Offering false promise |
| Quid Pro Quo | Offering service for info |
| Tailgating | Following authorized person |
| USB Drops | Leaving infected devices |

---

## 📦 Malware Types

| Type | Description |
|------|-------------|
| Virus | Self-replicating, needs host |
| Worm | Self-replicating, standalone |
| Trojan | Masquerades as legitimate |
| Ransomware | Encrypts data, demands payment |
| Spyware | Monitors activity |
| Keylogger | Records keystrokes |
| Botnet | Compromised network |

---

## 📋 Vector Risk Assessment

| Vector | Likelihood | Impact | Priority |
|--------|------------|--------|----------|
| Phishing | High | Medium | High |
| Web Exploits | High | High | High |
| Credential Theft | High | High | High |
| Supply Chain | Medium | Very High | Medium |
| Physical | Low | High | Medium |

---

## 🛡️ Defense in Depth

```
┌─────────────────────────────────────┐
│         PHYSICAL                     │
├─────────────────────────────────────┤
│         NETWORK                    │
├─────────────────────────────────────┤
│         APPLICATION               │
├─────────────────────────────────────┤
│         DATA                      │
└─────────────────────────────────────┘
```

### Controls by Layer

| Layer | Controls |
|-------|----------|
| Physical | Locks, CCTV, access cards |
| Network | Firewall, IDS, segmentation |
| Application | WAF, input validation |
| Data | Encryption, backup, DLP |

---

## 🔗 Related Topics

- [CIA Triad](CIA_Triad.md)
- [Threat Actors](threat-actors.md)
- [OWASP Top 10](../../OFFENSIVE_SECURITY/web-exploits/owasp-top-10.md)

---

[← Back to Threat Actors](threat-actors.md)