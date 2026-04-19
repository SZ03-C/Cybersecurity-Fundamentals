# 🔍 Hashing

One-way function that produces a fixed-size output.

## 🎯 What is Hashing?

```
┌─────────────────────────────────────────┐
│            HASHING                      │
├─────────────────────────────────────────┤
│                                         │
│  "Hello World" ───► [SHA-256] ───►     │
│                   abcef...              │
│                                         │
│  Properties:                           │
│  ✓ One-way (not reversible)           │
│  ✓ Fixed output size                   │
│  ✓ Avalanche effect (small change=big) │
│  ✓ Unique (low collision)             │
└─────────────────────────────────────────┘
```

## 📊 Hash Functions

### MD5

- **Output:** 128-bit (32 hex chars)
- **Status:** ❌ BROKEN - collisions possible
- **Use:** File checksums only

### SHA-1

- **Output:** 160-bit (40 hex chars)
- **Status:** ❌ BROKEN - collisions found
- **Use:** Legacy only

### SHA-256

- **Output:** 256-bit (64 hex chars)
- **Status:** ✅ Secure
- **Use:** Most common today

### SHA-3

- **Output:** 256/384/512-bit
- **Status:** ✅ Secure
- **Use:** High security needs

---

## 🔧 Python Example

```python
import hashlib

def hash_data(data, algorithm='sha256'):
    hash_func = hashlib.new(algorithm)
    hash_func.update(data.encode())
    return hash_func.hexdigest()

# Usage
message = "Hello World"
print(hash_data(message, 'sha256'))
# 7fd77495f5e5a

print(hash_data(message, 'sha512'))
print(hash_data(message, 'md5'))
```

---

## 🔒 Password Hashing

### Why Not Regular Hashing?

Regular hashes are too fast - vulnerable to brute force.

### Solution: Key Derivation Functions

| Algorithm | Memory | Best For |
|-----------|--------|----------|
| PBKDF2 | Low | Legacy compatibility |
| bcrypt | Medium | Good balance |
| scrypt | High | Memory-hard |
| Argon2 | Configurable | Best practice |

### bcrypt Example

```python
import bcrypt

def hash_password(password):
    salt = bcrypt.gensalt()
    return bcrypt.hashpw(password.encode(), salt)

def verify_password(password, hashed):
    return bcrypt.checkpw(password.encode(), hashed)

# Usage
hashed = hash_password("mypassword")
print(verify_password("mypassword", hashed))  # True
print(verify_password("wrong", hashed))    # False
```

---

## 📋 Use Cases

| Use Case | Hash Type |
|----------|----------|
| File Integrity | SHA-256 |
| Password Storage | bcrypt, Argon2 |
| Digital Signatures | SHA-256, SHA-512 |
| Blockchain | SHA-256, Keccak |

---

## ⚠️ Best Practices

- Never use MD5/SHA-1 for security
- Use bcrypt/Argon2 for passwords
- Add salt to prevent rainbow tables
- Use sufficient iterations

---

## 🎯 Comparing Hashes

```python
# Timing attack safe comparison
import hmac

def secure_compare(hash1, hash2):
    return hmac.compare_digest(hash1, hash2)
```

---

## 🔗 Related Topics

- [Symmetric Encryption](symmetric-encryption.md)
- [Digital Signatures](digital-signatures.md)

---

[← Back to Cryptography](../README.md)