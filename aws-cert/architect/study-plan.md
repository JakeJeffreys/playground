# 8-Week AWS Solutions Architect Certification Study Plan

A detailed week-by-week study schedule for the AWS Certified Solutions Architect - Associate exam.

## TLDR - Study Plan Overview

| Week | Focus Areas | Key Services | Hours |
|------|-------------|--------------|-------|
| **1** | Fundamentals & Compute | EC2, Auto Scaling, ALB/NLB | 15-18 |
| **2** | VPC & Networking | VPC, Direct Connect, Route 53, CloudFront | 18-20 |
| **3** | Storage Solutions | S3, EBS, EFS, Storage Gateway, FSx | 18-20 |
| **4** | Databases & Caching | RDS, Aurora, DynamoDB, ElastiCache, Redshift | 18-20 |
| **5** | Security & Identity | IAM, KMS, Secrets Manager, WAF, GuardDuty, Config, CloudTrail | 18-20 |
| **6** | High Availability & DR | Multi-AZ, DR strategies, CloudWatch, Cost Optimization | 18-20 |
| **7** | Integration & Migration + Practice Exam #1 | SQS, SNS, DMS, ECS + Review | 18-20 |
| **8** | Final Review & Practice Exams #2-3 | Architecture patterns + Exam prep | 15-20 |

**Total**: 140+ hours over 8 weeks

---

## Week 1: Fundamentals & Compute

### Learning Objectives
- Understand AWS global infrastructure
- Master EC2 and related services
- Learn Auto Scaling and Load Balancing

### Daily Breakdown

**Day 1-2: AWS Fundamentals**
- [ ] AWS Global Infrastructure (Regions, AZs, Edge Locations)
- [ ] Well-Architected Framework overview
- [ ] Create AWS account, enable MFA, set up billing alerts
- [ ] Create IAM user with appropriate permissions

**Day 3-5: EC2 Deep Dive**
- [ ] EC2 instance types and families (C5, M5, R5, T3, etc.)
- [ ] Pricing models (On-Demand, Reserved, Spot, Savings Plans)
- [ ] Security groups, key pairs, user data, metadata
- [ ] Placement groups (Cluster, Spread, Partition)
- [ ] Launch EC2 instances in different AZs
- [ ] Create and configure security groups
- [ ] Use EC2 user data for bootstrapping
- [ ] Create AMI from running instance
- [ ] Test placement groups

**Day 6-7: Auto Scaling & Load Balancing**
- [ ] Auto Scaling groups and policies
- [ ] Launch templates vs launch configurations
- [ ] Application Load Balancer (ALB) vs Network Load Balancer (NLB)
- [ ] Health checks and target groups
- [ ] Create Auto Scaling group across multiple AZs
- [ ] Configure ALB with target groups
- [ ] Implement scaling policies (target tracking, step, scheduled)
- [ ] EC2 and load balancing practice questions

### Study Time: 15-18 hours

---

## Week 2: VPC & Networking

### Learning Objectives
- Master VPC components and architecture
- Understand hybrid connectivity options
- Learn DNS and content delivery

### Daily Breakdown

**Day 1-4: VPC Deep Dive (CRITICAL)**
- [ ] VPC fundamentals (CIDR, subnets, route tables)
- [ ] Internet Gateway vs NAT Gateway vs NAT Instance
- [ ] Security Groups vs Network ACLs
- [ ] VPC Peering vs Transit Gateway
- [ ] VPC Endpoints (Gateway and Interface)
- [ ] VPC Flow Logs
- [ ] Create custom VPC with public and private subnets
- [ ] Configure route tables and Internet Gateway
- [ ] Set up NAT Gateway for private subnet internet access
- [ ] Create VPC Peering connection
- [ ] Configure Security Groups and NACLs
- [ ] Set up VPC Endpoint for S3
- [ ] VPC networking practice scenarios (50+ questions)

**Day 5: Hybrid Connectivity**
- [ ] Site-to-Site VPN
- [ ] Direct Connect and Direct Connect Gateway
- [ ] Transit Gateway for multi-VPC connectivity
- [ ] Configure Site-to-Site VPN (simulated)
- [ ] Use cases for each connectivity option

