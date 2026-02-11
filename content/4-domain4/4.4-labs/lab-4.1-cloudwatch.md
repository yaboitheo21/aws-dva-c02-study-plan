---
title: "Lab 4.1: CloudWatch Logs + Metrics + Insights"
date: 2025-02-11
weight: 1
---

**Skills covered:** 4.1.2, 4.1.3, 4.1.4, 4.2.2, 4.2.3

## Mục tiêu
- Custom metrics, Logs Insights queries, EMF, metric filters

## Bước 1: Structured Logging
```python
import json
def handler(event, context):
    print(json.dumps({
        'level': 'INFO', 'message': 'Processing order',
        'orderId': event.get('orderId'), 'requestId': context.aws_request_id
    }))
```

## Bước 2: Custom Metrics (PutMetricData)
```python
cloudwatch.put_metric_data(
    Namespace='MyApp',
    MetricData=[{'MetricName': 'OrderProcessed', 'Value': 1, 'Unit': 'Count'}]
)
```

## Bước 3: EMF
```python
print(json.dumps({
    '_aws': {
        'Timestamp': int(time.time() * 1000),
        'CloudWatchMetrics': [{'Namespace': 'MyApp', 'Dimensions': [['Service']],
            'Metrics': [{'Name': 'ProcessingTime', 'Unit': 'Milliseconds'}]}]
    },
    'Service': 'OrderService', 'ProcessingTime': 250
}))
```

## Bước 4: Logs Insights
```sql
fields @timestamp, @message
| filter @message like /ERROR/
| stats count(*) as errorCount by bin(5m)
```

## Bước 5: Metric Filter
- Filter pattern: `{ $.level = "ERROR" }` → Metric: ErrorCount

## Kiểm tra kiến thức
- [ ] EMF vs PutMetricData
- [ ] Logs Insights query syntax
- [ ] Metric filters
