# AWS Solutions Architect Certification Cheat Sheet

Quick reference for key architectural decisions, service limits, and best practices.

## Service Limits (Memorize These!)

### EC2
| Limit | Value |
|-------|-------|
| On-Demand instances (default) | 20 per region (varies by type) |
| EBS volume size (gp3/gp2) | 16 TiB max |
| EBS volume size (io2) | 64 TiB max |
| EBS IOPS (io2) | 64,000 max |
| Instance metadata timeout | 1 second default |
| Placement group instances | No hard limit (network limited) |

### VPC
| Limit | Value |
|-------|-------|
| VPCs per region | 5 (soft limit) |
| Subnets per VPC | 200 |
| Security groups per VPC | 2,500 |
| Rules per security group | 60 inbound, 60 outbound |
| Security groups per ENI | 5 (soft limit) |
| Network ACLs per VPC | 200 |
| Rules per NACL | 20 (soft limit) |
| VPC Peering connections | 125 per VPC |
| Route tables per VPC | 200 |
| Routes per route table | 50 (non-propagated) |

### S3
| Limit | Value |
|-------|-------|
| Buckets per account | 100 (soft limit to 1,000) |
| Object size | 5 TB max |
| Single PUT | 5 GB max |
| Multipart upload parts | 10,000 max |
| Request rate | 3,500 PUT/COPY/POST/DELETE, 5,500 GET/HEAD per prefix/sec |

### ELB
| Limit | Value |
|-------|-------|
| Targets per ALB | 1,000 |
| Listeners per ALB | 50 |
| Rules per ALB | 100 |
| Connection idle timeout | 60 seconds (default, configurable) |

### RDS
| Limit | Value |
|-------|-------|
| DB instances per account | 40 |
| Read replicas per master | 5 (15 for Aurora) |
| DB instance storage | 64 TiB max (SQL Server: 16 TiB) |
| Manual snapshots | 100 per region |
| Automated backup retention | 1-35 days |

### Lambda
| Limit | Value |
|-------|-------|
| Memory | 128 MB - 10,240 MB |
| Timeout | 15 minutes max |
| Concurrent executions | 1,000 (soft limit) |
| Deployment package (zipped) | 50 MB |
| /tmp storage | 10,240 MB max |

## Quick Decision Trees

### Compute Selection

```
Need compute?
├─ Traditional app, full OS control → EC2
├─ Event-driven, serverless → Lambda
├─ Containers
│  ├─ Serverless containers → ECS/EKS with Fargate
│  ├─ Need EC2 control → ECS/EKS with EC2
│  └─ Kubernetes required → EKS
├─ Batch processing → AWS Batch
├─ Just deploy code (no infra management) → Elastic Beanstalk
└─ High-performance computing → EC2 with placement groups

When to use EC2 instance types?
├─ Balanced workload → M5 (General Purpose)
├─ CPU-intensive → C5 (Compute Optimized)
├─ Memory-intensive (in-memory DB, cache) → R5/X1 (Memory Optimized)
├─ Storage-intensive (data warehouse) → I3/D2 (Storage Optimized)
├─ Burstable (variable workload) → T3
└─ GPU workload (ML, rendering) → P3/G4 (Accelerated Computing)
```

### Storage Selection

```
Need storage?
├─ Object storage / static files → S3
├─ Block storage for EC2 → EBS
├─ Shared file system
│  ├─ Linux (NFS) → EFS
│  ├─ Windows (SMB) → FSx for Windows
│  └─ High-performance computing → FSx for Lustre
├─ Archive / compliance → S3 Glacier
├─ Hybrid cloud storage
│  ├─ Files → File Gateway
│  ├─ Volumes → Volume Gateway
│  └─ Tapes → Tape Gateway
└─ In-memory cache → ElastiCache

S3 Storage Class Selection:
├─ Frequent access → S3 Standard
├─ Infrequent access
│  ├─ Need multi-AZ → S3 Standard-IA
│  └─ OK with single AZ → S3 One Zone-IA
├─ Unknown pattern → S3 Intelligent-Tiering
├─ Archive
│  ├─ Millisecond retrieval → Glacier Instant Retrieval
│  ├─ Minutes-hours retrieval → Glacier Flexible Retrieval
│  └─ Rare access (12+ hour retrieval) → Glacier Deep Archive
```

### Database Selection