**Day 6-7: Route 53 & CloudFront**
- [ ] Route 53 routing policies
- [ ] Health checks and failover
- [ ] CloudFront distributions and origins
- [ ] Edge locations and caching strategies
- [ ] Create Route 53 hosted zone
- [ ] Configure different routing policies
- [ ] Set up CloudFront distribution with S3 origin
- [ ] Configure cache behaviors and TTL
- [ ] Networking and CDN practice questions

### Study Time: 18-20 hours

---

## Week 3: Storage Solutions

### Learning Objectives
- Master S3 features and optimization
- Understand EBS, EFS, and other storage services
- Learn storage selection criteria

### Daily Breakdown

**Day 1-4: S3 Deep Dive (CRITICAL)**
- [ ] S3 storage classes and use cases
- [ ] Bucket policies, ACLs, and access control
- [ ] Versioning, MFA Delete, Object Lock
- [ ] S3 Replication (CRR and SRR)
- [ ] Lifecycle policies and transitions
- [ ] S3 encryption options (SSE-S3, SSE-KMS, SSE-C)
- [ ] S3 performance optimization (multipart, transfer acceleration)
- [ ] Create buckets with different storage classes
- [ ] Configure bucket policies and encryption
- [ ] Enable versioning and MFA Delete
- [ ] Set up lifecycle policies
- [ ] Configure Cross-Region Replication
- [ ] Host static website on S3 + CloudFront
- [ ] S3 practice questions (50+)

**Day 5-6: EBS & EFS**
- [ ] EBS volume types (gp3, io2, st1, sc1)
- [ ] EBS snapshots and lifecycle
- [ ] EBS encryption and performance
- [ ] EFS performance and throughput modes
- [ ] EFS storage classes (Standard, IA)
- [ ] Create and attach EBS volumes
- [ ] Create EBS snapshots and AMIs
- [ ] Set up EFS with multiple mount targets
- [ ] Test EFS across multiple EC2 instances

**Day 7: Other Storage Services**
- [ ] Storage Gateway (File, Volume, Tape)
- [ ] FSx for Windows and FSx for Lustre
- [ ] AWS Backup service
- [ ] When to use each storage service
- [ ] Storage selection practice questions

### Study Time: 18-20 hours

---

## Week 4: Databases & Caching

### Learning Objectives
- Master RDS and Aurora
- Understand database selection criteria
- Learn caching strategies

### Daily Breakdown

**Day 1-3: RDS & Aurora**
- [ ] RDS database engines and features
- [ ] Multi-AZ vs Read Replicas (CRITICAL)
- [ ] Automated backups vs manual snapshots
- [ ] RDS parameter groups and option groups
- [ ] Aurora architecture and features
- [ ] Aurora Serverless and Global Database
- [ ] Launch RDS instance with Multi-AZ
- [ ] Create Read Replicas
- [ ] Test automated backups and snapshots
- [ ] Deploy Aurora cluster
- [ ] Promote Read Replica to standalone
- [ ] RDS high availability practice scenarios

**Day 4-5: NoSQL & Other Databases**
- [ ] DynamoDB architecture and use cases
- [ ] DynamoDB capacity modes and global tables
- [ ] DynamoDB Accelerator (DAX)
- [ ] DocumentDB, Neptune, QLDB, Timestream
- [ ] When to use SQL vs NoSQL
- [ ] Create DynamoDB table with indexes
- [ ] Test DynamoDB global tables
- [ ] Database selection practice scenarios

**Day 6: ElastiCache**
- [ ] ElastiCache for Redis vs Memcached
- [ ] Caching strategies (lazy loading, write-through)
- [ ] Use cases (session store, database cache)
- [ ] Deploy ElastiCache cluster
- [ ] Caching architecture practice questions

**Day 7: Data Warehouse & Analytics**
- [ ] Redshift architecture
- [ ] Redshift Spectrum
- [ ] Athena for querying S3
- [ ] When to use data warehouse vs database
- [ ] Database and analytics practice questions

### Study Time: 18-20 hours

---

## Week 5: Security & Identity

### Learning Objectives
- Master IAM and access management
- Understand encryption and compliance
- Learn security best practices

### Daily Breakdown

