---
title: "Lab 2.1: Cognito User Pool"
date: 2025-02-11
weight: 1
---

**Skills covered:** 2.1.1, 2.1.2, 2.1.7

## Mục tiêu
- Tạo Cognito User Pool, App Client
- Sign-up, sign-in, verify JWT tokens

## Bước 1: Tạo User Pool
- Sign-in: Email, Password policy: Min 8 chars, MFA: Optional

## Bước 2: App Client
- No client secret (public apps), OAuth: Authorization code grant, Hosted UI

## Bước 3: Sign-up & Sign-in
1. Hosted UI → Sign up → Verify email → Sign in
2. Receive tokens (ID, Access, Refresh)
3. Decode JWT tại jwt.io → inspect claims

## Bước 4: API Gateway + Cognito Authorizer
1. Authorizers → Create Cognito authorizer
2. Request without token → 401
3. Request with valid token → 200

## Kiểm tra kiến thức
- [ ] ID token vs Access token vs Refresh token
- [ ] Cognito authorizer trong API Gateway
- [ ] OAuth 2.0 flows
