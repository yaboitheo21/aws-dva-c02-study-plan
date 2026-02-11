---
title: "Lab 1.2: Lambda trong VPC + DynamoDB"
date: 2025-02-11
weight: 2
---

**Skills covered:** 1.2.1, 1.2.2, 1.2.5, 1.3.4, 1.3.6

## Mục tiêu
- Đặt Lambda function trong VPC
- Tạo VPC Endpoint cho DynamoDB
- CRUD operations với DynamoDB

## Bước 1: Tạo DynamoDB Table
- Table name: `Orders`
- Partition key: `orderId` (String), Sort key: `createdAt` (String)
- Capacity: On-demand

## Bước 2: Tạo VPC Endpoint
1. VPC → Endpoints → Create
2. Service: `com.amazonaws.{region}.dynamodb`
3. Type: **Gateway**
4. Associate với route table

## Bước 3: Tạo Lambda trong VPC
1. Create Lambda function
2. Configuration → VPC: Chọn VPC, private subnets, security group
3. Execution role: Thêm DynamoDB + VPC permissions

## Bước 4: Code CRUD Operations
```python
import boto3
dynamodb = boto3.resource('dynamodb')
table = dynamodb.Table('Orders')

def handler(event, context):
    # PutItem
    table.put_item(Item={'orderId': '001', 'createdAt': '2025-01-01', 'status': 'new'})
    
    # GetItem
    response = table.get_item(Key={'orderId': '001', 'createdAt': '2025-01-01'})
    
    # Query
    response = table.query(KeyConditionExpression=Key('orderId').eq('001'))
    
    return {'statusCode': 200, 'body': 'OK'}
```

## Bước 5: Verify
1. Test Lambda → Check DynamoDB items
2. Xóa VPC Endpoint → Test lại → **Expect timeout**
3. Thêm lại VPC Endpoint → Test OK

## Kiểm tra kiến thức
- [ ] Hiểu tại sao Lambda trong VPC cần VPC Endpoint hoặc NAT Gateway
- [ ] Biết Gateway vs Interface VPC Endpoint
- [ ] Thành thạo DynamoDB CRUD operations
