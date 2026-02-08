# 8-Week AWS Developer Certification Study Plan

A detailed week-by-week study schedule for the AWS Certified Developer - Associate exam.

## TLDR - Study Plan Overview

| Week | Focus Areas | Key Services | Hours |
|------|-------------|--------------|-------|
| **1** | Compute & Fundamentals | EC2, Lambda | 12-15 |
| **2** | Storage & Databases | S3, DynamoDB | 15-18 |
| **3** | Security & IAM | IAM, Cognito, KMS, Secrets Manager | 15-18 |
| **4** | API Gateway & Networking | API Gateway, VPC | 15-18 |
| **5** | Messaging & Integration | SQS, SNS, EventBridge, Step Functions | 12-15 |
| **6** | CI/CD & Deployment | CodeCommit, CodeBuild, CodeDeploy, CodePipeline, Elastic Beanstalk, X-Ray | 15-18 |
| **7** | Containers & Practice Exam #1 | ECS, CloudWatch + Review | 15-20 |
| **8** | Final Review & Practice Exams #2-3 | All services + Exam prep | 15-20 |

**Total**: 120+ hours over 8 weeks

---

## Week 1: Compute & Fundamentals

### Learning Objectives
- Understand AWS global infrastructure (regions, AZs)
- Master EC2 basics
- Deep dive into Lambda

### Daily Breakdown

**Day 1-2: AWS Fundamentals**
- [ ] AWS Global Infrastructure overview
- [ ] Create AWS account, set up billing alerts
- [ ] Configure MFA and create IAM user

**Day 3-4: EC2**
- [ ] EC2 instance types, pricing models
- [ ] Security groups, key pairs, user data
- [ ] Launch EC2 instance, SSH access
- [ ] Create and attach EBS volume
- [ ] Create AMI and snapshot

**Day 5-7: Lambda**
- [ ] Lambda execution model and triggers
- [ ] Layers, environment variables, versions/aliases
- [ ] Create Lambda function in console
- [ ] Configure Lambda with S3 trigger
- [ ] Use Lambda layers
- [ ] Lambda practice questions

### Study Time: 12-15 hours

---

## Week 2: Storage & Databases

### Learning Objectives
- Master S3 features and security
- Deep dive into DynamoDB
- Understand caching strategies

### Daily Breakdown

**Day 1-3: S3**
- [ ] S3 storage classes and lifecycle policies
- [ ] Bucket policies, ACLs, encryption options
- [ ] Versioning, MFA delete, pre-signed URLs
- [ ] Create bucket with versioning
- [ ] Configure bucket policy and CORS
- [ ] Generate pre-signed URL
- [ ] Set up S3 event notification → Lambda

**Day 4-7: DynamoDB (CRITICAL)**
- [ ] DynamoDB core concepts and data modeling
- [ ] Partition keys, sort keys, indexes
- [ ] Read/write capacity modes
- [ ] DynamoDB Streams, transactions
- [ ] Create table with GSI and LSI
- [ ] Perform CRUD operations
- [ ] Implement DynamoDB Stream → Lambda
- [ ] DynamoDB practice questions (50+)

### Study Time: 15-18 hours

---

## Week 3: Security & IAM

### Learning Objectives
- Master IAM policies and roles
- Understand authentication and authorization
- Learn encryption and secrets management

### Daily Breakdown

**Day 1-3: IAM**
- [ ] IAM policies, roles, and groups
- [ ] Policy evaluation logic
- [ ] STS and temporary credentials
- [ ] Cross-account access
- [ ] Create custom IAM policies
- [ ] Create role for Lambda execution
- [ ] Implement cross-account role assumption
- [ ] IAM policy troubleshooting scenarios

**Day 4-5: Cognito**
- [ ] User pools vs identity pools
- [ ] OAuth 2.0 flows
- [ ] Create user pool
- [ ] Configure identity pool

