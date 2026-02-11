---
title: "Lab 4.5: CloudFront Caching"
date: 2025-02-11
weight: 5
---

**Skills covered:** 4.3.5, 4.3.6

## Mục tiêu
- CloudFront distribution, cache policies, cache based on headers

## Bước 1: S3 Origin
- S3 bucket + CloudFront distribution + OAC

## Bước 2: Cache Policy
- Default: CachingOptimized (TTL 24h)
- Custom: Cache based on Accept-Language header

## Bước 3: API Gateway Origin
- /api/* → API Gateway, CachingDisabled

## Bước 4: Cache Invalidation
- Update S3 → create invalidation `/*` → verify

## Bước 5: Monitor
- Cache hit ratio metrics → optimize TTL

## Kiểm tra kiến thức
- [ ] Cache policy vs origin request policy
- [ ] Cache invalidation cost/timing
- [ ] OAC vs OAI
