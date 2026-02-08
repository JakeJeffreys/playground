# AWS Certified Developer - Associate Study Guide

Study materials and resources for preparing for the AWS Certified Developer - Associate (DVA-C02) exam.

## Exam Overview

- **Exam Code**: DVA-C02
- **Duration**: 130 minutes
- **Format**: 65 questions (multiple choice and multiple response)
- **Passing Score**: 720/1000
- **Cost**: $150 USD
- **Validity**: 3 years

## Exam Domains

| Domain | Weight |
|--------|--------|
| Development with AWS Services | 32% |
| Security | 26% |
| Deployment | 24% |
| Troubleshooting and Optimization | 18% |

## Study Timeline

**Recommended: 6-8 weeks** (10-15 hours/week)

- **Weeks 1-2**: Core services (EC2, S3, Lambda, DynamoDB)
- **Weeks 3-4**: Security, IAM, and networking
- **Weeks 5-6**: CI/CD, deployment, and monitoring
- **Weeks 7-8**: Practice exams and review weak areas

## Core Services to Master

### Compute
- **Lambda** - Event-driven serverless compute
  - Execution models, triggers, layers
  - Environment variables and configuration
  - Cold starts and optimization
  - Integration with other services
- **EC2** - Virtual servers
  - Instance types and pricing models
  - Security groups and networking
  - User data and metadata
- **Elastic Beanstalk** - Platform as a Service
  - Deployment strategies (all at once, rolling, immutable)
  - Configuration files (.ebextensions)
  - Environment tiers (web server vs worker)

### Storage
- **S3** - Object storage
  - Bucket policies vs IAM policies
  - Versioning, lifecycle policies
  - Encryption (SSE-S3, SSE-KMS, SSE-C)
  - Pre-signed URLs
  - Event notifications
  - Storage classes
- **EBS** - Block storage
  - Volume types (gp3, io2, etc.)
  - Snapshots and encryption

### Databases
- **DynamoDB** - NoSQL database (CRITICAL)
  - Partition keys and sort keys
  - GSI vs LSI
  - Read/write capacity modes (provisioned vs on-demand)
  - DynamoDB Streams
  - Transactions and batch operations
  - Eventual vs strong consistency
- **RDS** - Relational databases
  - Read replicas vs Multi-AZ
  - Backup and recovery
- **ElastiCache** - In-memory caching
  - Redis vs Memcached
  - Use cases and patterns

### Messaging & Integration
- **SQS** - Message queuing
  - Standard vs FIFO queues
  - Visibility timeout
  - Dead letter queues
  - Long polling vs short polling
- **SNS** - Pub/sub messaging
  - Topics and subscriptions
  - Fan-out patterns
- **EventBridge** - Event bus
  - Rules and targets
  - Event patterns
- **Step Functions** - Workflow orchestration
  - State types
  - Error handling

### Developer Tools
- **CodeCommit** - Git repository
- **CodeBuild** - Build service
  - buildspec.yml
- **CodeDeploy** - Deployment automation
  - Deployment types (in-place, blue/green)
  - appspec.yml
  - Hooks and lifecycle events
- **CodePipeline** - CI/CD orchestration
- **X-Ray** - Distributed tracing
  - Segments and subsegments
  - Sampling rules
  - Annotations and metadata

### Security & IAM
- **IAM** - Identity and Access Management
  - Policies (identity-based, resource-based)
  - Roles and trust relationships
  - Policy evaluation logic
  - STS and temporary credentials
- **Cognito** - User authentication
  - User pools vs identity pools
  - OAuth 2.0 flows
- **KMS** - Key Management Service
  - CMKs and data keys
  - Envelope encryption
- **Secrets Manager** - Secret rotation
- **Parameter Store** - Configuration management

### Monitoring & Logging
- **CloudWatch**
  - Metrics, alarms, and dashboards
  - Logs and log groups
  - Events (now EventBridge)
  - Insights and queries
- **CloudTrail** - API auditing

### Networking
- **VPC** - Virtual Private Cloud
  - Subnets (public vs private)
  - NAT Gateway vs NAT Instance
  - Security groups vs NACLs
- **API Gateway** - API management
  - REST vs HTTP vs WebSocket APIs
  - Integration types (Lambda, HTTP, AWS service)
  - Stages and deployment
  - Throttling and usage plans
  - Authentication (IAM, Cognito, Lambda authorizers)

### Containers
- **ECS** - Container orchestration
  - Task definitions
  - Fargate vs EC2 launch types
- **ECR** - Container registry

## Study Resources

