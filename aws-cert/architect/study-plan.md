# 8-Week AWS Solutions Architect Certification Study Plan

A detailed week-by-week study schedule for the AWS Certified Solutions Architect - Associate exam.

## Week 1: Fundamentals & Compute

### Learning Objectives
- Understand AWS global infrastructure
- Master EC2 and related services
- Learn Auto Scaling and Load Balancing

### Daily Breakdown

**Day 1-2: AWS Fundamentals**
- [ ] Read: AWS Global Infrastructure (Regions, AZs, Edge Locations)
- [ ] Watch: Course introduction and AWS fundamentals
- [ ] Learn: Well-Architected Framework overview
- [ ] Hands-on: Create AWS account, enable MFA, set up billing alerts
- [ ] Hands-on: Create IAM user with appropriate permissions

**Day 3-5: EC2 Deep Dive**
- [ ] Read: EC2 instance types and families (C5, M5, R5, T3, etc.)
- [ ] Learn: Pricing models (On-Demand, Reserved, Spot, Savings Plans)
- [ ] Learn: Security groups, key pairs, user data, metadata
- [ ] Learn: Placement groups (Cluster, Spread, Partition)
- [ ] Hands-on: Launch EC2 instances in different AZs
- [ ] Hands-on: Create and configure security groups
- [ ] Hands-on: Use EC2 user data for bootstrapping
- [ ] Hands-on: Create AMI from running instance
- [ ] Hands-on: Test placement groups

**Day 6-7: Auto Scaling & Load Balancing**
- [ ] Read: Auto Scaling groups and policies
- [ ] Learn: Launch templates vs launch configurations
- [ ] Learn: Application Load Balancer (ALB) vs Network Load Balancer (NLB)
- [ ] Learn: Health checks and target groups
- [ ] Hands-on: Create Auto Scaling group across multiple AZs
- [ ] Hands-on: Configure ALB with target groups
- [ ] Hands-on: Implement scaling policies (target tracking, step, scheduled)
- [ ] Practice: EC2 and load balancing quiz questions

### Study Time: 15-18 hours

---

## Week 2: VPC & Networking

### Learning Objectives
- Master VPC components and architecture
- Understand hybrid connectivity options
- Learn DNS and content delivery

### Daily Breakdown

**Day 1-4: VPC Deep Dive (CRITICAL)**
- [ ] Read: VPC fundamentals (CIDR, subnets, route tables)
- [ ] Learn: Internet Gateway vs NAT Gateway vs NAT Instance
- [ ] Learn: Security Groups vs Network ACLs
- [ ] Learn: VPC Peering vs Transit Gateway
- [ ] Learn: VPC Endpoints (Gateway and Interface)
- [ ] Learn: VPC Flow Logs
- [ ] Hands-on: Create custom VPC with public and private subnets
- [ ] Hands-on: Configure route tables and Internet Gateway
- [ ] Hands-on: Set up NAT Gateway for private subnet internet access
- [ ] Hands-on: Create VPC Peering connection
- [ ] Hands-on: Configure Security Groups and NACLs
- [ ] Hands-on: Set up VPC Endpoint for S3
- [ ] Practice: VPC networking scenarios (do 50+ questions)

**Day 5: Hybrid Connectivity**
- [ ] Read: Site-to-Site VPN
- [ ] Learn: Direct Connect and Direct Connect Gateway
- [ ] Learn: Transit Gateway for multi-VPC connectivity
- [ ] Hands-on: Configure Site-to-Site VPN (simulated)
- [ ] Learn: Use cases for each connectivity option

**Day 6-7: Route 53 & CloudFront**
- [ ] Read: Route 53 routing policies
- [ ] Learn: Health checks and failover
- [ ] Learn: CloudFront distributions and origins
- [ ] Learn: Edge locations and caching strategies
- [ ] Hands-on: Create Route 53 hosted zone
- [ ] Hands-on: Configure different routing policies
- [ ] Hands-on: Set up CloudFront distribution with S3 origin
- [ ] Hands-on: Configure cache behaviors and TTL
- [ ] Practice: Networking and CDN quiz questions

### Study Time: 18-20 hours

---

## Week 3: Storage Solutions

### Learning Objectives
- Master S3 features and optimization
- Understand EBS, EFS, and other storage services
- Learn storage selection criteria

### Daily Breakdown

**Day 1-4: S3 Deep Dive (CRITICAL)**
- [ ] Read: S3 storage classes and use cases
- [ ] Learn: Bucket policies, ACLs, and access control
- [ ] Learn: Versioning, MFA Delete, Object Lock
- [ ] Learn: S3 Replication (CRR and SRR)
- [ ] Learn: Lifecycle policies and transitions
- [ ] Learn: S3 encryption options (SSE-S3, SSE-KMS, SSE-C)
- [ ] Learn: S3 performance optimization (multipart, transfer acceleration)
- [ ] Hands-on: Create buckets with different storage classes
- [ ] Hands-on: Configure bucket policies and encryption
- [ ] Hands-on: Enable versioning and MFA Delete
- [ ] Hands-on: Set up lifecycle policies
- [ ] Hands-on: Configure Cross-Region Replication
- [ ] Hands-on: Host static website on S3 + CloudFront
- [ ] Practice: S3 quiz questions (do 50+)

