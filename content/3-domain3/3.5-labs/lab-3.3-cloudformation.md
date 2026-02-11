---
title: "Lab 3.3: CloudFormation Stack"
date: 2025-02-11
weight: 3
---

**Skills covered:** 3.3.4, 3.4.3

## Mục tiêu
- CloudFormation template với parameters, mappings, outputs
- Change sets, drift detection

## Bước 1: Template
```yaml
AWSTemplateFormatVersion: '2010-09-09'
Parameters:
  Environment:
    Type: String
    AllowedValues: [dev, staging, prod]
Mappings:
  EnvConfig:
    dev:
      InstanceType: t3.micro
    prod:
      InstanceType: t3.small
Resources:
  MyTable:
    Type: AWS::DynamoDB::Table
    Properties:
      TableName: !Sub '${Environment}-orders'
      BillingMode: PAY_PER_REQUEST
      AttributeDefinitions:
        - AttributeName: orderId
          AttributeType: S
      KeySchema:
        - AttributeName: orderId
          KeyType: HASH
Outputs:
  TableArn:
    Value: !GetAtt MyTable.Arn
    Export:
      Name: !Sub '${Environment}-OrderTableArn'
```

## Bước 2: Deploy → Change Set → Drift Detection

## Kiểm tra kiến thức
- [ ] Intrinsic functions (!Ref, !Sub, !GetAtt)
- [ ] Parameters, Mappings, Conditions, Outputs
- [ ] Change sets và drift detection
