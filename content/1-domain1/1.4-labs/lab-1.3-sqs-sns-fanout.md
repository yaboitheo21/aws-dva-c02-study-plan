---
title: "Lab 1.3: SQS + SNS Fan-out Pattern"
date: 2025-02-11
weight: 3
---

**Skills covered:** 1.1.1, 1.1.3, 1.1.4, 1.1.8

## Mục tiêu
- Implement fan-out pattern: SNS → multiple SQS queues
- Lambda consumers cho mỗi queue
- Dead-letter queue handling

## Bước 1: Tạo SNS Topic
- SNS → Create topic → Standard → Name: `OrderEvents`

## Bước 2: Tạo SQS Queues
1. `OrderProcessing` (Standard)
2. `OrderNotification` (Standard)
3. `OrderAnalytics` (Standard)
4. `OrderProcessing-DLQ` (maxReceiveCount: 3)

## Bước 3: Subscribe Queues to SNS
- SNS → Subscriptions → Protocol: SQS → chọn từng queue
- Cấu hình SQS access policy cho SNS

## Bước 4: Tạo Lambda Consumers
- Lambda cho OrderProcessing, OrderNotification, OrderAnalytics
- Event source mapping: SQS → Lambda

## Bước 5: Test
1. Publish message to SNS topic
2. Verify tất cả 3 Lambda functions được trigger
3. Tạo Lambda cố tình throw error → sau 3 retries → message vào DLQ

## Kiểm tra kiến thức
- [ ] Hiểu fan-out pattern và use cases
- [ ] Biết cấu hình SQS access policy cho SNS
- [ ] Hiểu visibility timeout và DLQ