**Day 5-6: EBS & EFS**
- [ ] Read: EBS volume types (gp3, io2, st1, sc1)
- [ ] Learn: EBS snapshots and lifecycle
- [ ] Learn: EBS encryption and performance
- [ ] Learn: EFS performance and throughput modes
- [ ] Learn: EFS storage classes (Standard, IA)
- [ ] Hands-on: Create and attach EBS volumes
- [ ] Hands-on: Create EBS snapshots and AMIs
- [ ] Hands-on: Set up EFS with multiple mount targets
- [ ] Hands-on: Test EFS across multiple EC2 instances

**Day 7: Other Storage Services**
- [ ] Read: Storage Gateway (File, Volume, Tape)
- [ ] Learn: FSx for Windows and FSx for Lustre
- [ ] Learn: AWS Backup service
- [ ] Learn: When to use each storage service
- [ ] Practice: Storage selection quiz questions

### Study Time: 18-20 hours

---

## Week 4: Databases & Caching

### Learning Objectives
- Master RDS and Aurora
- Understand database selection criteria
- Learn caching strategies

### Daily Breakdown

**Day 1-3: RDS & Aurora**
- [ ] Read: RDS database engines and features
- [ ] Learn: Multi-AZ vs Read Replicas (CRITICAL)
- [ ] Learn: Automated backups vs manual snapshots
- [ ] Learn: RDS parameter groups and option groups
- [ ] Learn: Aurora architecture and features
- [ ] Learn: Aurora Serverless and Global Database
- [ ] Hands-on: Launch RDS instance with Multi-AZ
- [ ] Hands-on: Create Read Replicas
- [ ] Hands-on: Test automated backups and snapshots
- [ ] Hands-on: Deploy Aurora cluster
- [ ] Hands-on: Promote Read Replica to standalone
- [ ] Practice: RDS high availability scenarios

**Day 4-5: NoSQL & Other Databases**
- [ ] Read: DynamoDB architecture and use cases
- [ ] Learn: DynamoDB capacity modes and global tables
- [ ] Learn: DynamoDB Accelerator (DAX)
- [ ] Learn: DocumentDB, Neptune, QLDB, Timestream
- [ ] Learn: When to use SQL vs NoSQL
- [ ] Hands-on: Create DynamoDB table with indexes
- [ ] Hands-on: Test DynamoDB global tables
- [ ] Practice: Database selection scenarios

**Day 6: ElastiCache**
- [ ] Read: ElastiCache for Redis vs Memcached
- [ ] Learn: Caching strategies (lazy loading, write-through)
- [ ] Learn: Use cases (session store, database cache)
- [ ] Hands-on: Deploy ElastiCache cluster
- [ ] Practice: Caching architecture questions

**Day 7: Data Warehouse & Analytics**
- [ ] Read: Redshift architecture
- [ ] Learn: Redshift Spectrum
- [ ] Learn: Athena for querying S3
- [ ] Learn: When to use data warehouse vs database
- [ ] Practice: Database and analytics quiz questions

### Study Time: 18-20 hours

---

## Week 5: Security & Identity

### Learning Objectives
- Master IAM and access management
- Understand encryption and compliance
- Learn security best practices

### Daily Breakdown

**Day 1-3: IAM Deep Dive (CRITICAL)**
- [ ] Read: IAM users, groups, roles, and policies
- [ ] Learn: Policy types (managed, inline, resource-based)
- [ ] Learn: IAM policy evaluation logic
- [ ] Learn: Cross-account access patterns
- [ ] Learn: Permission boundaries and SCPs
- [ ] Learn: STS and temporary credentials
- [ ] Hands-on: Create custom IAM policies
- [ ] Hands-on: Configure cross-account role assumption
- [ ] Hands-on: Implement permission boundaries
- [ ] Hands-on: Use IAM Access Analyzer
- [ ] Practice: IAM policy troubleshooting (do 50+ questions)

**Day 4-5: Encryption & Key Management**
- [ ] Read: KMS concepts and key types
- [ ] Learn: Envelope encryption
- [ ] Learn: S3 encryption methods
- [ ] Learn: EBS and RDS encryption
- [ ] Learn: Secrets Manager vs Parameter Store
- [ ] Hands-on: Create KMS keys and key policies
- [ ] Hands-on: Encrypt S3 buckets with KMS
- [ ] Hands-on: Store secrets in Secrets Manager
- [ ] Hands-on: Use Parameter Store for configuration

