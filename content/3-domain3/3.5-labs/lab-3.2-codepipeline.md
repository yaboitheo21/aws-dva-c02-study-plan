---
title: "Lab 3.2: CodePipeline CI/CD"
date: 2025-02-11
weight: 2
---

**Skills covered:** 3.4.6, 3.4.7, 3.4.9

## Mục tiêu
- Tạo CI/CD pipeline: Source → Build → Deploy

## Bước 1: Source Stage
- CodeCommit repo hoặc GitHub connection

## Bước 2: Build Stage — buildspec.yml
```yaml
version: 0.2
phases:
  install:
    runtime-versions:
      python: 3.12
  build:
    commands:
      - sam build
      - sam package --s3-bucket $S3_BUCKET --output-template-file packaged.yaml
artifacts:
  files:
    - packaged.yaml
```

## Bước 3: Deploy Stage
- CloudFormation deploy action → packaged.yaml

## Bước 4: Test
- Push code change → pipeline triggers → verify deployment

## Kiểm tra kiến thức
- [ ] Pipeline stages và actions
- [ ] buildspec.yml structure
- [ ] Artifact passing between stages
