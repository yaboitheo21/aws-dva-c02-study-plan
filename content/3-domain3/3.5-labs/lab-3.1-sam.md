---
title: "Lab 3.1: SAM Deploy Lambda + API Gateway"
date: 2025-02-11
weight: 1
---

**Skills covered:** 3.1.1, 3.1.2, 3.3.4, 3.4.1

## Mục tiêu
- Tạo SAM project, deploy Lambda + API Gateway, test locally

## Bước 1: Init
```bash
sam init --runtime python3.12 --name my-api --app-template hello-world
```

## Bước 2: template.yaml
```yaml
AWSTemplateFormatVersion: '2010-09-09'
Transform: AWS::Serverless-2016-10-31
Resources:
  MyFunction:
    Type: AWS::Serverless::Function
    Properties:
      Handler: app.lambda_handler
      Runtime: python3.12
      Events:
        Api:
          Type: Api
          Properties:
            Path: /items
            Method: get
```

## Bước 3: Test Locally
```bash
sam local invoke MyFunction -e events/event.json
sam local start-api
curl http://localhost:3000/items
```

## Bước 4: Deploy
```bash
sam build
sam deploy --guided
```

## Kiểm tra kiến thức
- [ ] SAM template syntax
- [ ] sam build → sam deploy workflow
- [ ] samconfig.toml
