---
title: "Lab 4.2: X-Ray Tracing"
date: 2025-02-11
weight: 2
---

**Skills covered:** 4.1.2, 4.2.4, 4.2.6

## Mục tiêu
- Enable X-Ray, add annotations/metadata, analyze traces

## Bước 1: Enable X-Ray
- Lambda: Active Tracing ON
- API Gateway: Stage → X-Ray ON
- Role: AWSXRayDaemonWriteAccess

## Bước 2: Instrument Code
```python
from aws_xray_sdk.core import xray_recorder, patch_all
patch_all()

def handler(event, context):
    xray_recorder.current_subsegment().put_annotation('userId', 'user-123')
    xray_recorder.current_subsegment().put_metadata('details', {'amount': 100})
    with xray_recorder.in_subsegment('ProcessOrder'):
        pass  # business logic
```

## Bước 3: Analyze
- Service map → Traces → Filter by annotation → Find bottlenecks

## Bước 4: Sampling Rules
- 10% for /health, 100% for errors

## Kiểm tra kiến thức
- [ ] Annotations (indexed) vs Metadata (not indexed)
- [ ] Sampling rules
- [ ] Service map interpretation