**Day 1-3: IAM Deep Dive (CRITICAL)**
- [ ] IAM users, groups, roles, and policies
- [ ] Policy types (managed, inline, resource-based)
- [ ] IAM policy evaluation logic
- [ ] Cross-account access patterns
- [ ] Permission boundaries and SCPs
- [ ] STS and temporary credentials
- [ ] Create custom IAM policies
- [ ] Configure cross-account role assumption
- [ ] Implement permission boundaries
- [ ] Use IAM Access Analyzer
- [ ] IAM policy troubleshooting (50+ questions)

**Day 4-5: Encryption & Key Management**
- [ ] KMS concepts and key types
- [ ] Envelope encryption
- [ ] S3 encryption methods
- [ ] EBS and RDS encryption
- [ ] Secrets Manager vs Parameter Store
- [ ] Create KMS keys and key policies
- [ ] Encrypt S3 buckets with KMS
- [ ] Store secrets in Secrets Manager
- [ ] Use Parameter Store for configuration

**Day 6-7: Security Services**
- [ ] AWS Certificate Manager (ACM)
- [ ] WAF rules and conditions
- [ ] Shield Standard vs Advanced
- [ ] GuardDuty, Inspector, Macie
- [ ] AWS Config for compliance
- [ ] CloudTrail for auditing
- [ ] Configure WAF rules
- [ ] Enable GuardDuty
- [ ] Set up Config rules
- [ ] Create CloudTrail organization trail
- [ ] Security and compliance practice questions

### Study Time: 18-20 hours

---

## Week 6: High Availability & Disaster Recovery

### Learning Objectives
- Design highly available architectures
- Understand disaster recovery strategies
- Learn monitoring and optimization

### Daily Breakdown

**Day 1-2: High Availability Patterns**
- [ ] Multi-AZ deployment patterns
- [ ] Active-Active vs Active-Passive
- [ ] Health checks and failover
- [ ] Designing for fault tolerance
- [ ] Build highly available web application
- [ ] Configure Route 53 failover routing
- [ ] High availability practice scenarios

**Day 3-4: Disaster Recovery**
- [ ] DR strategies (Backup & Restore, Pilot Light, Warm Standby, Multi-Site)
- [ ] RTO vs RPO requirements
- [ ] Cross-region replication strategies
- [ ] Aurora Global Database for DR
- [ ] DynamoDB global tables
- [ ] Implement pilot light DR architecture
- [ ] Configure cross-region backup
- [ ] DR and business continuity practice scenarios

**Day 5-6: Monitoring & Logging**
- [ ] CloudWatch metrics, alarms, and dashboards
- [ ] CloudWatch Logs and Insights
- [ ] EventBridge (CloudWatch Events)
- [ ] CloudTrail vs Config vs CloudWatch
- [ ] AWS Systems Manager
- [ ] Create custom CloudWatch metrics
- [ ] Set up CloudWatch alarms and dashboards
- [ ] Create EventBridge rules
- [ ] Analyze logs with CloudWatch Insights

**Day 7: Cost Optimization**
- [ ] Cost optimization strategies
- [ ] AWS Cost Explorer and Budgets
- [ ] Trusted Advisor recommendations
- [ ] Right-sizing and reserved capacity
- [ ] Set up cost allocation tags
- [ ] Create budget alerts
- [ ] Cost optimization practice scenarios

### Study Time: 18-20 hours

---

## Week 7: Application Integration & Migration

### Learning Objectives
- Understand messaging and integration patterns
- Learn migration strategies
- Take first practice exam

### Daily Breakdown

**Day 1-2: Messaging Services**
- [ ] SQS (Standard vs FIFO)
- [ ] SNS topics and subscriptions
- [ ] EventBridge for event routing
- [ ] Step Functions for orchestration
- [ ] Decoupling architectures
- [ ] Create SQS queue with DLQ
- [ ] Implement SNS fan-out pattern
- [ ] Configure EventBridge rules
- [ ] Integration patterns practice questions

**Day 3: Migration & Transfer**
- [ ] Database Migration Service (DMS)
- [ ] Server Migration Service (SMS)
- [ ] DataSync and Snow Family
- [ ] 6 R's of migration (Rehost, Replatform, etc.)
- [ ] Migration Hub
- [ ] Migration strategy practice scenarios

