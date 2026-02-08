# AWS Certified Solutions Architect - Associate Study Guide

Study materials and resources for preparing for the AWS Certified Solutions Architect - Associate (SAA-C03) exam.

## Exam Overview

- **Exam Code**: SAA-C03
- **Duration**: 130 minutes
- **Format**: 65 questions (multiple choice and multiple response)
- **Passing Score**: 720/1000
- **Cost**: $150 USD
- **Validity**: 3 years

## Exam Domains

| Domain | Weight |
|--------|--------|
| Design Secure Architectures | 30% |
| Design Resilient Architectures | 26% |
| Design High-Performing Architectures | 24% |
| Design Cost-Optimized Architectures | 20% |

## Study Timeline

**Recommended: 6-8 weeks** (12-15 hours/week)

- **Weeks 1-2**: Core services (EC2, VPC, S3, IAM)
- **Weeks 3-4**: Databases, storage, and content delivery
- **Weeks 5-6**: High availability, disaster recovery, and migration
- **Weeks 7-8**: Practice exams and review weak areas

## Core Services to Master

### Compute

- **EC2** - Virtual servers (CRITICAL)
  - Instance types and families (C5, M5, R5, T3, etc.)
  - Pricing models (On-Demand, Reserved, Spot, Savings Plans)
  - Placement groups (Cluster, Spread, Partition)
  - Instance store vs EBS
  - Auto Scaling groups and launch templates
  - Elastic Load Balancing (ALB, NLB, GWLB, CLB)
- **Lambda** - Serverless compute
  - Use cases and limitations
  - Integration with other services
  - Cold starts and performance optimization
- **ECS/EKS** - Container orchestration
  - Fargate vs EC2 launch types
  - Service discovery
- **Elastic Beanstalk** - Platform as a Service
  - Deployment strategies
  - Environment configurations

### Storage

- **S3** - Object storage (CRITICAL)
  - Storage classes (Standard, IA, One Zone-IA, Glacier, Deep Archive)
  - Lifecycle policies
  - Versioning and MFA Delete
  - Replication (CRR, SRR)
  - Encryption (SSE-S3, SSE-KMS, SSE-C)
  - Access points and Object Lambda
  - S3 Transfer Acceleration
  - Static website hosting
- **EBS** - Block storage
  - Volume types (gp3, gp2, io2, io1, st1, sc1)
  - Snapshots and lifecycle
  - RAID configurations
  - Encryption
- **EFS** - Elastic File System
  - Performance modes (General Purpose, Max I/O)
  - Throughput modes (Bursting, Provisioned)
  - Storage classes (Standard, IA)
  - Mount targets and Multi-AZ
- **FSx** - Managed file systems
  - FSx for Windows File Server
  - FSx for Lustre (HPC workloads)
- **Storage Gateway** - Hybrid cloud storage
  - File Gateway, Volume Gateway, Tape Gateway
  - Use cases for on-premises integration

### Databases

- **RDS** - Relational Database Service (CRITICAL)
  - Multi-AZ vs Read Replicas
  - Backup and restore (automated, snapshots)
  - Database engines (MySQL, PostgreSQL, Oracle, SQL Server, MariaDB)
  - Parameter groups and option groups
  - Enhanced monitoring
- **Aurora** - AWS managed MySQL/PostgreSQL
  - Aurora Serverless
  - Global Database
  - Read replicas (up to 15)
  - Backtrack feature
- **DynamoDB** - NoSQL database
  - Partition keys and sort keys
  - Global tables
  - DAX (DynamoDB Accelerator)
  - On-demand vs provisioned capacity
- **ElastiCache** - In-memory caching
  - Redis vs Memcached
  - Cluster modes
  - Use cases (session store, caching layer)
- **Redshift** - Data warehousing
  - Columnar storage
  - Redshift Spectrum
  - Distribution styles
- **DocumentDB** - MongoDB-compatible
- **Neptune** - Graph database
- **QLDB** - Quantum Ledger Database

### Networking & Content Delivery

- **VPC** - Virtual Private Cloud (CRITICAL)
  - Subnets (public, private, isolated)
  - Route tables
  - Internet Gateway (IGW)
  - NAT Gateway vs NAT Instance
  - VPC Peering
  - Transit Gateway
  - VPN (Site-to-Site, Client VPN)
  - Direct Connect
  - VPC Endpoints (Gateway, Interface)
  - Security Groups vs NACLs
  - VPC Flow Logs