**Day 6-7: Security Services**
- [ ] Read: AWS Certificate Manager (ACM)
- [ ] Learn: WAF rules and conditions
- [ ] Learn: Shield Standard vs Advanced
- [ ] Learn: GuardDuty, Inspector, Macie
- [ ] Learn: AWS Config for compliance
- [ ] Learn: CloudTrail for auditing
- [ ] Hands-on: Configure WAF rules
- [ ] Hands-on: Enable GuardDuty
- [ ] Hands-on: Set up Config rules
- [ ] Hands-on: Create CloudTrail organization trail
- [ ] Practice: Security and compliance quiz questions

### Study Time: 18-20 hours

---

## Week 6: High Availability & Disaster Recovery

### Learning Objectives
- Design highly available architectures
- Understand disaster recovery strategies
- Learn monitoring and optimization

### Daily Breakdown

**Day 1-2: High Availability Patterns**
- [ ] Read: Multi-AZ deployment patterns
- [ ] Learn: Active-Active vs Active-Passive
- [ ] Learn: Health checks and failover
- [ ] Learn: Designing for fault tolerance
- [ ] Hands-on: Build highly available web application
- [ ] Hands-on: Configure Route 53 failover routing
- [ ] Practice: High availability scenarios

**Day 3-4: Disaster Recovery**
- [ ] Read: DR strategies (Backup & Restore, Pilot Light, Warm Standby, Multi-Site)
- [ ] Learn: RTO vs RPO requirements
- [ ] Learn: Cross-region replication strategies
- [ ] Learn: Aurora Global Database for DR
- [ ] Learn: DynamoDB global tables
- [ ] Hands-on: Implement pilot light DR architecture
- [ ] Hands-on: Configure cross-region backup
- [ ] Practice: DR and business continuity scenarios

**Day 5-6: Monitoring & Logging**
- [ ] Read: CloudWatch metrics, alarms, and dashboards
- [ ] Learn: CloudWatch Logs and Insights
- [ ] Learn: EventBridge (CloudWatch Events)
- [ ] Learn: CloudTrail vs Config vs CloudWatch
- [ ] Learn: AWS Systems Manager
- [ ] Hands-on: Create custom CloudWatch metrics
- [ ] Hands-on: Set up CloudWatch alarms and dashboards
- [ ] Hands-on: Create EventBridge rules
- [ ] Hands-on: Analyze logs with CloudWatch Insights

**Day 7: Cost Optimization**
- [ ] Read: Cost optimization strategies
- [ ] Learn: AWS Cost Explorer and Budgets
- [ ] Learn: Trusted Advisor recommendations
- [ ] Learn: Right-sizing and reserved capacity
- [ ] Hands-on: Set up cost allocation tags
- [ ] Hands-on: Create budget alerts
- [ ] Practice: Cost optimization scenarios

### Study Time: 18-20 hours

---

## Week 7: Application Integration & Migration

### Learning Objectives
- Understand messaging and integration patterns
- Learn migration strategies
- Take first practice exam

### Daily Breakdown

**Day 1-2: Messaging Services**
- [ ] Read: SQS (Standard vs FIFO)
- [ ] Learn: SNS topics and subscriptions
- [ ] Learn: EventBridge for event routing
- [ ] Learn: Step Functions for orchestration
- [ ] Learn: Decoupling architectures
- [ ] Hands-on: Create SQS queue with DLQ
- [ ] Hands-on: Implement SNS fan-out pattern
- [ ] Hands-on: Configure EventBridge rules
- [ ] Practice: Integration patterns quiz

**Day 3: Migration & Transfer**
- [ ] Read: Database Migration Service (DMS)
- [ ] Learn: Server Migration Service (SMS)
- [ ] Learn: DataSync and Snow Family
- [ ] Learn: 6 R's of migration (Rehost, Replatform, etc.)
- [ ] Learn: Migration Hub
- [ ] Practice: Migration strategy scenarios

**Day 4: Containers & Serverless**
- [ ] Read: ECS vs EKS
- [ ] Learn: Fargate vs EC2 launch types
- [ ] Learn: Lambda use cases and best practices
- [ ] Learn: API Gateway integration
- [ ] Hands-on: Deploy container to ECS Fargate
- [ ] Hands-on: Create Lambda function with API Gateway

**Day 5: First Practice Exam**
- [ ] Take full-length practice exam (130 min)
- [ ] Score and identify weak domains
- [ ] Create focused review list
- [ ] Analyze question patterns

**Day 6-7: Targeted Review**
- [ ] Review all incorrect answers thoroughly
- [ ] Re-study weak domains identified
- [ ] Hands-on labs for problem areas
- [ ] Read relevant service FAQs
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
- [ ] Hands-on labs for problem topics
- [ ] Re-read service FAQs for weak services
- [ ] Watch recap videos
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
- [ ] Light hands-on practice
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

[ ] Completed all video lectures
[ ] Read all assigned documentation
[ ] Read relevant service FAQs
[ ] Completed all hands-on labs
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
2. **Learn (60-90 min)**: Watch videos, read documentation, FAQs
3. **Practice (60-90 min)**: Hands-on labs and architecture design
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
