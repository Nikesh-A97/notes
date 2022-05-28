# One line describing the service
---
##### [[Amazon IAM|IAM]] 
- Define **permissions** for users and groups using **policies** and roles to be used for **access control** to **AWS Resources**

---
##### [[Amazon EC2|EC2]]
- **VMs** that provide **compute capacity** for workloads

---
##### [[Amazon Elastic Block Store|EBS Volume]]
- A **network drive** that is attached to an **EC2** instance for data persistence

---
##### AMI
- A **customization** of your **EC2** instance

---

##### [[Amazon Elastic File System|EFS]]
- A **managed network file system** that can mount to multiple EC2s

---
##### [[AWS Elastic Load Balancing|ELB]]
- Spread load across instances

---
##### [[Amazon EC2 Auto Scaling|ASG]]
- **Auto-scales** EC2 instances that depends on **demand**

---
##### [[AWS Simple Storage Service (S3)|S3]]
- A **bucket (directory)** that stores **objects (files)**

---
##### [[AWS Storage Gateway|SG]]
- **Hybrid storage** between on-prem and cloud to extend to S3

---
##### [[Amazon RDS|RDS]]
- **Managed** DB for SQL as a query language

---
##### [[Amazon Aurora|Aurora]]
- **Proprietary Optimized Cloud DB** for PostgreSQL & MySQL

---
##### [[Amazon ElastiCache|ElastiCache]]
- **In memory DB** for **high performance** & **low latency**

---
##### [[Amazon DynamoDB|DynamoDB]]
- **Serverless NoSQL DB** with **low latency**

---
##### [[Amazon Redshift|Redshift]]
- A **DW** for **analytics** and **DW** which stores data in **columns**

---
##### [[Amazon Athena|Athena]]
- **Serverless DB** with **SQL** to query data in **S3**

---
##### DMS
- **Quickly** and **Securely migrate DBs** to AWS

---
##### [[Amazon Elastic Container Service|ECS]]
- Launch **Docker** contianers and must provision **EC2** 

---
##### [[AWS Fargate|Fargate]]
- Same thing as *ECS* but **manged & serverless**

---
##### [[Amazon Elastic Container Registry|ECR]]
- **Store** docker images so they can be **run** by *fargate or ECS*

---
##### [[AWS Lambda|Lambda]]
- **Serverless** compute used to run functions

---
##### [[AWS Cloud Formation|CloudFormation]]
- Use **templates** to **outline** AWS **infrastructure** or **resources** 

---
##### [[AWS Elastic Beanstalk|Elastic Beanstalk]]
- **Managed** service in a developer centric view to deploy an app

---
##### [[AWS CodeDeploy|CodeDeploy]]
- Deploy application **automatically**

---
##### Systems Manager
- Manage **EC2** & **On-premise** systems for **patching** and **running commands** at scale

---
##### AWS OpsWorks
- Chef & Puppert help perform server configs automatically for **EC2** or other standard AWS resources

---
##### [[Amazon Route 53|Route53]]
- **Managed DNS** which **routes** users using policies

---
##### [[Amazon Cloud Front|CloudFront]]
- **CDN** , with **low latency** & **high transfer** speeds utilizing edge caches

---
##### [[AWS Global Accelerator|Global Acc]]
- Use **AnycastIP** to optimize route to you apps to improve availability and performance

---
##### [[Amazon Simple Queue Service|SQS]]
- **Decouple** apps using a queing service between apps

---
##### [[Amazon Simple Notification Service|SNS]]
- *event publishes* send **messages** to *subscribers* (http. emails, SQS queues, lambda functions)

---
##### [[Amazon Cloud Watch|CloudWatch]]
- Metrics for *every* service in AWS and create dashboards

---
##### CloudWatch Alarms
- **Trigger notifications** for any **metrics** and apply some **actions** to services such as ASG, EC2, SNS

---
##### CloudWatch Logs
- **Collect Logs** from services such as Elastic Beanstalk, ECS, $\lambda$, Route53 DNS quereis 

---
##### CloudWatch Events
- **Schedule CRON jobs** or **react** to service doing something, trigger $\lambda$ functions, send SQS/SNS messages

---
##### Amazon Event Bridge
- **Serverless** event bus to build event driven applications at scale

-----
##### [[AWS Cloud Trail]]
- **Governance, Compliance & Audit** for AWS account with **history** of **events** & **API Calls** 

---
##### [[AWS X-Ray|X-Ray]]
- **Visual Analysis** for apps to troubleshoot performance

---
##### [[AWS Health Dashboard]]
- Regular 
	- Shows health of all regions and all services
- Personal
	- Provides alerts and guidance when AWS experiences events that may impact you

---
##### [[Amazon VPC|VPC]]
- **Private network** to deploy your resources

---
##### [[AWS Shield|Shield]]
- **DDoS Protection**

---
##### [[Amazon Web Application Firewall|WAF]]
- A **firewall** to protect web apps and other AWS services from atks 

---
##### [[AWS Key Management Service|KMS]]
- **AWS Manages Encryption Keys** to use for AWS services such as EBS, S3, Redshift, RDS, EFS

---
##### AWS Secrets Manager
- **Store sercrets**, rotate, generate ($\lambda$), integrate them, and mostly used for RDS encyption 

---
#####  [[AWS Artifact|Artifact]]
- Portal that **provides** customers with **on-demand access** to AWS **Compliance Docs**

---
##### [[Amazon GuardDuty|GuardDuty]]
- **Threat Discovery** for AWS account and uses **ML algorithms**

---
##### [[Amazon Inspector|Inpsector]]
- **Security Assesments** for **EC2**

---
##### [[AWS Config|Config]]
- Helps with **Auditing** & **Recording Compliance** & recprds **Config changes** over time

---
##### Amazon Macie
- **Managed** data **sucrity & privacy** service that uses **ML** to identify **Personal Identifiable information**

---
##### [[AWS Organizations|Organizations]]
- **Manage multiple accounts** and offers **consolidated billing** for savings & **restrict** access using **SCPs**