**Day 6-7: Encryption & Secrets**
- [ ] KMS concepts and envelope encryption
- [ ] Secrets Manager vs Parameter Store
- [ ] Create KMS key and encrypt data
- [ ] Store secret in Secrets Manager
- [ ] Use Parameter Store with Lambda
- [ ] Security practice questions

### Study Time: 15-18 hours

---

## Week 4: API Gateway & Networking

### Learning Objectives
- Master API Gateway configurations
- Understand VPC networking
- Learn API security patterns

### Daily Breakdown

**Day 1-4: API Gateway**
- [ ] REST vs HTTP vs WebSocket APIs
- [ ] Integration types (Lambda, HTTP, AWS)
- [ ] Stages, deployment, and canary releases
- [ ] Throttling, usage plans, API keys
- [ ] CORS, request/response transformations
- [ ] Create REST API → Lambda
- [ ] Configure custom authorizer
- [ ] Implement request validation
- [ ] Set up API Gateway with VPC Link

**Day 5-7: VPC**
- [ ] VPC components (subnets, route tables, IGW)
- [ ] Security groups vs NACLs
- [ ] NAT Gateway, VPC endpoints
- [ ] Create VPC with public/private subnets
- [ ] Deploy Lambda in VPC
- [ ] Networking practice scenarios

### Study Time: 15-18 hours

---

## Week 5: Messaging & Integration

### Learning Objectives
- Understand asynchronous communication patterns
- Master SQS and SNS
- Learn Step Functions

### Daily Breakdown

**Day 1-3: SQS**
- [ ] Standard vs FIFO queues
- [ ] Visibility timeout, DLQ, long polling
- [ ] Message attributes and deduplication
- [ ] Create SQS queue
- [ ] Lambda polling from SQS
- [ ] Configure DLQ

**Day 4-5: SNS & EventBridge**
- [ ] SNS topics and subscriptions
- [ ] Fan-out pattern (SNS → SQS)
- [ ] EventBridge rules and targets
- [ ] Create SNS topic with multiple subscribers
- [ ] Implement EventBridge rule

**Day 6-7: Step Functions**
- [ ] State machine types
- [ ] State types and error handling
- [ ] Create simple workflow
- [ ] Integration patterns practice questions

### Study Time: 12-15 hours

---

## Week 6: CI/CD & Deployment

### Learning Objectives
- Master AWS developer tools
- Understand deployment strategies
- Learn monitoring and logging

### Daily Breakdown

**Day 1-2: CodeCommit & CodeBuild**
- [ ] CodeCommit basics
- [ ] buildspec.yml structure
- [ ] Create CodeCommit repository
- [ ] Create CodeBuild project

**Day 3-4: CodeDeploy & CodePipeline**
- [ ] Deployment types (in-place, blue/green)
- [ ] appspec.yml and lifecycle hooks
- [ ] Pipeline stages and actions
- [ ] Deploy to EC2 with CodeDeploy
- [ ] Create complete CI/CD pipeline

**Day 5-6: Elastic Beanstalk**
- [ ] Environment types and deployment policies
- [ ] .ebextensions configuration
- [ ] Deploy app to Elastic Beanstalk
- [ ] Implement rolling deployment

**Day 7: X-Ray**
- [ ] X-Ray concepts (segments, traces)
- [ ] Sampling rules and annotations
- [ ] Integrate X-Ray with Lambda
- [ ] CI/CD practice questions

### Study Time: 15-18 hours

---

## Week 7: Containers & Practice Exams

### Learning Objectives
- Understand ECS and container deployment
- Take first full practice exam
- Review weak areas

### Daily Breakdown

**Day 1-2: ECS**
- [ ] Task definitions and services
- [ ] Fargate vs EC2 launch type
- [ ] Deploy container to ECS
- [ ] Push image to ECR

**Day 3: CloudWatch**
- [ ] Metrics, logs, and alarms
- [ ] CloudWatch Insights queries
- [ ] Create custom metric
- [ ] Set up log aggregation

