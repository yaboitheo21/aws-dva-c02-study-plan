---
title: "Lab 3.6: API Gateway Stages + Variables"
date: 2025-02-11
weight: 6
---

**Skills covered:** 3.2.3, 3.3.5, 3.4.2, 3.4.10

## Mục tiêu
- Multiple stages (dev, prod), stage variables, canary deployment

## Bước 1: Lambda Versions + Aliases
- v1, v2 + aliases: `dev` → $LATEST, `prod` → v1

## Bước 2: Stage Variables
- Stage `dev`: `lambdaAlias=dev`, `tableName=dev-orders`
- Stage `prod`: `lambdaAlias=prod`, `tableName=prod-orders`
- Integration: `arn:aws:lambda:...:my-function:${stageVariables.lambdaAlias}`

## Bước 3: Test
- dev endpoint → dev Lambda alias
- prod endpoint → prod Lambda alias

## Bước 4: Canary
- Prod stage → Enable canary 10% → deploy → monitor → promote

## Kiểm tra kiến thức
- [ ] Stage variables use cases
- [ ] Canary trên API Gateway
- [ ] Custom domain mapping
