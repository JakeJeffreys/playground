# 8-Week AWS Developer Certification Study Plan

A detailed week-by-week study schedule for the AWS Certified Developer - Associate exam.

## Week 1: Compute & Fundamentals

### Learning Objectives
- Understand AWS global infrastructure (regions, AZs)
- Master EC2 basics
- Deep dive into Lambda

### Daily Breakdown

**Day 1-2: AWS Fundamentals**
- [ ] Read: AWS Global Infrastructure overview
- [ ] Watch: Course introduction and AWS basics
- [ ] Hands-on: Create AWS account, set up billing alerts
- [ ] Hands-on: Configure MFA and create IAM user

**Day 3-4: EC2**
- [ ] Read: EC2 instance types, pricing models
- [ ] Learn: Security groups, key pairs, user data
- [ ] Hands-on: Launch EC2 instance, SSH access
- [ ] Hands-on: Create and attach EBS volume
- [ ] Hands-on: Create AMI and snapshot

**Day 5-7: Lambda**
- [ ] Read: Lambda execution model and triggers
- [ ] Learn: Layers, environment variables, versions/aliases
- [ ] Hands-on: Create Lambda function in console
- [ ] Hands-on: Configure Lambda with S3 trigger
- [ ] Hands-on: Use Lambda layers
- [ ] Practice: Lambda quiz questions

### Study Time: 12-15 hours

---

## Week 2: Storage & Databases

### Learning Objectives
- Master S3 features and security
- Deep dive into DynamoDB
- Understand caching strategies

### Daily Breakdown

**Day 1-3: S3**
- [ ] Read: S3 storage classes and lifecycle policies
- [ ] Learn: Bucket policies, ACLs, encryption options
- [ ] Learn: Versioning, MFA delete, pre-signed URLs
- [ ] Hands-on: Create bucket with versioning
- [ ] Hands-on: Configure bucket policy and CORS
- [ ] Hands-on: Generate pre-signed URL
- [ ] Hands-on: Set up S3 event notification → Lambda

**Day 4-7: DynamoDB (CRITICAL)**
- [ ] Read: DynamoDB core concepts and data modeling
- [ ] Learn: Partition keys, sort keys, indexes
- [ ] Learn: Read/write capacity modes
- [ ] Learn: DynamoDB Streams, transactions
- [ ] Hands-on: Create table with GSI and LSI
- [ ] Hands-on: Perform CRUD operations
- [ ] Hands-on: Implement DynamoDB Stream → Lambda
- [ ] Practice: DynamoDB quiz questions (do 50+)

### Study Time: 15-18 hours

---

## Week 3: Security & IAM

### Learning Objectives
- Master IAM policies and roles
- Understand authentication and authorization
- Learn encryption and secrets management

### Daily Breakdown

**Day 1-3: IAM**
- [ ] Read: IAM policies, roles, and groups
- [ ] Learn: Policy evaluation logic
- [ ] Learn: STS and temporary credentials
- [ ] Learn: Cross-account access
- [ ] Hands-on: Create custom IAM policies
- [ ] Hands-on: Create role for Lambda execution
- [ ] Hands-on: Implement cross-account role assumption
- [ ] Practice: IAM policy troubleshooting scenarios

**Day 4-5: Cognito**
- [ ] Read: User pools vs identity pools
- [ ] Learn: OAuth 2.0 flows
- [ ] Hands-on: Create user pool
- [ ] Hands-on: Configure identity pool

**Day 6-7: Encryption & Secrets**
- [ ] Read: KMS concepts and envelope encryption
- [ ] Learn: Secrets Manager vs Parameter Store
- [ ] Hands-on: Create KMS key and encrypt data
- [ ] Hands-on: Store secret in Secrets Manager
- [ ] Hands-on: Use Parameter Store with Lambda
- [ ] Practice: Security quiz questions

### Study Time: 15-18 hours

---

## Week 4: API Gateway & Networking

### Learning Objectives
- Master API Gateway configurations
- Understand VPC networking
- Learn API security patterns

### Daily Breakdown

**Day 1-4: API Gateway**
- [ ] Read: REST vs HTTP vs WebSocket APIs
- [ ] Learn: Integration types (Lambda, HTTP, AWS)
- [ ] Learn: Stages, deployment, and canary releases
- [ ] Learn: Throttling, usage plans, API keys
- [ ] Learn: CORS, request/response transformations
- [ ] Hands-on: Create REST API → Lambda
- [ ] Hands-on: Configure custom authorizer
- [ ] Hands-on: Implement request validation
- [ ] Hands-on: Set up API Gateway with VPC Link

