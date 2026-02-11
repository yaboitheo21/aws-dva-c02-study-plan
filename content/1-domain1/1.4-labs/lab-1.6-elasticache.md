---
title: "Lab 1.6: ElastiCache Redis Session Store"
date: 2025-02-11
weight: 6
---

**Skills covered:** 1.1.2, 1.3.8

## Mục tiêu
- Tạo ElastiCache Redis cluster
- Session management + caching strategies

## Bước 1: Tạo ElastiCache Redis
- Node type: cache.t3.micro, VPC, security group (port 6379)

## Bước 2: Lambda kết nối Redis
- Lambda trong cùng VPC, security group allow outbound 6379

## Bước 3: Session Management
```python
# Login → Store session
redis.set(f"session:{session_id}", json.dumps(user_data), ex=3600)

# Request → Check session
data = redis.get(f"session:{session_id}")

# Logout → Delete
redis.delete(f"session:{session_id}")
```

## Bước 4: Lazy Loading + TTL
1. Check cache → miss → query DynamoDB → write cache (TTL 5min)
2. First request: cache miss, second request: cache hit

## Kiểm tra kiến thức
- [ ] Redis vs Memcached use cases
- [ ] Lazy loading pattern
- [ ] Stateless architecture với external session store