```
Need database?
├─ Relational (SQL)
│  ├─ Standard workload → RDS
│  ├─ High performance, auto-scaling → Aurora
│  ├─ Serverless + auto-scaling → Aurora Serverless
│  └─ Microsoft SQL Server with AD → RDS for SQL Server
├─ NoSQL
│  ├─ Key-value, massive scale → DynamoDB
│  ├─ Document store → DocumentDB
│  ├─ In-memory cache
│  │  ├─ Simple caching → ElastiCache Memcached
│  │  └─ Advanced features (pub/sub, persistence) → ElastiCache Redis
│  ├─ Graph relationships → Neptune
│  ├─ Time series → Timestream
│  └─ Ledger (immutable) → QLDB
├─ Data warehouse / analytics → Redshift
└─ Search → OpenSearch (formerly Elasticsearch)

High Availability for Databases:
├─ Automated failover (same region) → RDS Multi-AZ
├─ Read scaling → Read Replicas
├─ Cross-region disaster recovery → Cross-region Read Replica
└─ Global distribution → Aurora Global Database, DynamoDB Global Tables
```

### Load Balancer Selection

```
Which Load Balancer?
├─ HTTP/HTTPS traffic
│  ├─ Advanced routing (path, host, headers) → ALB
│  └─ Simple HTTP distribution → ALB
├─ TCP/UDP traffic
│  ├─ Ultra-low latency, static IP → NLB
│  └─ Millions of requests/sec → NLB
├─ Existing Classic infrastructure → CLB (legacy)
└─ Third-party virtual appliances → GWLB
```

### Networking & Connectivity

```
Connect to VPC?
├─ From internet
│  ├─ Public resources → Internet Gateway
│  └─ Private resources outbound only → NAT Gateway
├─ From on-premises
│  ├─ Over internet (encrypted) → Site-to-Site VPN
│  ├─ Dedicated, private connection → Direct Connect
│  └─ Both VPN + Direct Connect → Direct Connect with VPN backup
├─ Between VPCs
│  ├─ Two VPCs, same account → VPC Peering
│  ├─ Many VPCs, hub-and-spoke → Transit Gateway
│  └─ Cross-account → VPC Peering or Transit Gateway
├─ To AWS services (private)
│  ├─ S3, DynamoDB → VPC Gateway Endpoint (free)
│  └─ Other services → VPC Interface Endpoint (PrivateLink)
└─ From users globally → CloudFront, Global Accelerator
```

## High Availability & Disaster Recovery

### Multi-AZ Deployment Patterns

| Service | Multi-AZ Strategy |
|---------|-------------------|
| **EC2** | Auto Scaling group across multiple AZs |
| **RDS** | Enable Multi-AZ (synchronous replication) |
| **Aurora** | Automatically spans multiple AZs |
| **ELB** | Deploy to multiple AZs automatically |
| **S3** | Default: multi-AZ (except One Zone-IA) |
| **EFS** | Automatically multi-AZ |
| **ElastiCache** | Enable Multi-AZ with auto-failover |

### Disaster Recovery Strategies

| Strategy | Description | RTO | RPO | Cost |
|----------|-------------|-----|-----|------|
| **Backup & Restore** | Regular backups to S3/Glacier | Hours | Hours-Day | $ |
| **Pilot Light** | Minimal running resources in DR | 10-30 min | Minutes | $$ |
| **Warm Standby** | Scaled-down version always running | Minutes | Seconds | $$$ |
| **Multi-Site Active/Active** | Full production in multiple regions | Real-time | None | $$$$ |

**RTO** = Recovery Time Objective (how long to recover)
**RPO** = Recovery Point Objective (acceptable data loss)

## VPC Architecture Deep Dive

### Public vs Private Subnet

**Public Subnet**:
- Has route to Internet Gateway (0.0.0.0/0 → IGW)
- Resources get public IPs (if enabled)
- Use for: ALB, NAT Gateway, Bastion hosts

**Private Subnet**:
- No direct route to Internet Gateway
- Outbound internet via NAT Gateway in public subnet
- Use for: Application servers, databases

### Security Groups vs NACLs

| Feature | Security Groups | Network ACLs |
|---------|----------------|--------------|
| Level | Instance (ENI) | Subnet |
| State | Stateful | Stateless |
| Rules | Allow only | Allow and Deny |
| Processing | All rules evaluated | Rules processed in order |
| Default | Deny all inbound | Allow all |

### VPC Connectivity Options

**VPC Peering**:
- 1-to-1 connection between VPCs
- Non-transitive (must create full mesh)
- Can span regions and accounts
- No single point of failure

**Transit Gateway**:
- Hub-and-spoke model
- Supports thousands of VPCs
- Transitive routing
- Central management

## RDS vs Aurora Comparison

