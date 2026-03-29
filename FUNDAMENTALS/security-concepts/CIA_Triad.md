# 🔐 CIA Triad - Core Security Principles

The CIA Triad represents the three fundamental principles of information security.

## 📐 Visual Overview

```
        CONFIDENTIALITY
              ▲
             / \
            /   \
           /     \
          /   🔐  \
         /         \
        /───────────\
       /      │      \
      /       │       \
     /    INTEGRITY    \
    /         │         \
   ▼──────────┴──────────▼
CONFIDENTIALITY ◄──────► INTEGRITY ◄──────► AVAILABILITY
   (Privacy)             (Accuracy)           (Access)
```

## 🔒 1. Confidentiality (Privacy)

### Definition
Protecting information from unauthorized disclosure.

### Examples
- Encrypting sensitive files
- Password protection
- Access controls
- Classification of data

### Controls
```markdown
┌─────────────────────────────────────┐
│        CONFIDENTIALITY               │
├─────────────────────────────────────┤
│  Encryption                         │
│  ├── AES-256                        │
│  ├── RSA                            │
│  └── TLS/SSL                        │
├─────────────────────────────────────┤
│  Access Controls                    │
│  ├── RBAC (Role-Based)              │
│  ├── MAC (Mandatory)               │
│  └── DAC (Discretionary)            │
├─────────────────────────────────────┤
│  Authentication                     │
│  ├── MFA (Multi-Factor)             │
│  ├── Biometrics                     │
│  └── Certificates                   │
└─────────────────────────────────────┘
```

### Violations
- Data breaches
- Eavesdropping
- Social engineering
- Unauthorized access

## ✔️ 2. Integrity (Accuracy)

### Definition
Maintaining accuracy and consistency of data.

### Examples
- Hash verification
- Digital signatures
- Version control
- Audit trails

### Controls
```markdown
┌─────────────────────────────────────┐
│           INTEGRITY                 │
├─────────────────────────────────────┤
│  Hashing                            │
│  ├── SHA-256                        │
│  ├── SHA-3                          │
│  └── bcrypt                         │
├─────────────────────────────────────┤
│  Digital Signatures                 │
│  ├── Non-repudiation                │
│  ├── Authentication                 │
│  └── Integrity verification         │
├─────────────────────────────────────┤
│  Checksums                          │
│  ├── MD5 (legacy)                   │
│  └── CRC                            │
└─────────────────────────────────────┘
```

### Violations
- Unauthorized modifications
- Corruption
- Man-in-the-middle attacks
- Software tampering

## ⚡ 3. Availability (Access)

### Definition
Ensuring timely and reliable access to data.

### Examples
- Redundant systems
- Backup power
- DDoS protection
- Load balancers

### Controls
```markdown
┌─────────────────────────────────────┐
│          AVAILABILITY               │
├─────────────────────────────────────┤
│  Redundancy                         │
│  ├── RAID                           │
│  ├── Clustering                     │
│  └── Failover systems              │
├─────────────────────────────────────┤
│  Backups                            │
│  ├── Regular scheduling             │
│  ├── Off-site storage               │
│  └── Recovery testing               │
├─────────────────────────────────────┤
│  DDoS Protection                    │
│  ├── CDN                            │
│  ├── WAF                            │
│  └── Rate limiting                  │
└─────────────────────────────────────┘
```

### Violations
- DDoS attacks
- Hardware failures
- Natural disasters
- Ransomware

## ⚖️ Balancing the Triad

### Real-World Examples

| Scenario | Priority | Trade-offs |
|----------|----------|------------|
| Military systems | Confidentiality | May sacrifice availability |
| Banking systems | Integrity | Strong auth, audit trails |
| E-commerce | Availability | Real-time processing |

### Conflicts
```
┌─────────────────────────────────────────┐
│         CONFLICTS EXAMPLE               │
├─────────────────────────────────────────┤
│                                         │
│  High Security ◄──► Easy Access        │
│                                         │
│  More encryption = slower processing    │
│  Stricter auth = longer login times     │
│  More backups = higher storage costs    │
│                                         │
└─────────────────────────────────────────┘
```

## 📋 Implementation Checklist

### Confidentiality
- [ ] Data classification implemented
- [ ] Encryption at rest and in transit
- [ ] Access controls configured
- [ ] MFA enabled for critical systems
- [ ] Regular access reviews performed

### Integrity
- [ ] Checksums/hashing implemented
- [ ] Digital signatures in use
- [ ] Version control for code
- [ ] Audit logging enabled
- [ ] Change management process

### Availability
- [ ] Redundant systems in place
- [ ] Backup strategy defined
- [ ] Disaster recovery plan exists
- [ ] Monitoring/alerting active
- [ ] Incident response plan ready

## 🎯 Security Controls Mapping

| Control | Confidentiality | Integrity | Availability |
|---------|-----------------|-----------|--------------|
| Encryption | ✓ | ✓ | |
| Access Control | ✓ | ✓ | |
| Backup/Recovery | | ✓ | ✓ |
| IDS/IPS | ✓ | ✓ | ✓ |
| Firewall | ✓ | | ✓ |
| Antivirus | | ✓ | ✓ |

## 📚 Related Concepts

- **Non-repudiation** - Sender can't deny sending
- **Authentication** - Verifying identity
- **Authorization** - Permissions after auth
- **Accounting/Auditing** - Tracking actions

## ❓ Quiz Questions

1. What protects confidentiality?
2. Which triad component prevents unauthorized changes?
3. What prevents DDoS attacks?
4. How do digital signatures maintain integrity?
5. Why might a bank prioritize integrity over availability?

---

[← Back to Security Concepts](../README.md) | [Threat Actors →](threat-actors.md)
