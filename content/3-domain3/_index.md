---
title: "Domain 3: Deployment"
date: 2025-02-11
weight: 3
chapter: true
pre: "<b>3. </b>"
---

### Domain 3

# Deployment (20%)

Domain về triển khai ứng dụng, CI/CD, và Infrastructure as Code. Domain này chiếm **20% nội dung thi**, tương đương khoảng **13 câu hỏi**.

## Tổng quan

Phần quan trọng của application build là thiết kế **scalable, efficient, và cost-effective deployment solution**.

Deployment solutions bao gồm:
- Cách **update application version**
- Cách **manage supporting infrastructure** throughout complete application lifecycle

### Deployment Lifecycle Factors

- **Resource provisioning** - Tạo và quản lý resources
- **Configuration management** - Quản lý cấu hình
- **Application deployment** - Triển khai ứng dụng
- **Software updates** - Cập nhật phần mềm
- **Monitoring** - Giám sát
- **Access control** - Kiểm soát truy cập

### AWS Deployment Services

AWS provides services cho management capabilities của application lifecycle:
- Có thể dùng **standalone** hoặc **combined**
- Balance giữa **manual management** và **AWS managed resources**
- Giúp build và deliver applications **rapidly và reliably**

## 4 Task Statements

### Task 3.1: Prepare application artifacts to be deployed to AWS
- Manage dependencies của code module trong package
- Organize files và directory structure cho deployment
- Use code repositories trong deployment environments
- Apply application requirements cho resources
- Access application configuration data

### Task 3.2: Test applications in development environments
- Test deployed code bằng AWS services và tools
- Perform mock integration cho APIs
- Resolve integration dependencies
- Test applications bằng development endpoints
- Deploy application stack updates to existing environments

### Task 3.3: Automate deployment testing
- Create application test events
- Deploy API resources to various environments
- Create application environments với approved versions cho integration testing
- Implement và deploy Infrastructure as Code (IaC) templates
- Manage environments trong individual AWS services

### Task 3.4: Deploy code by using AWS CI/CD services
- Update existing IaC templates
- Manage application environments bằng AWS services
- Deploy application version bằng deployment strategies
- Commit code to repository to invoke build, test, deployment actions
- Use orchestrated workflows to deploy code to different environments
- Perform application rollbacks bằng existing deployment strategies
- Use labels và branches cho version và release management
- Use existing runtime configurations to create dynamic deployments

### Nội dung

{{% children depth="2" %}}
