---
title: "Domain 4: Troubleshooting and Optimization"
date: 2025-02-11
weight: 4
chapter: true
pre: "<b>4. </b>"
---

### Domain 4

# Troubleshooting and Optimization (24%)

Domain về giám sát, xử lý sự cố và tối ưu hiệu năng. Domain này chiếm **24% nội dung thi**, tương đương khoảng **15 câu hỏi**.

## Tổng quan

Để duy trì operational excellence, bạn phải:
- Thường xuyên đánh giá và ưu tiên cải tiến
- Giám sát hiệu năng để phát hiện suy giảm và khắc phục nhanh
- Định nghĩa, thu thập và phân tích metrics, logs, traces để có tầm nhìn về workload events

## AWS Services cho Observability & Monitoring

- **AWS CloudTrail** - API audit logs
- **Amazon CloudWatch** - Metrics, logs, alarms, dashboards
- **AWS X-Ray** - Distributed tracing
- **Amazon Managed Grafana** - Visualization
- **Amazon Managed Service for Prometheus** - Metrics collection
- **Amazon OpenSearch** - Log analytics
- **EventBridge, State Manager, SNS** - Event routing, notifications

## 3 Task Statements

### Task 4.1: Assist in a root cause analysis
- Debug code để identify defects
- Interpret application metrics, logs, traces
- Query logs để tìm relevant data
- Implement custom metrics (CloudWatch EMF)
- Review application health bằng dashboards và insights
- Troubleshoot deployment failures bằng service output logs

### Task 4.2: Instrument code for observability
- Implement code emit custom metrics
- Add annotations cho tracing services
- Implement notification alerts cho specific actions
- Implement tracing bằng AWS services và tools
- Implement effective logging strategy để record application behavior và state

### Task 4.3: Optimize applications
- Profile application performance
- Determine minimum memory và compute power
- Use subscription filter policies để optimize messaging
- Cache content based on request headers

### Nội dung

{{% children depth="2" %}}
