# 🌐 Network Scanning - Active Reconnaissance

Active discovery of network hosts and services.

## 🎯 What is Network Scanning?

Actively probing targets to discover live hosts, open ports, and services.

```
┌─────────────────────────────────────────┐
│       SCANNING PHASES                   │
├─────────────────────────────────────────┤
│                                         │
│  1. Host Discovery   (Is it alive?)     │
│         ▼                               │
│  2. Port Scanning   (What's open?)      │
│         ▼                               │
│  3. Service Enum  (What version?)    │
│         ▼                               │
│  4. OS Detection  (What OS?)         │
│         ▼                               │
│  5. Vulnerability  (What's weak?)    │
│                                         │
└─────────────────────────────────────────┘
```

---

## 🖥️ Nmap Basics

### Host Discovery

```bash
# Ping sweep
nmap -sn 192.168.1.0/24

# SYN discovery (requires root)
nmap -PS 192.168.1.1

# TCP discovery
nmap -PT 192.168.1.1
```

### Port Scanning

```bash
# TCP Connect (no root needed)
nmap -sT target.com

# SYN Scan (requires root)
nmap -sS target.com

# UDP Scan
nmap -sU target.com
```

### Common Port Scans

```bash
# Quick scan top 100 ports
nmap -F target.com

# Top 1000 ports
nmap --top-ports 1000 target.com

# All ports
nmap -p- target.com

# Specific ports
nmap -p 22,80,443,3306 target.com
```

---

## 📊 Port States

| State | Meaning |
|-------|---------|
| Open | Service accepting connections |
| Closed | No service, but accessible |
| Filtered | Firewall blocking |

---

## 🔍 Service Version Detection

```bash
# Version detection
nmap -sV target.com

# Aggressive (OS, version, script)
nmap -A target.com

# All available info
nmap -sV -sC -O target.com
```

---

## 🖥️ Nmap Scripts

### Basic Usage

```bash
# Default scripts
nmap -sC target.com

# Specific script
nmap --script=http-title target.com

# Script category
nmap --script=vuln target.com
```

### Useful Scripts

| Script | Purpose |
|--------|---------|
| `http-title` | Get web page title |
| `http-headers` | Get HTTP headers |
| `ssl-cert` | Get SSL certificate |
| `smb-enum-shares` | List SMB shares |
| `ssh-auth-methods` | SSH auth methods |
| `vuln` | Run vulnerability checks |

---

## 🎯 UDP Scanning

### Common UDP Scans

```bash
# SNMP
nmap -sU -p 161 target.com

# UDP top ports
nmap -sU -F target.com
```

---

## 📋 Full Nmap Examples

```bash
# Quick discovery
nmap -sn 10.0.0.0/24

# Full scan
nmap -sS -sV -sC -O -p- target.com

# Stealth scan
nmap -sS -p- -T4 target.com

# Web focused
nmap -sV -p 80,443,8080,8443 target.com
```

---

## 🛠️ Alternative Tools

### RustScan

```bash
# Faster scanning
rustscan -a target.com

# With Nmap
rustscan -a target.com -- -sV
```

---

## 📋 Scanning Checklist

- [ ] Confirm authorization
- [ ] Define scope
- [ ] Host discovery
- [ ] Port scan
- [ ] Service identification
- [ ] OS detection
- [ ] Vulnerability scan
- [ ] Document findings

---

## ⚠️ Legal Considerations

- Only scan systems you own or have permission to test
- Document all activities
- Follow scope rules

---

[← Back to OSINT](osint.md)
[Next: Vulnerability Assessment →](vulnerability-assessment.md)