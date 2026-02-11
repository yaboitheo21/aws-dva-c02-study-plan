---
title: "Lab 2.2: IAM Roles + STS AssumeRole"
date: 2025-02-11
weight: 2
---

**Skills covered:** 2.1.3, 2.1.4, 2.1.5, 2.1.6

## Mục tiêu
- Tạo IAM Role với trust policy, AssumeRole từ Lambda

## Bước 1: Tạo Target Role
- Trust policy: Allow Lambda execution role to assume
- Permissions: S3 read-only

## Bước 2: Lambda AssumeRole
```python
sts = boto3.client('sts')
response = sts.assume_role(
    RoleArn='arn:aws:iam::123456789012:role/S3ReadRole',
    RoleSessionName='LambdaSession'
)
credentials = response['Credentials']
s3 = boto3.client('s3',
    aws_access_key_id=credentials['AccessKeyId'],
    aws_secret_access_key=credentials['SecretAccessKey'],
    aws_session_token=credentials['SessionToken']
)
```

## Bước 3: Verify
1. Lambda WITHOUT AssumeRole → Access Denied
2. Lambda WITH AssumeRole → S3 access works
3. Check CloudTrail: AssumeRole event

## Kiểm tra kiến thức
- [ ] Trust policy vs permissions policy
- [ ] Temporary credentials lifecycle
- [ ] Cross-account access pattern
