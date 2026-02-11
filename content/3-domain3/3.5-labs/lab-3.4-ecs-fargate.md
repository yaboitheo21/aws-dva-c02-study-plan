---
title: "Lab 3.4: ECS Fargate Deployment"
date: 2025-02-11
weight: 4
---

**Skills covered:** 3.1.1, 3.1.4, 3.4.5

## Mục tiêu
- Build Docker image → push ECR → deploy ECS Fargate

## Bước 1: Dockerfile
```dockerfile
FROM python:3.12-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
EXPOSE 8080
CMD ["python", "app.py"]
```

## Bước 2: Push to ECR
```bash
aws ecr create-repository --repository-name my-app
docker build -t my-app .
docker tag my-app:latest {account}.dkr.ecr.{region}.amazonaws.com/my-app:v1
docker push {account}.dkr.ecr.{region}.amazonaws.com/my-app:v1
```

## Bước 3: ECS Setup
- Cluster (Fargate), Task definition (CPU 256, Memory 512), Service (desired: 2, ALB)

## Bước 4: Deploy Update
- Build v2 → push → update task definition → update service → rolling update

## Kiểm tra kiến thức
- [ ] Task definition components
- [ ] Fargate vs EC2 launch type
- [ ] Rolling update trong ECS