**Day 4: Containers & Serverless**
- [ ] ECS vs EKS
- [ ] Fargate vs EC2 launch types
- [ ] Lambda use cases and best practices
- [ ] API Gateway integration
- [ ] Deploy container to ECS Fargate
- [ ] Create Lambda function with API Gateway

**Day 5: First Practice Exam**
- [ ] Take full-length practice exam (130 min)
- [ ] Score and identify weak domains
- [ ] Create focused review list
- [ ] Analyze question patterns

**Day 6-7: Targeted Review**
- [ ] Review all incorrect answers thoroughly
- [ ] Re-study weak domains identified
- [ ] Labs for problem areas
- [ ] Study relevant service FAQs
- [ ] Review Well-Architected Framework for weak areas

### Study Time: 18-20 hours

---

## Week 8: Final Review & Practice Exams

### Learning Objectives
- Take multiple practice exams
- Review all core concepts
- Build exam confidence

### Daily Breakdown

**Day 1: Architecture Patterns Review**
- [ ] Review: Multi-tier web application architectures
- [ ] Review: Serverless architectures
- [ ] Review: Hybrid cloud architectures
- [ ] Review: Event-driven architectures
- [ ] Review: Microservices patterns
- [ ] Create architecture diagrams for common scenarios

**Day 2: Second Practice Exam**
- [ ] Take practice exam #2
- [ ] Review all questions (correct and incorrect)
- [ ] Identify remaining weak areas
- [ ] Note common mistake patterns

**Day 3: Service Limits & Gotchas**
- [ ] Review: EC2 instance types and limits
- [ ] Review: VPC limits and best practices
- [ ] Review: S3 performance and limits
- [ ] Review: RDS Multi-AZ vs Read Replicas
- [ ] Review: Common exam gotchas
- [ ] Create final cheat sheet

**Day 4: Deep Dive on Weak Areas**
- [ ] Focus on domains with lowest practice scores
- [ ] Labs for problem topics
- [ ] Study service FAQs for weak services
- [ ] Review videos/content for weak areas
- [ ] Review Well-Architected Framework pillars

**Day 5: Third Practice Exam**
- [ ] Take practice exam #3
- [ ] Aim for 85%+ score
- [ ] Review any remaining gaps
- [ ] Build confidence

**Day 6: Final Review**
- [ ] Quick review of all services
- [ ] Review exam strategies and keywords
- [ ] Review cheat sheets and notes
- [ ] Light practice
- [ ] Mentally prepare
- [ ] Get good sleep!

**Day 7: Exam Day (or rest day)**
- [ ] Light review in morning
- [ ] Review key decision trees
- [ ] Stay calm and confident
- [ ] Take the exam!
- [ ] Celebrate! 🎉

### Study Time: 15-20 hours

---

## Weekly Checklist Template

Use this for each week:

```
Week #: ___
Focus: _______________

[ ] Studied all core topics
[ ] Studied relevant documentation and FAQs
[ ] Completed labs
[ ] Took weekly practice questions (score: ___%)
[ ] Reviewed and understood mistakes
[ ] Created architecture diagrams
[ ] Updated study notes

Services mastered this week:
1. _______________
2. _______________
3. _______________

Weak areas to review:
1. _______________
2. _______________
3. _______________

Total study hours: ___ / 18 target
```

---

## Daily Study Routine

**Weekday Schedule** (2-3 hours/day):
1. **Warm-up (10 min)**: Review yesterday's notes
2. **Learn (60-90 min)**: Study core concepts and service features
3. **Practice (60-90 min)**: Labs and architecture design
4. **Review (20 min)**: Take notes, create diagrams, flashcards

**Weekend Schedule** (4-6 hours/day):
- Deep dive labs and complex scenarios
- Build complete architectures
- Practice exam questions (50-100 per day)
- Review and reinforce weak areas

---

## Progress Tracking

| Week | Topics | Labs | Quiz Score | Weak Areas | Hours |
|------|--------|------|------------|------------|-------|
| 1 | Compute & LB | ☐ | ___% | | ___ |
| 2 | VPC & Networking | ☐ | ___% | | ___ |
| 3 | Storage | ☐ | ___% | | ___ |
| 4 | Databases | ☐ | ___% | | ___ |
| 5 | Security & IAM | ☐ | ___% | | ___ |
| 6 | HA & DR | ☐ | ___% | | ___ |
| 7 | Integration & PE #1 | ☐ | ___% | | ___ |
| 8 | Final Review | ☐ | ___% | | ___ |

