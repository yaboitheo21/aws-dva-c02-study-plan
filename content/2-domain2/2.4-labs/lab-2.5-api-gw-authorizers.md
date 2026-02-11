---
title: "Lab 2.5: API Gateway Authorizers"
date: 2025-02-11
weight: 5
---

**Skills covered:** 2.1.1, 2.1.2, 2.1.6, 2.1.7

## Mục tiêu
- So sánh 3 loại authorizers: IAM, Lambda, Cognito

## Bước 1: IAM Authorizer
- Method → Authorization: AWS_IAM
- Test với SigV4 signed request

## Bước 2: Lambda Authorizer (Token-based)
```python
def handler(event, context):
    token = event['authorizationToken']
    if validate_token(token):
        return generate_policy('user', 'Allow', event['methodArn'])
    return generate_policy('user', 'Deny', event['methodArn'])
```
- Token source: Authorization header, Caching: 300s

## Bước 3: Cognito Authorizer
- Tạo Cognito authorizer → test với JWT token

## So sánh

| | IAM | Lambda | Cognito |
|---|---|---|---|
| Use case | AWS services, internal | Custom logic | User auth |
| Token | SigV4 | Custom | JWT |
| Caching | No | Yes | Yes |

## Kiểm tra kiến thức
- [ ] Khi nào dùng loại authorizer nào
- [ ] Lambda authorizer caching
- [ ] Policy document format
