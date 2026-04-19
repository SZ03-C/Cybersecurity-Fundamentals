# 🌐 TLS/SSL - Transport Layer Security

Securing communications over networks.

## 🎯 What is TLS?

Protocol that secures data in transit between clients and servers.

```
┌─────────────────────────────────────────┐
│         TLS SECURITY LAYERS              │
├─────────────────────────────────────────┤
│                                         │
│  Application Layer (HTTPS, SSH, etc.)  │
│           ▼                              │
│       TLS Layer                         │
│           ▼                              │
│      TCP Layer                         │
│           ▼                              │
│      IP Layer                         │
└─────────────────────────────────────────┘
```

## 📊 TLS History

| Version | Status | Year |
|---------|--------|------|
| SSL 1.0 | ❌ Broken | 1994 |
| SSL 2.0 | ❌ Broken | 1994 |
| SSL 3.0 | ❌ Broken | 1996 |
| TLS 1.0 | ❌ Deprecated | 1999 |
| TLS 1.1 | ❌ Deprecated | 2006 |
| TLS 1.2 | ✅ Current | 2008 |
| TLS 1.3 | ✅ Latest | 2018 |

---

## 🔐 TLS Handshake

```
┌─────────────────────────────────────────────┐
│          TLS HANDSHAKE                      │
├─────────────────────────────────────────────┤
│                                             │
│  Client ──► ClientHello (cipher suites)    │
│               ▼                            │
│  Server ──► ServerHello (chosen cipher)   │
│               ▼                            │
│  Server ──► Certificate + Key Exchange  │
│               ▼                            │
│  Client ──► Verify + Finished            │
│               ▼                            │
│  Encrypted Session Established ✓          │
│                                             │
└─────────────────────────────────────────────┘
```

### What Happens

1. **ClientHello** - Supported cipher suites
2. **ServerHello** - Selected cipher + certificate
3. **Key Exchange** - Generate session keys
4. **Verify** - Confirm handshake integrity

---

## 🛡️ TLS 1.3 Improvements

| TLS 1.2 | TLS 1.3 |
|----------|---------|
| 2 round trips | 1 round trip |
| Many cipher suites | 5 secure suites |
| MD5/SHA-1 legacy | SHA-256+ only |
| Session resumption | 0-RTT mode |

---

## 🔧 Checking TLS

### OpenSSL CLI

```bash
# Check certificate
openssl s_client -connect google.com:443

# Check TLS version
openssl s_client -connect google.com:443 -tls1_2

# Cipher suites
openssl ciphers -s 'HIGH:!aNULL'
```

### SSL Labs Test

```bash
# Online test
https://www.ssllabs.com/ssltest/
```

---

## 📋 Certificate Types

| Type | Validation | Green Bar? |
|------|------------|------------|
| DV | Domain only | Yes |
| OV | Organization | Yes |
| EV | Extended | Yes (strict) |

---

## ⚠️ Common Issues

| Issue | Fix |
|-------|-----|
| Expired certificate | Renew |
| Self-signed | Replace with CA |
| Weak cipher | Disable, use TLS 1.2+ |
| Missing chain | Install intermediate |

---

## 🔧 Nginx Configuration

```nginx
server {
    listen 443 ssl http2;
    
    ssl_certificate /path/to/cert.pem;
    ssl_certificate_key /path/to/key.pem;
    
    # Modern configuration
    ssl_protocols TLSv1.2 TLSv1.3;
    ssl_ciphers ECDHE-ECDSA-AES128-GCM-SHA256:...;
    ssl_prefer_server_ciphers on;
    
    # HSTS
    add_header Strict-Transport-Security "max-age=63072000";
}
```

---

## 🛡️ Best Practices

- Use TLS 1.3 (or 1.2 minimum)
- Disable TLS 1.0/1.1
- Use strong cipher suites
- Enable HSTS
- Use CA-signed certificates

---

## 📋 Checklist

- [ ] TLS 1.2+ enabled
- [ ] TLS 1.0/1.1 disabled
- [ ] Strong ciphers only
- [ ] Certificate valid
- [ ] HSTS enabled
- [ ] No weak protocols

---

## 🔗 Related Topics

- [Symmetric Encryption](symmetric-encryption.md)
- [Asymmetric Encryption](asymmetric-encryption.md)

---

[← Back to Cryptography](../README.md)