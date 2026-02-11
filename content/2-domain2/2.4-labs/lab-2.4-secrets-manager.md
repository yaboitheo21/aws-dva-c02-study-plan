---
title: "Lab 2.4: Secrets Manager"
date: 2025-02-11
weight: 4
---

**Skills covered:** 2.3.2, 2.3.3

## Mục tiêu
- Store DB credentials, Lambda đọc secrets, automatic rotation

## Bước 1: Tạo Secret
- Type: Credentials for RDS database
- Secret name: `prod/myapp/rds`

## Bước 2: Lambda đọc Secret
```python
secrets = boto3.client('secretsmanager')
response = secrets.get_secret_value(SecretId='prod/myapp/rds')
credentials = json.loads(response['SecretString'])
```

## Bước 3: Caching
- Dùng AWS Secrets Manager caching library → giảm API calls

## Bước 4: Rotation (Optional)
- Enable automatic rotation, interval: 30 days

## Kiểm tra kiến thức
- [ ] Secrets Manager vs SSM Parameter Store
- [ ] Caching best practices
- [ ] Rotation mechanism