### Official AWS Resources
- [AWS Certified Developer Official Study Guide](https://www.amazon.com/Certified-Developer-Official-Study-Guide/dp/1119508193)
- [AWS Developer Center](https://aws.amazon.com/developer/)
- [AWS Whitepapers](https://aws.amazon.com/whitepapers/)
  - AWS Well-Architected Framework
  - AWS Security Best Practices
- [AWS FAQs](https://aws.amazon.com/faqs/) - Read FAQs for core services

### Online Courses
- **A Cloud Guru** - AWS Certified Developer Associate
- **Udemy** - Stephane Maarek's Ultimate AWS Certified Developer Associate
- **Linux Academy / A Cloud Guru**
- **AWS Skill Builder** - Free official training

### Practice Exams
- **Tutorials Dojo** - Highly recommended practice tests
- **Whizlabs** - Practice exams
- **AWS Official Practice Exam** - $20, 20 questions

### Hands-on Labs
- **AWS Free Tier** - Practice with actual services
- **A Cloud Guru Playground**
- **Qwiklabs**

### Documentation to Read
- Lambda Developer Guide
- DynamoDB Developer Guide
- API Gateway Developer Guide
- Elastic Beanstalk Developer Guide

## Study Tips

### 1. Hands-on Practice is Essential
- Create an AWS account and use Free Tier
- Build real projects using the services
- Don't just read - actually deploy and configure services
- Break things and learn how to troubleshoot

### 2. Focus on These High-Impact Areas
- **Lambda** - Appears in many scenarios
- **DynamoDB** - Critical for developer exam
- **IAM** - Understand policies deeply
- **API Gateway** - Integration patterns
- **CI/CD tools** - CodePipeline, CodeDeploy, CodeBuild

### 3. Understand Integration Patterns
- How services work together (Lambda + API Gateway + DynamoDB)
- Event-driven architectures
- Asynchronous vs synchronous processing

### 4. Know the "Why"
- Don't just memorize - understand when to use each service
- Learn trade-offs between services (SQS vs SNS vs EventBridge)
- Understand cost optimization strategies

### 5. Practice Exam Strategy
- Take practice exams under timed conditions
- Review explanations for ALL questions (even correct ones)
- Identify patterns in wrong answers
- Focus on weak areas

### 6. Common Exam Scenarios
- Troubleshooting deployment failures
- Securing applications and data
- Optimizing performance and cost
- Implementing CI/CD pipelines
- Handling errors and retries

## Sample Projects to Build

### Project 1: Serverless API
**Goal**: Build a REST API with CRUD operations
- API Gateway → Lambda → DynamoDB
- IAM authentication
- CloudWatch logging

### Project 2: Image Processing Pipeline
**Goal**: Process uploaded images asynchronously
- S3 upload → Lambda trigger → Process → Store in S3
- SNS notifications
- Error handling with DLQ

### Project 3: CI/CD Pipeline
**Goal**: Automated deployment pipeline
- CodeCommit → CodeBuild → CodeDeploy
- Automated testing
- Blue/green deployment

### Project 4: Microservices with Containers
**Goal**: Deploy containerized app
- ECS with Fargate
- Application Load Balancer
- ECR for container images

## Key Concepts to Memorize

### Lambda Limits
- Memory: 128 MB - 10,240 MB
- Timeout: 15 minutes max
- Deployment package: 50 MB (zipped), 250 MB (unzipped)
- /tmp storage: 512 MB - 10,240 MB

### DynamoDB
- Item size limit: 400 KB
- Batch operations: 25 items max
- Query: Only on partition key + optional sort key
- Scan: Reads entire table (avoid in production)

### SQS
- Default visibility timeout: 30 seconds (max 12 hours)
- Message retention: 4 days default (1 min - 14 days)
- Message size: 256 KB max
- FIFO throughput: 300 TPS (3000 with batching)

### S3
- Object size: 5 TB max
- Single PUT: 5 GB max (use multipart for larger)
- Pre-signed URL: Valid up to 7 days (with IAM credentials)

## Common Gotchas

1. **Lambda cold starts** - Use provisioned concurrency for latency-sensitive apps
2. **DynamoDB hot partitions** - Design partition keys carefully
3. **S3 eventual consistency** - Now strong consistency for all operations (as of Dec 2020)
4. **IAM policy evaluation** - Explicit deny always wins
5. **API Gateway timeout** - 29 seconds max
6. **CodeDeploy hooks** - Know the order of lifecycle events

## Exam Day Tips

- **Time management**: 2 minutes per question, flag and move on
- **Read carefully**: Watch for "MOST cost-effective", "LEAST operational overhead"
- **Eliminate wrong answers**: Usually can eliminate 2 options quickly
- **AWS prefers managed services**: When in doubt, choose the more managed option
- **Security first**: If an option is insecure, it's wrong

## Next Steps After Passing

1. **Build real projects** using certified knowledge
2. **Pursue other certifications**:
   - AWS Solutions Architect Associate
   - AWS DevOps Engineer Professional
3. **Stay current** with AWS updates (re:Invent, blogs)
4. **Share knowledge** and mentor others

## Additional Resources

- [AWS Developer Blog](https://aws.amazon.com/blogs/developer/)
- [AWS This Week](https://acloudguru.com/videos/aws-this-week)
- [r/AWSCertifications](https://www.reddit.com/r/AWSCertifications/)
- [AWS re:Post](https://repost.aws/) - Community Q&A

## Useful Links

- [Exam Guide (Official)](https://aws.amazon.com/certification/certified-developer-associate/)
- [Sample Questions](https://d1.awsstatic.com/training-and-certification/docs-dev-associate/AWS-Certified-Developer-Associate_Sample-Questions.pdf)
- [Service Limits Documentation](https://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html)

---

**Good luck with your certification journey!** 🚀

Remember: Consistent daily study and hands-on practice are more effective than cramming.
