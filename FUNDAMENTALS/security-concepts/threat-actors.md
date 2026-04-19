# 🎭 Threat Actors - Who Attacks and Why

Understanding threat actors helps prioritize security efforts.

## 📊 Threat Actor Overview

```
┌─────────────────────────────────────────────────────────────────┐
│                    THREAT ACTOR PYRAMID                     │
├─────────────────────────────────────────────────────────────────┤
│                                                         │
│                        APT                                │
│                       ▲▲▲                                │
│                      /    \                              │
│            Cyber Criminal          ◄──── Most sophisticated│
│                    ▲▲▲                                 │
│                   /    \                               │
│           Hacktivist         ◄──── Ideology-based        │
│                  ▲▲▲                                  │
│                 /    \                                 │
│            Insider        ◄──── Trusted insider        │
│                ▲▲▲                                    │
│               /    \                                   │
│         Script Kiddie    ◄──── Least sophisticated   │
│                                                         │
└─────────────────────────────────────────────────────────────────┘
```

## 🏷️ Threat Actor Types

### 1. Script Kiddies

**Motivation:** Fame, learning, curiosity

| Aspect | Details |
|--------|---------|
| Skill Level | Low |
| Tools | Pre-made tools, scripts |
| Target | Random, easy targets |
| Impact | Usually low (defacement, downtime) |

**Example:** Running Metasploit modules without understanding

**Defense:** Keep systems updated, basic hardening

---

### 2. Hacktivists

**Motivation:** Political/social causes, ideology

| Aspect | Details |
|--------|---------|
| Skill Level | Medium to High |
| Tools | Custom tools, DDoS |
| Target | Organizations they oppose |
| Impact | Data leaks, service disruption |

**Examples:** Anonymous, LulzSec

**Defense:** Strong DDoS protection, monitoring

---

### 3. Cyber Criminals

**Motivation:** Financial gain

| Aspect | Details |
|--------|---------|
| Skill Level | Low to High |
| Tools | Ransomware, phishing kits, exploits |
| Target | Anyone with money/data |
| Impact | Financial loss, data theft |

**Attack Types:**
- Ransomware
- Credential theft
- Credit card fraud
- Business email compromise (BEC)

**Defense:** Backups, MFA, awareness training

---

### 4. Insider Threats

**Motivation:** Revenge, money, negligence

| Type | Description |
|------|-------------|
| Malicious | Intentional harm or theft |
| Negligent | Careless, accidental |
| Compromised | Stolen credentials |

**Indicators:**
- Unauthorized access attempts
- Data exfiltration
- Policy violations
- Odd working hours

**Defense:** Least privilege, monitoring, DLP

---

### 5. Advanced Persistent Threat (APT)

**Motivation:** Espionage, long-term access

| Aspect | Details |
|--------|---------|
| Skill Level | Very High |
| Tools | Zero-days, custom malware |
| Target | Government, critical infrastructure |
| Impact | Severe,长期潜伏 |

**Characteristics:**
- Long-term presence
- Evading detection
- Nation-state backed
- Highly targeted

**Examples:** FIN7, Lazarus, Cozy Bear

**Defense:** Advanced detection, threat hunting

---

## 🎯 Attack Vectors

### How Attackers Gain Access

```
┌─────────────────────────────────────────┐
│           ATTACK VECTORS                 │
├─────────────────────────────────────────┤
│                                         │
│  ┌─────────┐    ┌─────────┐           │
│  │Network  │    │  Web   │             │
│  │Attacks  │    │Attacks │             │
│  │- Scanning│    │- SQLi  │            │
│  │- Exploits│    │- XSS   │             │
│  └─────────┘    └─────────┘           │
│                                         │
│  ┌─────────┐    ┌─────────┐           │
│  │  Email  │    │Social  │             │
│  │Attacks │    │Engineering          │
│  │- Phishing│    │- Pretexting       │
│  │- Malware│    │- Baiting │            │
│  └─────────┘    └─────────┘           │
│                                         │
│  ┌─────────┐    ┌─────────┐           │
│  │Physical │    │Supply   │             │
│  │Attacks  │    │Chain    │            │
│  │- USB    │    │- Third- │            │
│  │- Theft  │    │  party  │            │
│  └─────────┘    └─────────┘           │
└─────────────────────────────────────────┘
```

### Common Attack Techniques

| Vector | Examples | Prevention |
|--------|----------|------------|
| Phishing | Email, SMS, voice | Training, filtering |
| Exploits | Buffer overflow, zero-day | Patching, WAF |
| Credential | Brute force, stuffing | MFA, lockout policy |
| Social Engineering | Pretexting, baiting | Awareness |
| Physical | USB drops, tailgating | Access control |
| Supply Chain | Compromised software | Verification |

---

## 🔬 MITRE ATT&CK Framework

Categories of attacker techniques:

| Tactic | Description |
|--------|-------------|
| Reconnaissance | Gathering information |
| Resource Development | Setting up infrastructure |
| Initial Access | Getting into the network |
| Execution | Running malicious code |
| Persistence | Maintaining access |
| Privilege Escalation | Gaining higher access |
| Defense Evasion | Avoiding detection |
| Credential Access | Stealing credentials |
| Discovery | Finding targets |
| Lateral Movement | Moving between systems |
| Collection | Gathering data |
| Command & Control | C2 communication |
| Exfiltration | Stealing data |
| Impact | Disrupting systems |

---

## 🛡️ Defense by Threat Actor

| Threat Actor | Priority Defenses |
|-------------|------------------|
| Script Kiddies | Updates, basic hardening |
| Hacktivists | DDoS protection, monitoring |
| Cyber Criminals | MFA, backups, training |
| Insiders | Least privilege, DLP |
| APT | Threat hunting, segmentation |

---

## 📋 Assessment Questions

1. Who would target you/your organization?
2. What's their motivation?
3. What do they want?
4. How would they get in?
5. What's the impact if they succeed?

---

## 🔗 Related Topics

- [CIA Triad](CIA_Triad.md)
- [Risk Assessment →](risk-management.md)

---

[← Back to CIA Triad](CIA_Triad.md)