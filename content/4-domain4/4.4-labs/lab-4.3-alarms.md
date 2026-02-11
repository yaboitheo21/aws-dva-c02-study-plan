---
title: "Lab 4.3: CloudWatch Alarms + SNS"
date: 2025-02-11
weight: 3
---

**Skills covered:** 4.1.5, 4.2.5

## Mục tiêu
- CloudWatch Alarms, SNS notifications, composite alarms

## Bước 1: SNS Topic
- Create `AlertsTopic`, subscribe email, confirm

## Bước 2: Lambda Error Alarm
- Metric: Lambda Errors > 5 trong 5 min → SNS

## Bước 3: DynamoDB Throttle Alarm
- Metric: ThrottledRequests > 0 trong 1 min → SNS

## Bước 4: Composite Alarm
- Lambda Error AND DynamoDB Throttle → only alert khi BOTH true

## Kiểm tra kiến thức
- [ ] Alarm states (OK, ALARM, INSUFFICIENT_DATA)
- [ ] Evaluation periods và datapoints
- [ ] Composite alarms
