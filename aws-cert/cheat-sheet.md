# AWS Developer Certification Cheat Sheet

Quick reference for key limits, concepts, and decision trees.

## Service Limits (Memorize These!)

### Lambda
| Limit | Value |
|-------|-------|
| Memory | 128 MB - 10,240 MB (1 MB increments) |
| Timeout | 15 minutes max |
| Deployment package (zipped) | 50 MB |
| Deployment package (unzipped) | 250 MB |
| /tmp storage | 512 MB - 10,240 MB |
| Environment variables | 4 KB total |
| Concurrent executions | 1,000 (soft limit, can increase) |

### DynamoDB
| Limit | Value |
|-------|-------|
| Item size | 400 KB max |
| Partition key length | 2,048 bytes |
| Sort key length | 1,024 bytes |
| Batch operations | 25 items or 16 MB max |
| Table name length | 3-255 characters |
| GSI per table | 20 max |
| LSI per table | 5 max |

### SQS
| Limit | Value |
|-------|-------|
| Message size | 256 KB max |
| Message retention | 4 days default (1 min - 14 days) |
| Visibility timeout | 30 sec default (0 - 12 hours) |
| FIFO throughput | 300 TPS (3,000 with batching) |
| Standard throughput | Nearly unlimited |
| Delay queue | 0 - 15 minutes |
| Long polling | 1 - 20 seconds |

### S3
| Limit | Value |
|-------|-------|
| Object size | 5 TB max |
| Single PUT | 5 GB max |
| Multipart upload (recommended) | > 100 MB |
| Bucket names | 3-63 characters, globally unique |
| Pre-signed URL expiry | Up to 7 days (IAM temp credentials) |

### API Gateway
| Limit | Value |
|-------|-------|
| Timeout | 29 seconds max |
| Payload size | 10 MB |
| Default throttle | 10,000 RPS (soft limit) |
| Burst | 5,000 requests |

### SNS
| Limit | Value |
|-------|-------|
| Message size | 256 KB |
| Topic name | 256 characters |
| SMS message | 140 bytes |

### Step Functions
| Limit | Value |
|-------|-------|
| Execution history | 25,000 events |
| Execution time (Standard) | 1 year |
| Execution time (Express) | 5 minutes |

## Quick Decision Trees

### Compute: Which Service?

```
Need compute?
├─ Event-driven / serverless → Lambda
├─ Full VM control needed → EC2
├─ Container-based
│  ├─ Want serverless → ECS with Fargate
│  └─ Need EC2 control → ECS with EC2
├─ Just deploy code (PaaS) → Elastic Beanstalk
└─ Workflow orchestration → Step Functions
```

### Storage: Which Service?

```
Need storage?
├─ Object storage / static files → S3
├─ Block storage for EC2 → EBS
├─ File system (NFS) → EFS
├─ Archive / long-term → S3 Glacier
└─ In-memory cache → ElastiCache
```

### Database: Which Service?

```
Need database?
├─ NoSQL / Key-value → DynamoDB
├─ Relational (SQL)
│  ├─ Managed → RDS
│  └─ Serverless → Aurora Serverless
├─ In-memory cache
│  ├─ Simple cache → ElastiCache Memcached
│  └─ Advanced features → ElastiCache Redis
├─ Graph → Neptune
└─ Time series → Timestream
```

### Messaging: Which Service?

```
Need messaging?
├─ Queue (async processing) → SQS
├─ Pub/Sub (fan-out) → SNS
├─ Event bus (routing) → EventBridge
├─ Streaming → Kinesis
└─ Workflow coordination → Step Functions
```

## DynamoDB Deep Dive

### When to use GSI vs LSI

**Global Secondary Index (GSI)**
- Can be created anytime
- Different partition key and optional sort key
- Eventual consistency only
- Has its own throughput

**Local Secondary Index (LSI)**
- Must be created at table creation
- Same partition key, different sort key
- Supports eventual OR strong consistency
- Shares throughput with base table

### Read Consistency

| Type | Latency | Cost | Use Case |
|------|---------|------|----------|
| Eventually Consistent | Lower | 50% cheaper | Most reads, can tolerate stale data |
| Strongly Consistent | Higher | Standard | Need latest data immediately |

### Capacity Modes

**Provisioned**
- Predictable workload
- Cost optimization with reserved capacity
- Auto-scaling available
- Pay per RCU/WCU

**On-Demand**
- Unpredictable workload
- No capacity planning
- Pay per request (more expensive)
- Instant scaling

## Lambda Integration Patterns

### Invocation Types

| Type | Use Case | How It Works |
|------|----------|--------------|
| Synchronous | API Gateway, SDK | Waits for response |
| Asynchronous | S3, SNS, EventBridge | Returns immediately, retries 2x |
| Poll-based | SQS, DynamoDB Streams, Kinesis | Lambda polls source |

### Error Handling

**Synchronous**: Return error to caller
**Asynchronous**:
- Retries 2 times
- Send to DLQ (SQS or SNS)
- Max event age: 6 hours

**Poll-based**:
- Retries until data expires
- Configure DLQ on source (SQS)
- Bisect batch on error

## IAM Policy Evaluation Logic

```
1. Deny by default
2. Evaluate all applicable policies
3. Explicit DENY → DENY (always wins)
4. Explicit ALLOW → ALLOW
5. No explicit ALLOW → DENY
```

**Policy Types Priority**:
1. Organization SCPs (deny only)
2. Resource-based policies
3. IAM permissions boundaries
4. Identity-based policies

