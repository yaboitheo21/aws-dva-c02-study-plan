---
title: "Lab 1.5: DynamoDB GSI/LSI + Query vs Scan"
date: 2025-02-11
weight: 5
---

**Skills covered:** 1.3.1, 1.3.2, 1.3.3, 1.3.4

## Mục tiêu
- Tạo table với GSI và LSI
- So sánh Query vs Scan performance

## Bước 1: Tạo Table với Indexes
- Table: `Products`, PK: `category`, SK: `productId`
- LSI: `category-price-index` (SK: `price`)
- GSI: `brand-index` (PK: `brand`, SK: `createdAt`)

## Bước 2: Load 100+ Sample Items
- BatchWriteItem với diverse categories, brands, prices

## Bước 3: Query vs Scan
1. Query by category → nhanh, ít RCU
2. Scan toàn bộ table → chậm, nhiều RCU
3. So sánh ConsumedCapacity

## Bước 4: Index Queries
1. Query LSI: Products sorted by price
2. Query GSI: Products by brand
3. Strongly consistent trên LSI ✅ vs GSI ❌

## Bước 5: FilterExpression
- Query + FilterExpression → observe RCU **KHÔNG giảm**

## Kiểm tra kiến thức
- [ ] GSI vs LSI khi nào dùng
- [ ] FilterExpression không giảm RCU
- [ ] GSI chỉ eventually consistent