**Total Hours**: ___ / 140 recommended

**Practice Exam Scores**:
- Exam 1 (Week 7): ___%
- Exam 2 (Week 8): ___%
- Exam 3 (Week 8): ___%

---

## Exam Readiness Checklist

You're ready when you can:
- [ ] Score 85%+ on practice exams consistently
- [ ] Design multi-tier architectures from scratch
- [ ] Explain VPC networking without notes
- [ ] Choose appropriate storage for any scenario
- [ ] Design for high availability and disaster recovery
- [ ] Troubleshoot IAM permission issues
- [ ] Optimize architectures for cost
- [ ] Secure applications using defense in depth
- [ ] Explain RDS Multi-AZ vs Read Replicas clearly
- [ ] Select appropriate database for any workload
- [ ] Design hybrid cloud architectures
- [ ] Apply Well-Architected Framework principles

---

## Recommended Practice Exam Schedule

- **Week 4**: Domain-specific practice questions (50-100 per week)
- **Week 5**: Domain-specific practice questions (50-100 per week)
- **Week 6**: Full-length timed practice exam
- **Week 7**: Full-length timed practice exam + review
- **Week 8**: 2 full-length timed practice exams + targeted review

**Target Scores**:
- First exam: 70%+
- Second exam: 80%+
- Third exam: 85%+
- Exam day: 85%+ (720/1000 to pass)

---

## Architecture Design Practice

Spend time each week designing solutions for these scenarios:

**Week 1-2**: Basic Architectures
- 3-tier web application (web, app, database)
- Static website with global delivery
- Auto-scaling application

**Week 3-4**: Storage & Data
- Data lake architecture
- Hybrid storage solution
- Multi-region data replication

**Week 5-6**: Secure & Resilient
- Multi-AZ high availability design
- Disaster recovery architecture
- Secure hybrid cloud architecture

**Week 7-8**: Complex Scenarios
- Migration from on-premises
- Event-driven microservices
- Global, low-latency application

---

## Key Resources by Priority

**Must-Read** (in order):
1. AWS Well-Architected Framework
2. VPC documentation
3. EC2 User Guide (instance types, Auto Scaling)
4. S3 Developer Guide
5. RDS User Guide (Multi-AZ, Read Replicas)
6. IAM User Guide (policies, roles)

**Service FAQs to Read**:
1. VPC
2. EC2
3. S3
4. RDS
5. IAM
6. Route 53
7. CloudFront
8. ELB

**Optional but Helpful**:
- AWS Reference Architectures
- AWS Whitepapers on migration
- AWS YouTube re:Invent sessions
- AWS This Week podcast

---

## Tips for Success

### Study Strategies
- **Focus on "Why"**: Don't just memorize - understand when and why to use each service
- **Think Architecturally**: Always consider the bigger picture, not just individual services
- **Draw Diagrams**: Visualize architectures - this helps tremendously
- **Practice Trade-offs**: Cost vs Performance, RTO vs Cost, etc.
- **Hands-on is Critical**: You can't fake experience - build real solutions

### Exam Strategies
- **Read Carefully**: Look for keywords like "MOST cost-effective", "LEAST operational overhead", "MOST secure"
- **Eliminate Wrong Answers**: Usually 2 answers are clearly wrong
- **Trust AWS Best Practices**: Multi-AZ, encryption, managed services, least privilege
- **Watch for Distractors**: Some answers are correct but not the BEST answer
- **Time Management**: Flag hard questions, come back later

### Common Traps to Avoid
- Choosing outdated services (EC2-Classic, CloudWatch Events instead of EventBridge)
- Over-engineering when simple solution exists
- Ignoring the "MOST" or "LEAST" qualifier in questions
- Selecting insecure options (they're always wrong)
- Forgetting Multi-AZ for high availability requirements

---

**Remember**: You're learning to be a Solutions Architect, not just passing an exam. Focus on understanding architectural principles, and the certification will follow naturally.

**Good luck!** 🏗️