| Feature | RDS | Aurora |
|---------|-----|--------|
| Storage | EBS-based | Shared cluster storage |
| Read replicas | 5 max | 15 max |
| Failover time | 1-2 minutes | < 30 seconds |
| Replicas | Async | Async (can be sync for Global) |
| Backups | Automated to S3 | Continuous to S3 |
| Backtrack | No | Yes (MySQL compatible) |
| Global database | Manual cross-region replica | Native, < 1 sec replication |
| Serverless | No | Yes (Aurora Serverless) |
| Cost | $ | $$ (20% more) |

## S3 Best Practices & Features

### S3 Replication

**Cross-Region Replication (CRR)**:
- Compliance, lower latency, disaster recovery
- Async replication
- Versioning must be enabled
- Can change storage class

**Same-Region Replication (SRR)**:
- Log aggregation
- Live replication between accounts
- Disaster recovery within region

### S3 Security Layers

```
Access Control:
├─ IAM Policies (who can access from AWS side)
├─ Bucket Policies (resource-based, can grant cross-account)
├─ ACLs (legacy, not recommended)
├─ Block Public Access (account/bucket level override)
└─ Pre-signed URLs (temporary, time-limited access)

Encryption:
├─ In Transit: HTTPS/TLS
└─ At Rest:
   ├─ SSE-S3 (S3-managed keys, AES-256)
   ├─ SSE-KMS (AWS KMS managed keys, audit trail)
   ├─ SSE-C (customer-provided keys)
   └─ Client-Side Encryption
```

### S3 Performance Optimization

- **Multi-part upload**: Required for > 5 GB, recommended for > 100 MB
- **Transfer Acceleration**: Use CloudFront edge locations for faster uploads
- **Byte-range fetches**: Parallel downloads, fail-safe
- **S3 Select**: Query data without retrieving entire object
- **Prefix strategy**: Distribute requests across multiple prefixes

## Route 53 Routing Policies

| Policy | Use Case | How It Works |
|--------|----------|--------------|
| **Simple** | Single resource | Returns all values in random order |
| **Weighted** | A/B testing, gradual migration | Distribute traffic by percentage |
| **Latency** | Global users | Route to lowest latency region |
| **Failover** | Active-passive DR | Primary/secondary with health checks |
| **Geolocation** | Content localization | Route based on user location |
| **Geoproximity** | Traffic flow control | Route based on resource and user location |
| **Multi-value** | Simple load balancing | Return multiple healthy values |

## CloudFront Use Cases & Optimization

**Use Cases**:
- Static website hosting (S3 + CloudFront)
- Dynamic content acceleration
- Video streaming (on-demand, live)
- API acceleration
- Software distribution

**Cache Optimization**:
- Use cache behaviors for different URL patterns
- Set appropriate TTL (Time To Live)
- Use Origin Shield for additional caching layer
- Invalidate cache when needed (costs apply)
- Use query strings and cookies wisely

**Lambda@Edge vs CloudFront Functions**:
| Feature | CloudFront Functions | Lambda@Edge |
|---------|---------------------|-------------|
| Runtime | JavaScript | Node.js, Python |
| Triggers | Viewer request/response | All 4 triggers |
| Execution time | < 1 ms | 5-10 seconds |
| Use case | Simple transformations | Complex logic |
| Cost | Very cheap | Moderate |

## IAM Best Practices

**Principle of Least Privilege**:
- Grant minimum permissions required
- Use groups for common permission sets
- Avoid long-term access keys (use roles)
- Enable MFA for privileged users
- Use IAM Access Analyzer to validate policies

**Policy Evaluation Logic**:
1. **Explicit Deny** → Deny (always wins)
2. Organizational SCPs (boundary)
3. Resource-based policies (S3 bucket policy, etc.)
4. Permission boundaries (max permissions for IAM entity)
5. Identity-based policies (attached to user/group/role)
6. **No Explicit Allow** → Deny

**Cross-Account Access**:
1. Create IAM role in Account B
2. Define trust policy (allow Account A to assume)
3. Grant permissions in role policy
4. User in Account A assumes role with STS
5. Temporary credentials returned

## Cost Optimization Strategies

### EC2 Cost Optimization
- **Reserved Instances**: 1 or 3 year commitment (up to 75% savings)
- **Savings Plans**: Flexible commitment to compute usage
- **Spot Instances**: Up to 90% savings (interruptible)
- **Right-sizing**: Match instance type to workload
- **Auto Scaling**: Scale down during off-peak

### Storage Cost Optimization
- **S3 Lifecycle Policies**: Transition to cheaper storage classes
- **S3 Intelligent-Tiering**: Automatic cost optimization
- **EBS Snapshots**: Delete old snapshots, use lifecycle policies
- **EFS Infrequent Access**: Automatically move unused files

