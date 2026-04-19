# 🔐 Asymmetric Encryption

Public key for encryption, private key for decryption.

## 🎯 What is Asymmetric Encryption?

```
┌─────────────────────────────────────────┐
│    ASYMMETRIC ENCRYPTION                 │
├─────────────────────────────────────────┤
│                                         │
│  Plain Text ──► [E] ──► Cipher Text     │
│               PUB_KEY                   │
│                     ▼                    │
│  Cipher Text ──► [D] ──► Plain Text    │
│               PRIV_KEY                  │
└─────────────────────────────────────────┘
```

## 📊 Key Pairs

| Key | Purpose | Keep Secret? |
|-----|---------|-------------|
| Public Key | Encrypt, verify | No (share freely) |
| Private Key | Decrypt, sign | YES (never share) |

---

## 🛡️ Common Algorithms

### RSA

| Key Size | Security Level |
|----------|----------------|
| 2048-bit | Standard |
| 3072-bit | Strong |
| 4096-bit | Highest |

### ECC (Elliptic Curve)

| Curve | Security Level |
|-------|----------------|
| P-256 | Standard |
| P-384 | Strong |
| P-521 | Highest |

---

## 🔧 Python Example

```python
from Crypto.PublicKey import RSA
from Crypto.Cipher import PKCS1_OAEP
import base64

def generate_keypair():
    key = RSA.generate(2048)
    return key.export_key(), key.publickey().export_key()

def encrypt(message, public_key):
    key = RSA.import_key(public_key)
    cipher = PKCS1_OAEP.new(key)
    ciphertext = cipher.encrypt(message.encode())
    return base64.b64encode(ciphertext).decode()

def decrypt(ciphertext, private_key):
    key = RSA.import_key(private_key)
    cipher = PKCS1_OAEP.new(key)
    data = base64.b64decode(ciphertext)
    return cipher.decrypt(data).decode()

# Usage
priv, pub = generate_keypair()
encrypted = encrypt("Secret", pub)
decrypted = decrypt(encrypted, priv)
```

---

## 🎯 Use Cases

| Use Case | Description |
|----------|-------------|
| Key Exchange | Send symmetric key securely |
| Digital Signatures | Verify sender identity |
| SSL/TLS | Secure web traffic |
| Email Encryption | PGP, S/MIME |

---

## ⚠️ Best Practices

- Use 2048-bit+ RSA or P-256+ ECC
- Never share private key
- Use OAEP padding for encryption
- Use PSS padding for signatures

---

## 📋 Comparison: RSA vs ECC

| Aspect | RSA | ECC |
|--------|-----|-----|
| Key Size | 2048-bit | 256-bit |
| Speed | Slower | Faster |
| Security | High | High (smaller keys) |
| Adoption | Very widespread | Growing |

---

## 🔗 Related Topics

- [Symmetric Encryption](symmetric-encryption.md)
- [Digital Signatures](digital-signatures.md)

---

[← Back to Cryptography](../README.md)