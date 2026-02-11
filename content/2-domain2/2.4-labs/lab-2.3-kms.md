---
title: "Lab 2.3: KMS Encryption"
date: 2025-02-11
weight: 3
---

**Skills covered:** 2.2.1, 2.2.3, 2.2.4, 2.2.7

## Mục tiêu
- Tạo KMS key, encrypt/decrypt, envelope encryption, key rotation

## Bước 1: Tạo KMS Key
- Symmetric, key policy allow Lambda role, enable auto rotation

## Bước 2: Direct Encryption (≤ 4KB)
```python
kms = boto3.client('kms')
encrypted = kms.encrypt(KeyId='alias/my-key', Plaintext=b'secret data')
decrypted = kms.decrypt(CiphertextBlob=encrypted['CiphertextBlob'])
```

## Bước 3: Envelope Encryption (> 4KB)
```python
data_key = kms.generate_data_key(KeyId='alias/my-key', KeySpec='AES_256')
# Encrypt data locally with plaintext key
# Store encrypted_key + encrypted_data
# Delete plaintext key from memory
```

## Bước 4: S3 SSE-KMS
- Upload object với SSE-KMS → download → auto decrypt
- Check CloudTrail: GenerateDataKey, Decrypt events

## Kiểm tra kiến thức
- [ ] Direct vs envelope encryption
- [ ] KMS API quota limits
- [ ] SSE-S3 vs SSE-KMS vs SSE-C