### Database Cost Optimization
- **Aurora Serverless**: Pay per second when active
- **RDS Reserved Instances**: Up to 60% savings
- **DynamoDB On-Demand**: Pay per request (unpredictable workloads)
- **ElastiCache Reserved Nodes**: Long-term commitment savings

### General Best Practices
- Use CloudWatch to identify unused resources
- Enable Cost Explorer and budget alerts
- Use AWS Trusted Advisor for recommendations
- Tag resources for cost allocation
- Choose appropriate regions (pricing varies)

## Migration Strategies (6 R's)

| Strategy | Description | Effort | Optimization |
|----------|-------------|--------|--------------|
| **Rehost** (Lift-and-shift) | Migrate as-is | Low | Low |
| **Replatform** (Lift-tinker-shift) | Minor optimizations | Medium | Medium |
| **Repurchase** (Drop-and-shop) | Move to SaaS | Low-Medium | High |
| **Refactor** (Re-architect) | Redesign for cloud-native | High | Highest |
| **Retire** | Decommission | Minimal | N/A |
| **Retain** (Revisit) | Keep on-premises | None | N/A |

## Common Exam Scenarios & Solutions

### Scenario: Highly Available Web Application
**Requirements**: 99.99% availability, auto-scaling
**Solution**:
- Multi-AZ ALB
- Auto Scaling group across 3+ AZs
- RDS Multi-AZ or Aurora
- ElastiCache for session store
- CloudFront for static content
- Route 53 health checks

### Scenario: Minimize Latency for Global Users
**Requirements**: Low latency worldwide
**Solution**:
- CloudFront with multiple origins
- Route 53 latency-based routing
- Aurora Global Database
- DynamoDB Global Tables
- S3 Cross-Region Replication
- Global Accelerator for static IPs

### Scenario: Secure Hybrid Cloud
**Requirements**: Extend on-premises to AWS securely
**Solution**:
- Direct Connect for dedicated connection
- Site-to-Site VPN as backup
- AWS PrivateLink for service access
- Transit Gateway for multiple VPCs
- Storage Gateway for hybrid storage
- Route 53 Resolver for DNS

### Scenario: Cost-Effective Data Archive
**Requirements**: Store 10 years of compliance data
**Solution**:
- S3 Glacier Deep Archive
- S3 Lifecycle policies
- S3 Object Lock (compliance mode)
- Cross-region replication for DR
- CloudTrail for access logging

### Scenario: Decouple Application Components
**Requirements**: Asynchronous processing, fault-tolerant
**Solution**:
- SQS for message queuing
- SNS for fan-out notifications
- DynamoDB for state management
- Lambda for event processing
- Dead Letter Queue for failed messages
- Step Functions for workflows

## Well-Architected Framework Pillars

### 1. Operational Excellence
- IaC (CloudFormation, CDK)
- Automated deployments
- Monitoring and logging (CloudWatch, X-Ray)
- Regular game days and runbooks

### 2. Security
- IAM with least privilege
- Defense in depth (security groups, NACLs, WAF)
- Encryption in transit and at rest
- Detective controls (GuardDuty, Config)
- Incident response automation

### 3. Reliability
- Multi-AZ deployments
- Auto Scaling and load balancing
- Automated backups and recovery
- Chaos engineering
- Monitor and adapt to changes

### 4. Performance Efficiency
- Right-size resources
- Use caching (CloudFront, ElastiCache)
- Serverless where appropriate
- Review and optimize regularly
- Experiment and test

### 5. Cost Optimization
- Use appropriate pricing models
- Measure and monitor costs
- Eliminate unused resources
- Right-size and scale
- Use managed services

### 6. Sustainability
- Minimize resource usage
- Use efficient architectures
- Choose optimal regions
- Maximize utilization
- Use managed services

## Exam Keywords → Solutions

| Keyword | Likely Solution |
|---------|-----------------|
| "Highly available" | Multi-AZ, multiple regions, load balancing |
| "Fault tolerant" | Auto Scaling, Multi-AZ, automated backups |
| "Most cost-effective" | Spot, Reserved, lifecycle policies, serverless |
| "Least operational overhead" | Managed services (RDS, Aurora, Lambda) |
| "Secure" | Encryption, private subnets, IAM, KMS, WAF |
| "Scalable" | Auto Scaling, DynamoDB, S3, CloudFront |
| "Low latency" | CloudFront, ElastiCache, Direct Connect |
| "Disaster recovery" | Multi-region, backups, Route 53 failover |
| "Decouple" | SQS, SNS, EventBridge |
| "Migrate" | DMS, SMS, DataSync, Snow Family |

---

**Print this and keep it handy during your final review!** Remember to think architecturally - not just what services do, but when and why to use them.
