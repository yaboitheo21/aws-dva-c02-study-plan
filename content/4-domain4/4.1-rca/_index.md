---
title: "Root Cause Analysis"
date: 2025-02-11
weight: 1
pre: "<b>4.1 </b>"
---

### Task 4.1: Assist in a root cause analysis

Root cause analysis là critical cho troubleshooting, đặc biệt với distributed services.

## Quy trình RCA

1. **Monitor KPIs** - Theo dõi key performance indicators để đảm bảo resources hoạt động tốt
2. **Identify Components** - Xác định components nào ảnh hưởng performance hoặc efficiency
3. **Build Alarms** - Tạo alarms và notifications để proactively và automatically xử lý performance issues
4. **Incident Response** - Xác định metrics nào hữu ích trong việc identify root cause
5. **Add Visibility** - Tạo dashboards để tăng visibility vào performance

## AWS Services cho RCA

### Full Application Performance
- **AWS X-Ray** - Debug distributed applications, understand underlying services performance, identify root cause

### API Endpoints Monitoring
- **CloudWatch Synthetics** - Monitor API endpoints

### End-to-End View
- **CloudWatch ServiceLens** - End-to-end view của application

### Log Analytics
- **CloudWatch Logs Insights** - Search và analyze logs
- **Amazon OpenSearch** - Advanced log analytics
- **Amazon Athena** - Query logs trong S3
- **Amazon Kinesis** - Real-time log analysis

## Skills 4.1.1 → 4.1.7

Debug code, interpret metrics/logs/traces, query logs, custom metrics (EMF), dashboards, deployment failures.

{{% children %}}
