---
title: "Lab 1.4: EventBridge Event-Driven Architecture"
date: 2025-02-11
weight: 4
---

**Skills covered:** 1.1.1, 1.1.12

## Mục tiêu
- Tạo custom event bus, rules với event patterns
- Multiple targets, archive và replay events

## Bước 1: Tạo Custom Event Bus
- EventBridge → Event buses → Create → Name: `OrderEventBus`

## Bước 2: Tạo Rules
1. Rule 1: Match `order.created` → Lambda
2. Rule 2: Match `order.created` với amount > 100 → SNS
3. Rule 3: Schedule rule: Every 5 minutes → Lambda

## Bước 3: Publish Events
```python
events_client.put_events(Entries=[{
    'Source': 'com.myapp.orders',
    'DetailType': 'order.created',
    'Detail': json.dumps({'orderId': '123', 'amount': 150}),
    'EventBusName': 'OrderEventBus'
}])
```

## Bước 4: Archive & Replay
1. Create archive cho OrderEventBus
2. Replay archived events → verify Lambda triggered lại

## Kiểm tra kiến thức
- [ ] Hiểu event pattern matching syntax
- [ ] Biết default vs custom event bus
- [ ] Hiểu archive và replay use cases