- **Route 53** - DNS service
  - Routing policies (Simple, Weighted, Latency, Failover, Geolocation, Geoproximity, Multi-value)
  - Health checks
  - Domain registration
  - DNSSEC
- **CloudFront** - CDN
  - Origins (S3, EC2, ALB, custom)
  - Edge locations and Regional Edge Caches
  - Cache behaviors and TTL
  - Origin Shield
  - Lambda@Edge and CloudFront Functions
  - Signed URLs and cookies
- **API Gateway** - API management
  - REST, HTTP, WebSocket APIs
  - Caching and throttling
  - Integration types
- **AWS Global Accelerator** - Network performance
  - Static anycast IPs
  - Health checks and traffic dial

### Security & Identity

- **IAM** - Identity and Access Management (CRITICAL)
  - Users, groups, roles, policies
  - Policy types (managed, inline, resource-based)
  - Permission boundaries
  - Service Control Policies (SCPs)
  - IAM Access Analyzer
  - Cross-account access
- **KMS** - Key Management Service
  - Customer managed keys vs AWS managed keys
  - Key rotation
  - Envelope encryption
  - CMK policies
- **Secrets Manager** - Secret rotation and management
- **Systems Manager Parameter Store** - Configuration management
- **AWS Certificate Manager (ACM)** - SSL/TLS certificates
- **WAF** - Web Application Firewall
  - Rules and conditions
  - Integration with CloudFront, ALB, API Gateway
- **Shield** - DDoS protection
  - Standard (free) vs Advanced
- **GuardDuty** - Threat detection
- **Inspector** - Vulnerability scanning
- **Macie** - Data security and privacy
- **Cognito** - User authentication
  - User pools and identity pools

### Monitoring & Management

- **CloudWatch** - Monitoring and observability
  - Metrics, alarms, and dashboards
  - Logs and log groups
  - EventBridge (CloudWatch Events)
  - Container Insights, Lambda Insights
- **CloudTrail** - API auditing and governance
  - Organization trails
  - Event history
  - Integration with CloudWatch Logs
- **AWS Config** - Resource inventory and compliance
  - Config rules
  - Conformance packs
- **Trusted Advisor** - Best practice recommendations
  - Cost optimization, performance, security, fault tolerance
- **Systems Manager** - Operational management
  - Session Manager
  - Patch Manager
  - Automation
  - OpsCenter

### Migration & Transfer

- **Database Migration Service (DMS)** - Database migration
  - Homogeneous vs heterogeneous migrations
  - Schema Conversion Tool (SCT)
  - CDC (Change Data Capture)
- **Server Migration Service (SMS)** - Server migration
- **DataSync** - Data transfer
  - On-premises to AWS
  - Between AWS storage services
- **Snow Family** - Physical data transfer
  - Snowcone, Snowball, Snowmobile
  - Edge computing capabilities
- **Migration Hub** - Track migrations

### Application Integration

- **SQS** - Message queuing
  - Standard vs FIFO queues
  - Dead letter queues
  - Visibility timeout
- **SNS** - Pub/sub messaging
  - Topics and subscriptions
  - Fan-out patterns
- **EventBridge** - Event bus
  - Event patterns and rules
- **Step Functions** - Workflow orchestration
- **MQ** - Managed message broker (ActiveMQ, RabbitMQ)
- **AppSync** - GraphQL API

### Analytics

- **Kinesis** - Real-time data streaming
  - Data Streams
  - Data Firehose
  - Data Analytics
  - Video Streams
- **Athena** - Serverless query service
  - Query S3 data with SQL
- **EMR** - Big data processing (Hadoop, Spark)
- **QuickSight** - Business intelligence
- **Glue** - ETL service
  - Data Catalog
  - Crawlers

### Other Important Services

- **Organizations** - Multi-account management
  - Service Control Policies
  - Consolidated billing
  - Account structure (OUs)
- **CloudFormation** - Infrastructure as Code
  - Stacks and templates
  - StackSets
  - Change sets
  - Drift detection