**Day 5-7: VPC**
- [ ] Read: VPC components (subnets, route tables, IGW)
- [ ] Learn: Security groups vs NACLs
- [ ] Learn: NAT Gateway, VPC endpoints
- [ ] Hands-on: Create VPC with public/private subnets
- [ ] Hands-on: Deploy Lambda in VPC
- [ ] Practice: Networking scenarios

### Study Time: 15-18 hours

---

## Week 5: Messaging & Integration

### Learning Objectives
- Understand asynchronous communication patterns
- Master SQS and SNS
- Learn Step Functions

### Daily Breakdown

**Day 1-3: SQS**
- [ ] Read: Standard vs FIFO queues
- [ ] Learn: Visibility timeout, DLQ, long polling
- [ ] Learn: Message attributes and deduplication
- [ ] Hands-on: Create SQS queue
- [ ] Hands-on: Lambda polling from SQS
- [ ] Hands-on: Configure DLQ

**Day 4-5: SNS & EventBridge**
- [ ] Read: SNS topics and subscriptions
- [ ] Learn: Fan-out pattern (SNS → SQS)
- [ ] Learn: EventBridge rules and targets
- [ ] Hands-on: Create SNS topic with multiple subscribers
- [ ] Hands-on: Implement EventBridge rule

**Day 6-7: Step Functions**
- [ ] Read: State machine types
- [ ] Learn: State types and error handling
- [ ] Hands-on: Create simple workflow
- [ ] Practice: Integration patterns quiz

### Study Time: 12-15 hours

---

## Week 6: CI/CD & Deployment

### Learning Objectives
- Master AWS developer tools
- Understand deployment strategies
- Learn monitoring and logging

### Daily Breakdown

**Day 1-2: CodeCommit & CodeBuild**
- [ ] Read: CodeCommit basics
- [ ] Learn: buildspec.yml structure
- [ ] Hands-on: Create CodeCommit repository
- [ ] Hands-on: Create CodeBuild project

**Day 3-4: CodeDeploy & CodePipeline**
- [ ] Read: Deployment types (in-place, blue/green)
- [ ] Learn: appspec.yml and lifecycle hooks
- [ ] Learn: Pipeline stages and actions
- [ ] Hands-on: Deploy to EC2 with CodeDeploy
- [ ] Hands-on: Create complete CI/CD pipeline

**Day 5-6: Elastic Beanstalk**
- [ ] Read: Environment types and deployment policies
- [ ] Learn: .ebextensions configuration
- [ ] Hands-on: Deploy app to Elastic Beanstalk
- [ ] Hands-on: Implement rolling deployment

**Day 7: X-Ray**
- [ ] Read: X-Ray concepts (segments, traces)
- [ ] Learn: Sampling rules and annotations
- [ ] Hands-on: Integrate X-Ray with Lambda
- [ ] Practice: CI/CD quiz questions

### Study Time: 15-18 hours

---

## Week 7: Containers & Practice Exams

### Learning Objectives
- Understand ECS and container deployment
- Take first full practice exam
- Review weak areas

### Daily Breakdown

**Day 1-2: ECS**
- [ ] Read: Task definitions and services
- [ ] Learn: Fargate vs EC2 launch type
- [ ] Hands-on: Deploy container to ECS
- [ ] Hands-on: Push image to ECR

**Day 3: CloudWatch**
- [ ] Read: Metrics, logs, and alarms
- [ ] Learn: CloudWatch Insights queries
- [ ] Hands-on: Create custom metric
- [ ] Hands-on: Set up log aggregation

**Day 4: First Practice Exam**
- [ ] Take full-length practice exam (130 min)
- [ ] Score and identify weak areas
- [ ] Create focused review list

**Day 5-7: Targeted Review**
- [ ] Review incorrect answers thoroughly
- [ ] Re-study weak domains
- [ ] Hands-on practice for weak areas
- [ ] Read relevant FAQs and whitepapers

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
- [ ] Hands-on labs for problem topics
- [ ] Review service FAQs
- [ ] Watch recap videos

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

[ ] Completed all video lectures
[ ] Read all assigned documentation
[ ] Completed all hands-on labs
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
2. **Learn (60-90 min)**: Watch videos or read docs
3. **Practice (60-90 min)**: Hands-on labs
4. **Review (20 min)**: Take notes, create flashcards

**Weekend (4-5 hours/day)**:
- Longer hands-on projects
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
