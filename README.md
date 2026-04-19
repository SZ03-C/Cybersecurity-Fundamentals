# 🔐 Cybersecurity Fundamentals

> A comprehensive cybersecurity knowledge base covering from basics to advanced defensive and offensive security concepts

![Cybersecurity](https://img.shields.io/badge/Level-Beginner%20to%20Advanced-red)
![Security+](https://img.shields.io/badge/Certification-CompTIA%20Security+-blue)
![Last Updated](https://img.shields.io/badge/Updated-March%202026-orange)

## 📚 Repository Structure

```
Cybersecurity-Fundamentals/
├── README.md
├── FUNDAMENTALS/
│   ├── security-concepts/
│   │   ├── CIA_Triad.md
│   │   ├── threat-actors.md
│   │   ├── attack-vectors.md
│   │   └── risk-management.md
│   ├── cryptography/
│   │   ├── symmetric-encryption.md
│   │   ├── asymmetric-encryption.md
│   │   ├── hashing.md
│   │   ├── digital-signatures.md
│   │   └── tls-ssl.md
│   └── networking-security/
│       ├── firewalls.md
│       ├── ids-ips.md
│       ├── vpns.md
│       └── zero-trust.md
├── OFFENSIVE_SECURITY/
│   ├── reconnaissance/
│   │   ├── osint.md
│   │   ├── network-scanning.md
│   │   └── vulnerability-assessment.md
│   ├── exploitation/
│   │   ├── common-exploits.md
│   │   ├── buffer-overflow.md
│   │   └── web-exploits.md
│   ├── post-exploitation/
│   │   ├── lateral-movement.md
│   │   ├── privilege-escalation.md
│   │   └── persistence.md
│   └── tools/
│       ├── metasploit/
│       ├── burpsuite/
│       └── sqlmap/
├── DEFENSIVE_SECURITY/
│   ├── incident-response/
│   │   ├── IR_Process.md
│   │   ├── forensics-basics.md
│   │   └── malware-analysis.md
│   ├── SIEM/
│   │   ├── siem-concepts.md
│   │   └── log-analysis.md
│   ├── hardening/
│   │   ├── windows-hardening.md
│   │   ├── linux-hardening.md
│   │   └── network-hardening.md
│   └── threat-hunting/
│       ├── threat-hunting-basics.md
│       └── mitre-attack.md
├── COMPLIANCE/
│   ├── iso-27001.md
│   ├── gdpr.md
│   └── nist-framework.md
├── CTF_RESOURCES/
│   ├── ctf-guide.md
│   ├── forensics-challenges.md
│   └── web-security-challenges.md
└── CERTIFICATIONS/
    ├── comptia-security-plus.md
    ├── ceh-roadmap.md
    └── oscp-preparation.md
```

## 🎯 Learning Roadmap

### Month 1-2: Security Fundamentals

```
Week 1-2: Core Concepts
├── CIA Triad (Confidentiality, Integrity, Availability)
├── Types of threats and threat actors
├── Attack vectors and surfaces
└── Risk assessment basics

Week 3-4: Cryptography Basics
├── Symmetric vs Asymmetric encryption
├── Hashing algorithms (MD5, SHA, bcrypt)
├── Digital signatures and certificates
└── TLS/SSL handshake
```

### Month 3-4: Networking Security

```
Week 5-6: Network Defense
├── Firewalls (hardware & software)
├── IDS/IPS systems
├── VPNs and network segmentation
└── Network monitoring

Week 7-8: Applied Security
├── Network hardening
├── Access control models
├── Authentication methods
└── AAA frameworks
```

### Month 5-6: Offensive Security Basics

```
Week 9-10: Reconnaissance
├── OSINT techniques
├── Network scanning with Nmap
├── Vulnerability assessment
└── Enumeration

Week 11-12: Common Vulnerabilities
├── OWASP Top 10
├── SQL Injection
├── XSS and CSRF
└── Buffer overflow basics
```

### Month 7-8: Defensive Security

```
Week 13-14: Incident Response
├── IR process (Preparation → Detection → Response)
├── Digital forensics basics
├── Malware analysis fundamentals
└── Evidence preservation

Week 15-16: SIEM & Monitoring
├── Log analysis
├── SIEM tools (Splunk, ELK)
├── Threat hunting concepts
└── MITRE ATT&CK framework
```

## 🔒 Security Fundamentals

### CIA Triad

```
        ┌───────────────┐
        │   INTEGRITY   │
        │  ✓ Data accuracy
        │  ✓ No unauthorized changes
        │  ✓ Audit trails
        └───────┬───────┘
                │
    ┌───────────┴───────────┐
    │                       │
┌───┴───┐               ┌───┴───┐
│ CONF- │               │ AVAIL-│
│IDENT- │               │  ABLE │
│IALITY │               │       │
│ ✓ Encryption
│ ✓ Access controls
└─────────┘               └───────┘
```

### Types of Threats

| Category | Examples |
|----------|----------|
| Malware | Virus, Worm, Trojan, Ransomware |
| Network | MITM, DDoS, Sniffing |
| Web | SQLi, XSS, CSRF |
| Social | Phishing, Pretexting, Baiting |
| Physical | Theft, Shoulder surfing |

### Threat Actors

| Actor | Motivation | Example |
|-------|------------|---------|
| Script Kiddie | Fame | Basic attacks |
| Hacktivist | Political | DDoS campaigns |
| Cyber Criminal | Financial | Ransomware, Theft |
| APT | Espionage | State-sponsored |
| Insider | Varies | Disgruntled employees |

## 🛡️ Defense Mechanisms

### Layered Security (Defense in Depth)

```
┌─────────────────────────────────────┐
│         Physical Security           │ ← Guards, locks, CCTV
├─────────────────────────────────────┤
│         Network Security            │ ← Firewalls, IDS
├─────────────────────────────────────┤
│         Endpoint Security           │ ← Antivirus, EDR
├─────────────────────────────────────┤
│         Application Security        │ ← WAF, input validation
├─────────────────────────────────────┤
│         Data Security               │ ← Encryption, backups
└─────────────────────────────────────┘
```

### Access Control Models

```
DAC (Discretionary)     │ Owner controls access
─────────────────────────────────────────────
MAC (Mandatory)         │ System enforces based on clearance
─────────────────────────────────────────────
RBAC (Role-Based)       │ Access based on job function
─────────────────────────────────────────────
ABAC (Attribute-Based)   │ Access based on multiple attributes
```

## 📖 OWASP Top 10 (2021)

1. **A01: Broken Access Control** - Unauthorized access
2. **A02: Cryptographic Failures** - Data exposure
3. **A03: Injection** - SQL, NoSQL, OS injection
4. **A04: Insecure Design** - Missing security controls
5. **A05: Security Misconfiguration** - Default configs
6. **A06: Vulnerable Components** - Outdated libraries
7. **A07: Auth Failures** - Weak authentication
8. **A08: Data Integrity Failures** - Software updates
9. **A09: Logging Failures** - Missing incident tracking
10. **A10: SSRF** - Server-side request forgery

## 🔧 Essential Tools
These are just example commands in further practices the whole installation to implementation will be demonstrated
### Network Analysis
```bash
# Nmap - Port scanning
nmap -sV -sC -p- 192.168.1.1

# Wireshark - Packet analysis
wireshark -i eth0

# tcpdump - Command-line sniffing
sudo tcpdump -i eth0 port 80
```

### Vulnerability Assessment
```bash
# Nikto - Web server scanner
nikto -h https://target.com

# OpenVAS - Vulnerability scanner
openvas-start

# Burp Suite - Web proxy
burpsuite
```

### Password Cracking
```bash
# John the Ripper
john --wordlist=rockyou.txt hash.txt

# Hashcat
hashcat -m 1000 hash.txt rockyou.txt

# Hydra - Online attacks
hydra -l admin -P rockyou.txt ssh://target.com
```

### Forensics
```bash
# Autopsy - Disk analysis
autopsy &

# Volatility - Memory forensics
volatility -f memory.dmp windows.pslist

# Binwalk - Embedded files
binwalk firmware.bin
```

## 📋 Security Checklist

### Personal Security
- [ ] Use a password manager
- [ ] Enable 2FA everywhere
- [ ] Keep software updated
- [ ] Use VPN on public WiFi
- [ ] Backup important data

### System Hardening
- [ ] Disable unnecessary services
- [ ] Configure firewall rules
- [ ] Enable logging and monitoring
- [ ] Remove default passwords
- [ ] Implement principle of least privilege

### Network Security
- [ ] Segment networks (VLANs)
- [ ] Use encryption (TLS/WPA3)
- [ ] Implement IDS/IPS
- [ ] Regular security audits
- [ ] Update firmware regularly

## 📚 Practice Platforms

### Beginner
- [TryHackMe](https://tryhackme.com/) - Guided learning
- [PicoCTF](https://picoctf.org/) - Beginner CTFs
- [CyberSec Labs](https://www.cyberseclabs.co.uk/)

### Intermediate
- [HackTheBox](https://hackthebox.eu/) - Advanced boxes
- [VulnHub](https://www.vulnhub.com/) - Downloadable VMs
- [PortSwigger Web Academy](https://portswigger.net/web-security)

### Advanced
- [Proving Grounds](https://proving grounds.offensive.com/)
- [PentesterLab](https://pentesterlab.com/)
  

## 🎓 Certifications Path

```
Beginner          Intermediate         Advanced
────────────────────────────────────────────────
CompTIA           CEH                  OSCP
ITF+      →       Security+    →       OSEP
          →       CEH          →       CISSP
                                       CISM
```

## 📝 Incident Response Process

```
┌─────────────────────────────────────────────────┐
│                    PREPARE                        │
│   - Create IR team                               │
│   - Develop policies                             │
│   - Train staff                                  │
└─────────────────────────────────────────────────┘
                         ↓
┌─────────────────────────────────────────────────┐
│                    DETECT                        │
│   - Monitor systems                              │
│   - Analyze alerts                               │
│   - Initial assessment                           │
└─────────────────────────────────────────────────┘
                         ↓
┌─────────────────────────────────────────────────┐
│                    CONTAIN                       │
│   - Isolate affected systems                     │
│   - Preserve evidence                            │
│   - Limit damage                                 │
└─────────────────────────────────────────────────┘
                         ↓
┌─────────────────────────────────────────────────┐
│                    ERADICATE                     │
│   - Remove malware                               │
│   - Close vulnerabilities                        │
│   - Patch systems                                │
└─────────────────────────────────────────────────┘
                         ↓
┌─────────────────────────────────────────────────┐
│                    RECOVER                       │
│   - Restore from backups                         │
│   - Verify integrity                             │
│   - Resume operations                            │
└─────────────────────────────────────────────────┘
                         ↓
┌─────────────────────────────────────────────────┐
│                    LESSONS                       │
│   - Document incident                             │
│   - Update procedures                            │
│   - Train team                                   │
└─────────────────────────────────────────────────┘
```

## ⚠️ Disclaimer

> This repository is for **educational purposes only**. Always practice ethical hacking, obtain proper authorization, and follow responsible disclosure practices.

## 🤝 Contributing

Feel free to add your notes, writeups, and resources!

## 📧 Connect

- GitHub: https://github.com/SZ03-C
- LinkedIn: https://www.linkedin.com/in/shaguftha-zabeen-a41371379/

---

*Stay safe, stay secure!* 🔒
