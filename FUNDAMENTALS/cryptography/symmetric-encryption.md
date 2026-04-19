# 🔐 Symmetric Encryption

Same key for encryption and decryption.

## 🎯 What is Symmetric Encryption?

```
┌─────────────────────────────────────────┐
│     SYMMETRIC ENCRYPTION                 │
├─────────────────────────────────────────┤
│                                         │
│  Plain Text ──► [E] ──► Cipher Text     │
│                  KEY                   │
│                     ▼                  │
│  Cipher Text ──► [D] ──► Plain Text   │
│                  KEY                   │
└─────────────────────────────────────────┘
```

## 📊 Key Characteristics

| Aspect | Details |
|--------|---------|
| Key | Same for encrypt/decrypt |
| Speed | Fast |
| Key Management |Challenged |
| Use Case | Bulk data encryption |

---

## 🛡️ Common Algorithms

### AES (Advanced Encryption Standard)

| Key Size | Security Level |
|----------|----------------|
| 128-bit | Standard |
| 192-bit | Strong |
| 256-bit | Highest (military) |

### Modes of Operation

| Mode | Description | Use |
|------|-------------|-----|
| ECB | Electronic Code Book | Not recommended |
| CBC | Cipher Block Chaining | Most common |
| CTR | Counter Mode | Parallel processing |
| GCM | Galois/Counter Mode | Authenticated encryption |

---

## 🔧 Python Example (PyCryptodome)

```python
from Crypto.Cipher import AES
from Crypto.Random import get_random_bytes
from Crypto.Util.Padding import pad, unpad
import base64

def encrypt(plaintext, key):
    iv = get_random_bytes(16)
    cipher = AES.new(key, AES.MODE_CBC, iv)
    padded = pad(plaintext.encode(), AES.block_size)
    ciphertext = cipher.encrypt(padded)
    return base64.b64encode(iv + ciphertext).decode()

def decrypt(ciphertext_b64, key):
    data = base64.b64decode(ciphertext_b64)
    iv = data[:16]
    ciphertext = data[16:]
    cipher = AES.new(key, AES.MODE_CBC, iv)
    plaintext = unpad(cipher.decrypt(ciphertext), AES.block_size)
    return plaintext.decode()

# Usage
key = get_random_bytes(32)  # 256-bit
message = "Secret message"

encrypted = encrypt(message, key)
decrypted = decrypt(encrypted, key)
```

---

## 🔧 OpenSSL CLI

```bash
# Encrypt
echo "secret" | openssl enc -aes-256-cbc -salt -out file.enc

# Decrypt
openssl enc -aes-256-cbc -d -in file.enc -out decrypted.txt
```

---

## ⚠️ Best Practices

- Use AES-256
- Always use random IV
- Use authenticated mode (GCM) when possible
- Never reuse keys for different data

---

## 📋 Comparison

| Algorithm | Key Size | Speed | Security |
|-----------|----------|-------|----------|
| AES-256 | 256-bit | Fast | Very High |
| ChaCha20 | 256-bit | Very Fast | High |
| DES | 56-bit | Fast | Low (broken) |
| 3DES | 168-bit | Slow | Medium |

---

## 🔗 Related Topics

- [Asymmetric Encryption](asymmetric-encryption.md)
- [Hashing](hashing.md)
- [TLS/SSL](tls-ssl.md)

---

[← Back to Cryptography](../README.md)