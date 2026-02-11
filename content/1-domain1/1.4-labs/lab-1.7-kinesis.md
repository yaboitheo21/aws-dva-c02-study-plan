---
title: "Lab 1.7: Kinesis Data Streams + Lambda"
date: 2025-02-11
weight: 7
---

**Skills covered:** 1.1.10, 1.2.7

## Mục tiêu
- Tạo Kinesis Data Stream, producer + Lambda consumer

## Bước 1: Tạo Kinesis Data Stream
- Stream name: `ClickStream`, Capacity mode: On-demand

## Bước 2: Producer
```python
kinesis.put_record(
    StreamName='ClickStream',
    Data=json.dumps({'userId': 'u1', 'page': '/home'}),
    PartitionKey='u1'
)
```

## Bước 3: Consumer Lambda
- Trigger: Kinesis → ClickStream
- Batch size: 100, Starting position: LATEST
- Decode base64, parse JSON

## Bước 4: Error Handling
- Bisect batch on error, max retry: 3
- On-failure destination: SQS DLQ

## Kiểm tra kiến thức
- [ ] Partition key và shard distribution
- [ ] Batch size và error handling config
- [ ] Kinesis vs SQS use cases
