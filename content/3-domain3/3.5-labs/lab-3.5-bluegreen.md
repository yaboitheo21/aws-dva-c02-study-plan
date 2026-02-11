---
title: "Lab 3.5: Blue/Green with CodeDeploy"
date: 2025-02-11
weight: 5
---

**Skills covered:** 3.4.5, 3.4.8, 3.4.11

## Mục tiêu
- Lambda blue/green deployment, traffic shifting, automatic rollback

## Bước 1: SAM Template
```yaml
Resources:
  MyFunction:
    Type: AWS::Serverless::Function
    Properties:
      Handler: app.handler
      Runtime: python3.12
      AutoPublishAlias: live
      DeploymentPreference:
        Type: Canary10Percent5Minutes
        Alarms:
          - !Ref MyAlarm
```

## Bước 2: Deploy v1 → Deploy v2 (traffic shifting)
- 10% traffic → v2, 90% → v1 → after 5 min → 100% v2

## Bước 3: Rollback
- CloudWatch alarm (error > 5%) → deploy buggy v3 → auto rollback

## Kiểm tra kiến thức
- [ ] Canary vs Linear vs AllAtOnce
- [ ] Automatic rollback config
- [ ] Lambda alias traffic shifting
