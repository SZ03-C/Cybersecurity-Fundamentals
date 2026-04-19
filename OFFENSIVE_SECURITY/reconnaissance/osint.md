# 🔍 OSINT - Open Source Intelligence

Passive information gathering from publicly available sources.

## 🎯 What is OSINT?

Gathering information from public sources without directly interacting with target.

```
┌─────────────────────────────────────────┐
│           OSINT SOURCES                 │
├─────────────────────────────────────────┤
│                                         │
│  ┌─────────┐  ┌─────────┐  ┌─────────┐  │
│  │ Search  │  │ Social  │  │  DNS   │  │
│  │ Engines │  │  Media  │  │Records │  │
│  └─────────┘  └─────────┘  └─────────┘  │
│                                         │
│  ┌─────────┐  ┌─────────┐  ┌─────────┐  │
│  │ Public  │  │  Job   │  │ SHODAN  │  │
│  │  Docs   │  │Posts   │  │ IoT    │  │
│  └─────────┘  └─────────┘  └─────────┘  │
└─────────────────────────────────────────┘
```

---

## 🔎 Google Dorking

### Search Operators

| Operator | Example | Description |
|----------|---------|-------------|
| `site:` | `site:github.com company` | Specific site |
| `inurl:` | `inurl:admin login` | URL contains |
| `intitle:` | `intitle:"index of"` | Title contains |
| `filetype:` | ` filetype:pdf` | File type |
| `ext:` | `ext:doc` | Extension |
| `-` | `-password` | Exclude |

### Useful Dorks

```bash
# Login pages
site:target.com inurl:login|admin|panel

# Exposed documents
filetype:xls "password" site:target.com

# Config files
site:target.com ext:xml | ext:json | ext:conf

# Database files
site:target.com ext:sql | ext:db

# Backup files
site:target.com ext:bak | ext:old | ext:tar
```

---

## 👥 Social Media OSINT

### Tools

| Tool | Purpose |
|------|---------|
| Sherlock | Username research |
| Social Links | Profile analysis |
| Maltego | Link analysis |

### What to Look For

- Employee names/roles
- Technology stack
- Physical locations
- Internal terminology
- Organizational structure

---

## 🌐 DNS Reconnaissance

### DNS Records

| Record | Purpose |
|--------|---------|
| A | IPv4 address |
| AAAA | IPv6 address |
| CNAME | Alias |
| MX | Mail server |
| TXT | Text/verification |
| NS | Name servers |
| SOA | Zone authority |

### DNS Tools

```bash
# Basic lookup
dig target.com

# All records
dig target.com ANY

# Reverse DNS
dig -x 192.168.1.1

# Zone transfer (if allowed)
dig axfr target.com @ns1.target.com
```

---

## 🕵️ Passive Reconnaissance Tools

### theHarvester

```bash
# Email gathering
theHarvester -d target.com -b all

# Specific sources
theHarvester -d target.com -b linkedin
```

### Recon-ng

```bash
#启动
recon-ng

# 使用模块
modules search
use recon/domains-contacts/whois
```

---

## 🔍 People Search

### People Search Engines

- Pipl
- Truecaller
- Spokeo
- BeenVerified

### What to Find

- Contact information
- Previous addresses
- Social profiles
- Relatives/associates

---

## 📦 Company OSINT

### Public Records

- WHOIS information
- Business registration
- Patent filings
- Job postings (tech stack!)
- Press releases

---

## 🛠️ OSINT Automation

### SpiderFoot

```bash
# Basic scan
spiderfoot -d -s target.com

#特定模块
spiderfoot -m module1,module2 -d target.com
```

---

## 📋 OSINT Checklist

- [ ] Target domain WHOIS
- [ ] Email addresses
- [ ] Employee information
- [ ] Technology stack
- [ ] Subdomains
- [ ] Public leaks
- [ ] Social media presence
- [ ] Physical locations

---

## ⚠️ Legal Considerations

- Only use public sources
- Don't access private data
- Document findings
- Follow responsible disclosure

---

## 🔗 Related Topics

- [Network Scanning](network-scanning.md)
- [Nmap Basics](../../TOOLS/nmap/basics/port-scanning-basics.sh)

---

[← Back to Offensive Security](../README.md)