## S3 Security Layers

```
Bucket Level:
├─ Bucket Policy (JSON, principal-based)
├─ ACL (legacy, avoid)
└─ Block Public Access (safety net)

Object Level:
├─ Object ACL
└─ Pre-signed URL (temporary access)

Encryption:
├─ In Transit: HTTPS/TLS
└─ At Rest:
   ├─ SSE-S3 (S3 managed keys)
   ├─ SSE-KMS (KMS managed keys)
   ├─ SSE-C (customer provided keys)
   └─ Client-side encryption
```

## CodeDeploy Lifecycle Hooks

### EC2/On-Premises

**In-Place Deployment**:
1. ApplicationStop
2. DownloadBundle
3. BeforeInstall
4. Install
5. AfterInstall
6. ApplicationStart
7. **ValidateService** ← Your tests here

**Blue/Green Deployment**:
1. BeforeBlockTraffic
2. BlockTraffic
3. AfterBlockTraffic
4. ApplicationStop
5. DownloadBundle
6. BeforeInstall
7. Install
8. AfterInstall
9. ApplicationStart
10. **ValidateService**
11. BeforeAllowTraffic
12. AllowTraffic
13. AfterAllowTraffic

### Lambda Deployments
- Linear: Traffic shifts in equal increments
- Canary: Test with small percentage first
- All-at-once: Immediate shift

## SQS Patterns

### Standard vs FIFO

| Feature | Standard | FIFO |
|---------|----------|------|
| Ordering | Best effort | Guaranteed |
| Delivery | At least once | Exactly once |
| Throughput | Unlimited | 300 TPS (3K batched) |
| Use case | High throughput | Order matters |

### Visibility Timeout Pattern

```
1. Message received by consumer
2. Visibility timeout starts (message hidden)
3. Consumer processes message
   ├─ Success → Delete message
   └─ Failure → Timeout expires, message reappears
```

**Best Practice**: Set timeout to 6x average processing time

## Common Exam Scenarios

### Scenario: Optimize Lambda Cold Starts
**Solutions**:
- Use Provisioned Concurrency
- Minimize deployment package size
- Use Lambda layers for dependencies
- Keep functions warm (not recommended)

### Scenario: DynamoDB Hot Partition
**Solutions**:
- Better partition key design (high cardinality)
- Add random suffix to partition key
- Use DynamoDB Accelerator (DAX)
- Switch to on-demand mode

### Scenario: Secure API with Minimal Latency
**Solutions**:
- API Gateway with Lambda Authorizer (cached)
- Cognito User Pools
- WAF for additional protection
- CloudFront for caching + TLS

### Scenario: Process Large Files from S3
**Solutions**:
- S3 event → SQS → Lambda (not direct trigger for large files)
- Use S3 Select for partial data
- Increase Lambda memory and /tmp space
- Or use EC2/ECS for very large files

### Scenario: Failed Deployments
**Debug Steps**:
1. Check CloudWatch Logs
2. Review CodeDeploy deployment logs
3. Check IAM permissions
4. Validate appspec.yml syntax
5. Check lifecycle hook scripts

## X-Ray Concepts

**Segments**: Individual service calls
**Subsegments**: Calls within segments (DB, external APIs)
**Traces**: End-to-end request path
**Annotations**: Searchable key-value pairs (indexed)
**Metadata**: Additional info (not indexed)

## Environment Variables Best Practices

| Secret Type | Storage |
|-------------|---------|
| API keys, passwords | Secrets Manager (with rotation) |
| Configuration | Parameter Store (free tier) |
| Small configs | Lambda environment vars (encrypted with KMS) |
| Large configs | S3 bucket |

## Elastic Beanstalk Deployment Policies

| Policy | Downtime | Rollback Speed | Cost |
|--------|----------|----------------|------|
| All at once | Yes | Fast | Low |
| Rolling | No (partial) | Slow | Low |
| Rolling with batch | No | Medium | Medium |
| Immutable | No | Fast | High (2x) |
| Blue/Green | No | Fastest | Highest |

## API Gateway Caching

- Cache at stage level
- TTL: 0 - 3600 seconds
- Cache size: 0.5 GB - 237 GB
- Can be invalidated per request (with proper permissions)
- Reduces backend calls and improves latency

## Key Acronyms

- **RCU**: Read Capacity Unit (4 KB strongly consistent)
- **WCU**: Write Capacity Unit (1 KB)
- **TTL**: Time to Live
- **STS**: Security Token Service
- **SCPs**: Service Control Policies
- **VTL**: Velocity Template Language (API Gateway transformations)
- **DAX**: DynamoDB Accelerator
- **ECS**: Elastic Container Service
- **ECR**: Elastic Container Registry

## Exam Keywords → Solutions

| Keyword | Likely Solution |
|---------|-----------------|
| "Least operational overhead" | Managed service, serverless |
| "Most cost-effective" | Reserved capacity, S3 lifecycle, spot instances |
| "Highly available" | Multi-AZ, multiple regions |
| "Decouple" | SQS, SNS, EventBridge |
| "Real-time" | Kinesis, WebSocket API |
| "Audit" | CloudTrail |
| "Monitor" | CloudWatch |
| "Trace" | X-Ray |
| "Secrets" | Secrets Manager, Parameter Store |
| "Temporary credentials" | STS, IAM roles |

---

Print this and keep it handy during your final review week!
