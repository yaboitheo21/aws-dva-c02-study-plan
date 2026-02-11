---
title: "Lab 4.4: Lambda Performance Tuning"
date: 2025-02-11
weight: 4
---

**Skills covered:** 4.3.1, 4.3.2, 4.3.3, 4.3.7

## Mục tiêu
- Tối ưu Lambda memory/CPU, giảm cold start, connection reuse

## Bước 1: Baseline (128MB, 100 invocations)

## Bước 2: Memory Optimization
- 256MB → 512MB → 1024MB → so sánh Duration

## Bước 3: Cold Start Optimization
```python
# GOOD: Outside handler
dynamodb = boto3.resource('dynamodb')
table = dynamodb.Table('Orders')

def handler(event, context):
    return table.get_item(Key={'id': event['id']})
```

## Bước 4: Provisioned Concurrency
- Publish version → alias → provisioned concurrency: 5 → no cold starts

## Kiểm tra kiến thức
- [ ] Memory-CPU relationship
- [ ] Cold start mitigation
- [ ] Reserved vs provisioned concurrency