- **Backup** - Centralized backup
  - Backup plans and vaults
- **Disaster Recovery** - Backup and DR strategies
  - Pilot Light, Warm Standby, Multi-Site Active/Active

## Study Resources

### Official AWS Resources
- [AWS Certified Solutions Architect Official Study Guide](https://www.amazon.com/Certified-Solutions-Architect-Official-Study/dp/1119982626)
- [AWS Architecture Center](https://aws.amazon.com/architecture/)
- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)
- [AWS Whitepapers](https://aws.amazon.com/whitepapers/)
  - Well-Architected Framework (MUST READ)
  - AWS Security Best Practices
  - Architecting for the Cloud: AWS Best Practices
  - AWS Storage Services Overview
- [AWS FAQs](https://aws.amazon.com/faqs/) - Read FAQs for all core services

### Online Courses
- **A Cloud Guru** - AWS Certified Solutions Architect Associate
- **Udemy** - Stephane Maarek's Ultimate AWS Certified Solutions Architect Associate
- **Linux Academy / A Cloud Guru**
- **AWS Skill Builder** - Free official training
- **Adrian Cantrill** - Highly regarded comprehensive course

### Practice Exams
- **Tutorials Dojo** - Highly recommended (Jon Bonso)
- **Whizlabs** - Practice exams
- **AWS Official Practice Exam** - $20, 20 questions

### Hands-on Labs
- **AWS Free Tier** - Practice with actual services
- **A Cloud Guru Sandbox**
- **Qwiklabs / Pluralsight**
- **AWS Workshops** - workshops.aws

### Must-Read Documentation
- VPC User Guide
- EC2 User Guide
- S3 Developer Guide
- RDS User Guide
- Well-Architected Framework

## Study Tips

### 1. Understand the Well-Architected Framework
- **Operational Excellence** - Run and monitor systems
- **Security** - Protect information and systems
- **Reliability** - Recover from failures, scale resources
- **Performance Efficiency** - Use resources efficiently
- **Cost Optimization** - Avoid unnecessary costs
- **Sustainability** - Minimize environmental impact

### 2. Focus on High-Impact Areas
- **VPC** - Deeply understand networking
- **EC2** - Know all instance types and use cases
- **S3** - Storage classes and when to use each
- **RDS/Aurora** - HA and DR strategies
- **IAM** - Security best practices
- **Load Balancing** - ALB vs NLB use cases

### 3. Learn Architectural Patterns
- Multi-tier architectures
- Event-driven architectures
- Microservices patterns
- Hybrid cloud architectures
- Disaster recovery strategies

### 4. Understand Trade-offs
- Cost vs Performance
- RTO vs RPO
- Consistency vs Availability
- Managed services vs self-managed

### 5. Practice Exam Strategy
- Take practice exams under timed conditions
- Review ALL explanations (correct and incorrect)
- Identify patterns in questions
- Focus on weak domains

### 6. Common Exam Scenarios
- Design highly available and fault-tolerant systems
- Choose appropriate storage solutions
- Secure applications and data
- Optimize for cost
- Migrate on-premises workloads
- Design for disaster recovery

## Sample Architecture Scenarios

### Scenario 1: Highly Available Web Application
**Requirements**: Auto-scaling web tier, database HA
- Multi-AZ VPC
- ALB across multiple AZs
- EC2 Auto Scaling groups
- RDS Multi-AZ
- CloudFront for content delivery
- Route 53 for DNS

### Scenario 2: Serverless Data Processing
**Requirements**: Process files uploaded to S3
- S3 bucket with event notification
- Lambda for processing
- DynamoDB for metadata
- SNS for notifications
- CloudWatch for monitoring

### Scenario 3: Hybrid Cloud Connectivity
**Requirements**: Secure connection to on-premises datacenter
- VPN or Direct Connect
- Transit Gateway for multi-VPC connectivity
- Route 53 Resolver for DNS
- Storage Gateway for hybrid storage

### Scenario 4: Disaster Recovery
**Requirements**: RPO < 1 hour, RTO < 4 hours
- Pilot Light strategy
- Regular snapshots and AMIs
- Cross-region replication
- Route 53 failover routing
- Automated recovery with Lambda/CloudFormation

## Key Concepts to Memorize

### EC2 Instance Types
- **General Purpose**: T3, M5 (balanced compute, memory, networking)
- **Compute Optimized**: C5 (high-performance processors)
- **Memory Optimized**: R5, X1 (in-memory databases, big data)
- **Storage Optimized**: I3, D2 (high sequential read/write, data warehouses)
- **Accelerated Computing**: P3, G4 (GPU workloads, ML)

### EBS Volume Types
- **gp3/gp2**: General purpose SSD (boot volumes, dev/test)
- **io2/io1**: Provisioned IOPS SSD (databases, critical apps)
- **st1**: Throughput optimized HDD (big data, data warehouses)
- **sc1**: Cold HDD (infrequent access, lowest cost)

### S3 Storage Classes
- **Standard**: Frequent access, low latency
- **Intelligent-Tiering**: Unknown access patterns
- **Standard-IA**: Infrequent access, rapid retrieval
- **One Zone-IA**: Infrequent access, single AZ
- **Glacier Instant Retrieval**: Archive, millisecond retrieval
- **Glacier Flexible Retrieval**: Archive, minutes to hours
- **Glacier Deep Archive**: Long-term archive, 12-48 hours

### RDS Multi-AZ vs Read Replicas
| Feature | Multi-AZ | Read Replicas |
|---------|----------|---------------|
| Purpose | High availability | Read scaling |
| Sync | Synchronous | Asynchronous |
| Endpoint | Same endpoint | Separate endpoint |
| Failover | Automatic | Manual promotion |
| Region | Same region | Same or cross-region |

## Common Gotchas

1. **NAT Gateway** - Must be in public subnet, requires EIP
2. **Security Groups** - Stateful (return traffic automatic)
3. **NACLs** - Stateless (must allow both inbound and outbound)
4. **S3 bucket names** - Globally unique
5. **RDS Read Replicas** - Can be promoted to standalone DB
6. **EBS snapshots** - Incremental, stored in S3
7. **VPC Peering** - Non-transitive routing
8. **Reserved Instances** - Zonal vs Regional scope

## Exam Day Tips

- **Time management**: 2 minutes per question
- **Read carefully**: "MOST cost-effective", "LEAST operational overhead", "MOST secure"
- **Eliminate wrong answers**: Usually can eliminate 2 options immediately
- **AWS best practices**: Choose managed services, multi-AZ, encryption
- **Flag and review**: Don't get stuck on hard questions
- **No penalty for guessing**: Answer all questions

## Disaster Recovery Strategies

| Strategy | RTO/RPO | Cost | Complexity |
|----------|---------|------|------------|
| Backup & Restore | Hours/24hr | $ | Low |
| Pilot Light | 10 min/min | $$ | Medium |
| Warm Standby | Minutes/sec | $$$ | Medium-High |
| Multi-Site Active/Active | Real-time/none | $$$$ | High |

## Next Steps After Passing

1. **Gain hands-on experience** with complex architectures
2. **Pursue advanced certifications**:
   - AWS Solutions Architect Professional
   - AWS Security Specialty
   - AWS Advanced Networking Specialty
3. **Stay current** with AWS announcements (re:Invent, What's New)
4. **Share knowledge** through blogs, mentoring, presentations

## Additional Resources

- [AWS Architecture Blog](https://aws.amazon.com/blogs/architecture/)
- [AWS This Week](https://acloudguru.com/videos/aws-this-week)
- [r/AWSCertifications](https://www.reddit.com/r/AWSCertifications/)
- [AWS re:Post](https://repost.aws/) - Community Q&A
- [AWS Reference Architectures](https://aws.amazon.com/architecture/reference-architecture-diagrams/)

## Useful Links

- [Exam Guide (Official)](https://aws.amazon.com/certification/certified-solutions-architect-associate/)
- [Sample Questions](https://d1.awsstatic.com/training-and-certification/docs-sa-assoc/AWS-Certified-Solutions-Architect-Associate_Sample-Questions.pdf)
- [Service Limits Documentation](https://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html)
- [AWS Architecture Icons](https://aws.amazon.com/architecture/icons/) - For diagramming

---

**Good luck with your certification journey!** 🏗️

Remember: Think like an architect - consider scalability, reliability, security, and cost in every design decision.
