---
title: "Lab 1.1: API Gateway + Lambda REST API"
date: 2025-02-11
weight: 1
---

**Skills covered:** 1.1.6, 1.1.9, 1.2.2, 1.2.5

## Mục tiêu
- Tạo Lambda function xử lý CRUD operations
- Tạo REST API với API Gateway
- Cấu hình proxy integration
- Test với curl/Postman

## Bước 1: Tạo Lambda Function
1. AWS Console → Lambda → Create function
2. Runtime: Python 3.12 hoặc Node.js 20.x
3. Tạo handler xử lý GET, POST, PUT, DELETE
4. Cấu hình: Memory 128MB, Timeout 30s

## Bước 2: Tạo REST API
1. API Gateway → Create API → REST API
2. Create Resource: `/items`
3. Create Methods: GET, POST, PUT, DELETE
4. Integration type: **Lambda Proxy Integration**
5. Deploy API → Create stage `dev`

## Bước 3: Test
```bash
# GET
curl -X GET https://{api-id}.execute-api.{region}.amazonaws.com/dev/items

# POST
curl -X POST -d '{"name":"test"}' https://{api-id}.execute-api.{region}.amazonaws.com/dev/items
```

## Bước 4: Request Validation
1. Tạo Model (JSON Schema) cho request body
2. Tạo Request Validator
3. Test với invalid payload → expect 400 error

## Kiểm tra kiến thức
- [ ] Hiểu proxy vs non-proxy integration
- [ ] Biết cách đọc event object trong Lambda
- [ ] Biết format response cho API Gateway proxy integration
- [ ] Hiểu request validation flow