**Day 4: First Practice Exam**
- [ ] Take full-length practice exam (130 min)
- [ ] Score and identify weak areas
- [ ] Create focused review list

**Day 5-7: Targeted Review**
- [ ] Review incorrect answers thoroughly
- [ ] Re-study weak domains
- [ ] Practice for weak areas
- [ ] Study relevant FAQs and whitepapers

### Study Time: 15-20 hours

---

## Week 8: Final Review & Practice Exams

### Learning Objectives
- Take multiple practice exams
- Review all services and limits
- Build confidence

### Daily Breakdown

**Day 1: Service Limits & Gotchas**
- [ ] Review: Lambda limits and best practices
- [ ] Review: DynamoDB limits and optimization
- [ ] Review: SQS/SNS limits
- [ ] Review: Common exam gotchas
- [ ] Create cheat sheet of key numbers

**Day 2: Second Practice Exam**
- [ ] Take practice exam #2
- [ ] Review all questions (correct and incorrect)
- [ ] Note new weak areas

**Day 3-4: Targeted Deep Dive**
- [ ] Focus on remaining weak areas
- [ ] Labs for problem topics
- [ ] Review service FAQs
- [ ] Review content for weak areas

**Day 5: Third Practice Exam**
- [ ] Take practice exam #3
- [ ] Aim for 85%+ score
- [ ] Final review of missed questions

**Day 6: Final Review**
- [ ] Review all notes and cheat sheets
- [ ] Quick review of all services
- [ ] Review exam strategies
- [ ] Get good sleep!

**Day 7: Exam Day (or rest day)**
- [ ] Light review in morning
- [ ] Stay calm and confident
- [ ] Take the exam!

### Study Time: 15-20 hours

---

## Weekly Checklist Template

Use this for each week:

```
Week #: ___
Focus: _______________

[ ] Studied all core topics
[ ] Studied relevant documentation
[ ] Completed labs
[ ] Took weekly quiz (score: ___%)
[ ] Reviewed and understood mistakes
[ ] Created study notes/flashcards

Weak areas to review:
1. _______________
2. _______________
3. _______________

Total study hours: ___ / 15 target
```

---

## Daily Study Routine

**Ideal Schedule** (2-3 hours/day):
1. **Warm-up (10 min)**: Review yesterday's notes
2. **Learn (60-90 min)**: Study core concepts and service features
3. **Practice (60-90 min)**: Labs and exercises
4. **Review (20 min)**: Take notes, create flashcards

**Weekend (4-5 hours/day)**:
- Longer projects and labs
- Practice exam questions
- Review week's material

---

## Progress Tracking

| Week | Topics | Labs | Quiz Score | Hours |
|------|--------|------|------------|-------|
| 1 | Compute & Lambda | ☐ | ___% | ___ |
| 2 | Storage & DynamoDB | ☐ | ___% | ___ |
| 3 | Security & IAM | ☐ | ___% | ___ |
| 4 | API Gateway & VPC | ☐ | ___% | ___ |
| 5 | Messaging | ☐ | ___% | ___ |
| 6 | CI/CD | ☐ | ___% | ___ |
| 7 | Containers & PE #1 | ☐ | ___% | ___ |
| 8 | Final Review | ☐ | ___% | ___ |

**Total Hours**: ___ / 120 recommended

---

## Exam Readiness Checklist

You're ready when you can:
- [ ] Score 85%+ on practice exams consistently
- [ ] Explain core services without looking at notes
- [ ] Design architectures for common scenarios
- [ ] Troubleshoot IAM policy issues
- [ ] Write Lambda functions with proper error handling
- [ ] Design DynamoDB tables with appropriate keys
- [ ] Configure CI/CD pipelines
- [ ] Understand all deployment strategies
- [ ] Explain security best practices

---

**Remember**: Quality > Quantity. Understand concepts deeply rather than memorizing facts.

**Good luck!** 🎯
