# AWS Cloud notes

## Contents
  - [Module 1 : Cloud Concepts Overview](#module-1--cloud-concepts-overview)
  - [Module 2 : Cloud Economics & Billing](#module-2--cloud-economics--billing)
  - [Module 3 : AWS Global Infrastructure Overview](#module-3--aws-global-infrastructure-overview)
  - [Module 4 : AWS Cloud Security](#module-4--aws-cloud-security)
  - [Module 5 : Networking and Content Delivery](#module-5--networking-and-content-delivery)
  - [Module 6 : Compute](#module-6--compute)
  - [Module 7 : Storage](#module-7--storage)
  - [Module 8 : Databases](#module-8--databases)
  - [Module 9 : Cloud Architecture](#module-9--cloud-architecture)
  - [Module 10 : Auto-Scaling and Monitoring](#module-10--auto-scaling-and-monitoring)

---

## Module 1 : Cloud Concepts Overview

[ To the top ](#contents)

### Cloud Computing
- It is the on demand delivery of computing power, DB storage, and other resources
- Pay-as-you-go pricing
- Using computers/resources owned by the service provider
- Think of it as software not hardware

### Hardware vs Software

<h4 style="color:#f08f18"> Hardware </h4>

- Requires space, staff, security, planning, and capital expenditure, as it's physical
- Takes a long time to acquire, provision and maintain the physical infrastructure
- If full capacity of hardware not being used --> money wasted.
- If you require more capacity --> downtime on services while upgrading 

<h4 style="color:#f08f18"> Software </h4>

- Thinking of it as software, select services that match needs required 
- Pay for what you use, and use it when you need to
- Flexible with scaling capacity

### Cloud Service Models
<img src="diag/cloudServiceModels.png" width="500" height="100">

### Advantages of Cloud Computing
<ul>
	<li><b style="color:#f08f18">Trade capital expense for variable expense</b></li>
	<ul>
		<li>Pay only for when you use and consume resource and save on physical hardware</li>
	</ul>
  <li><b style="color:#f08f18">Massive Economies of Scale</b></li>
	<ul>
		<li>Benefit from the aggregate usage from all customers, pass savings onto customers</li>
	</ul>
  <li><b style="color:#f08f18">Variable Capacity</b></li>
	<ul>
		<li>Scale up/down as required</li>
	</ul>
  <li><b style="color:#f08f18">Speed & Agility</b></li>
	<ul>
		<li>Resources that are required are obtainable within minutes as opposed to weeks</li>
	</ul>
  <li><b style="color:#f08f18">No spending on running/maintaining physical DCs</b></li>
	<ul>
		<li>All handled by the cloud DCs</li>
	</ul>
  <li><b style="color:#f08f18">Global</b></li>
	<ul>
		<li>Deploy applications globally</li>
	</ul>
</ul>

### What are web services
- A piece of software that makes itself available of the internet
- Uses a standardized format such as <text style="color:#f08f18">XML</text> or <text style="color:#f08f18">JSON</text> for API responses

### What is AWS
- A secure cloud platform that offers cloud-based products
- Flexible and services work together as building blocks

### Categories of AWS services and covered in the course
<p>
<img src="diag/awsService.png" width="572" height="273">
</p>

### Ways to interact with AWS
- AWS Management Console
- Command Line Interface (AWS CLI)
- SDKs

### AWS Cloud Adoption Framework (CAF)
- People, process and technology must be in alignment
- For business to migrate to the cloud, they must understand different states within the businesses
- AWS CAF provides guidance and best practices to help build a successful approach to cloud computing 

<h4 style="color:#f08f18"> Business </h4>

- Stakeholders ensure strategies and goals align with IT 

<h4 style="color:#f08f18"> People </h4>

- HR/managers/etc prioritize staffing, training and organizational change 

<h4 style="color:#f08f18"> Governance </h4>

- CIO, enterprise architects, BAs, etc use AWS to align goals and minimize risk

<h4 style="color:#f08f18"> Platform </h4>

- CTO, IT managers, solutions architects must understand nature of IT systems and relationships.
- Describe the environment in detail

<h4 style="color:#f08f18"> Security </h4>

- CISO, IT security, can use AWS framework to meet whatever security objectives they need

<h4 style="color:#f08f18"> Operations </h4>

- IT operations/support managers, support define how business will be conducted

--- 

## Module 2 : Cloud Economics & Billing

[ To the top ](#contents)

### AWS pricing model
<ul>
	<li><b style="color:#f08f18">Compute</b></li>
	<ul>
		<li>Charged per hour/second</li>
    <li>Varies by instance</li>
	</ul>
  <li><b style="color:#f08f18">Storage</b></li>
	<ul>
		<li>Charged typically per GB</li>
	</ul>
  <li><b style="color:#f08f18">Data Transfer</b></li>
	<ul>
		<li>Outbound aggregated and charged</li>
    <li>Inbound no charge</li>
    <li>Charged typically per GB</li>
	</ul>
</ul>

### Paying for AWS
- Pay for what you use
- Pay less when you reserver
- Pay less when you use more (Tiered pricing)
- No upfront expenses

### Total Cost of Ownership (TCO)

This is the financial estimate to help identify direct and indirect cost of a system.
The considerations are
- Server Costs
- Storage Costs
- Network Costs
- IT Labor Costs

### Pricing calculator
- The estimates and costs of everything for AWS cloud
- A bunch of benefits from reduced spending to agile business processes 

### AWS Organizations
- Account management service for multiple AWS accounts
- OU - A branch for multiple accounts
- Apply security and service polices for accounts
- Create Organization -> Create Organization units -> Create service control policies -> Test restrictions
- Can be accessed from AWS management console, AWS CLI, SDKs and APIs

### AWS Billing
- Just tools to look at billing with various tools that show what you are using
- Tools : AWS -/ Budgets / Cost and Usage Report  / Cost Explorer

### AWS Support
- Account assistance
  - AWS support concierge
- Best practices
  - AWS Trusted Advisor
- Proactive guidance
  - Technical Account manager
- Support Plans : Basic, Dev, Business and Enterprise

--- 

## Module 3 : AWS Global Infrastructure Overview

[ To the top ](#contents)

### Global Infrastructure
- Designed and built to deliver a flexible, reliable, scalable and secure cloud computing environment
- Provides high quality global network performance

### AWS Region
- A geographical area
- Consist of two or more Availability zones
- An availability zone contains 1 ore more DC
- Data is not replicated outside the given region

### Selecting a Region
- Consider the data governance and legal requirements restricts regions
- Proximity to customers affect latency
- Not all AWS services are available in every region
- Costs vary by region

### Availability Zones
- Each zone is an isolated partition of the AWS infrastructure
- Consists of discrete data centers
- Designed for fault isolation
- Interconnected by a private network
- Recommend replicating data/resources across zones

### AWS infrastructure features
<ul>
	<li><b style="color:#f08f18">Elasticity and scalability</b></li>
	<ul>
		<li>Dynamically adjust capacity and scalable to accommodate growth</li>
	</ul>
  <li><b style="color:#f08f18">Fault Tolerance</b></li>
	<ul>
		<li>Continues to operate in the presence of a failure</li>
    <li>Built in redundancy</li>
	</ul>
  <li><b style="color:#f08f18">High Availability</b></li>
	<ul>
		<li>High level of operational performance</li>
    <li>Minimal downtime</li>
    <li>Little to no human intervention</li>
	</ul>
</ul>

### AWS Storage Service Category
<ul>
	<li><b style="color:#f08f18">Amazon S3</b></li>
	<ul>
		<li>Service that offers scalability, data availability, security and performance</li>
	</ul>
  <li><b style="color:#f08f18">Amazon EBS</b></li>
	<ul>
		<li>High performance block storage designed to be used with EC2 for intensive workloads</li>
	</ul>
  <li><b style="color:#f08f18">Amazon EFS</b></li>
	<ul>
		<li>Scalable elastic network file system</li>
	</ul>
  <li><b style="color:#f08f18">Amazon Glacier</b></li>
	<ul>
		<li>Low cost AWS S3 storage class for data archiving and long term backup</li>
	</ul>
</ul>

### AWS Compute Service Category
<ul>
	<li><b style="color:#f08f18">Amazon EC2</b></li>
	<ul>
		<li>Resizable compute capacity as VMs in the cloud</li>
	</ul>
  <li><b style="color:#f08f18">Amazon EC2 Auto Scaling</b></li>
	<ul>
		<li>Automatically add or remove EC2 instances as desired</li>
	</ul>
  <li><b style="color:#f08f18">Amazon ECS</b></li>
	<ul>
		<li>Scalable containers that support docker containers</li>
	</ul>
  <li><b style="color:#f08f18">Amazon EC2 Registry</b></li>
	<ul>
		<li>Make it easier to store, manage and deploy docker containers</li>
	</ul>
  <li><b style="color:#f08f18">Amazon Elastic Beanstalk</b></li>
	<ul>
		<li>Deploying and scaling web applications</li>
	</ul>
  <li><b style="color:#f08f18">Amazon EKS</b></li>
	<ul>
		<li>For applications that use Kubernetes on AWS</li>
	</ul>
  <li><b style="color:#f08f18">AWS Lambda</b></li>
	<ul>
		<li>Run code without provisioning or managing servers</li>
	</ul>
  <li><b style="color:#f08f18">AWS Fargate</b></li>
	<ul>
		<li>For ECS to run containers without managing clusters or servers</li>
	</ul>
</ul>

### AWS Database Service Category
<ul>
	<li><b style="color:#f08f18">Amazon Relational DB (RDB) Service</b></li>
	<ul>
		<li>RDB in the cloud</li>
	</ul>
  <li><b style="color:#f08f18">Amazon Aurora</b></li>
	<ul>
		<li>MySQL and postgresSQL compatible RDB</li>
	</ul>
  <li><b style="color:#f08f18">Amazon Redshift</b></li>
	<ul>
		<li>Enables to run analytical queries against large sets of data</li>
	</ul>
  <li><b style="color:#f08f18">Amazon DynamoDB</b></li>
	<ul>
		<li>A K-V document noSQL DB</li>
	</ul>
</ul>

### AWS Networking & Content Delivery Service Category
<ul>
	<li><b style="color:#f08f18">Amazon VPC</b></li>
	<ul>
		<li>Launch AWS resources in a virtual network you define</li>
	</ul>
  <li><b style="color:#f08f18">Elastic Load Balancing</b></li>
	<ul>
		<li>Automatically distribute incoming traffic across multiple targets such as EC2 or lambda</li>
	</ul>
  <li><b style="color:#f08f18">Amazon CloudFront</b></li>
	<ul>
		<li>A CDN that delivers data, videos, APIs, and more globally</li>
	</ul>
  <li><b style="color:#f08f18">AWS Transit Gateway</b></li>
	<ul>
		<li>Connect VPC and on-premise network to a centrally managed gateway</li>
	</ul>
  <li><b style="color:#f08f18">Amazon Route 53</b></li>
	<ul>
		<li>Cloud domain name system used to route end users to internet applications</li>
	</ul>
  <li><b style="color:#f08f18">AWS Direct Connect</b></li>
	<ul>
		<li>A dedicated private network connection from your own DCs to AWS</li>
	</ul>
  <li><b style="color:#f08f18">AWS VPN</b></li>
	<ul>
		<li>A VPN to the AWS global network</li>
	</ul>
</ul>

### AWS Security, Identity & Compliance Service Category
<ul>
	<li><b style="color:#f08f18">AWS IAM</b></li>
	<ul>
		<li>Securely access AWS services and resources</li>
	</ul>
  <li><b style="color:#f08f18">AWS Organizations</b></li>
	<ul>
		<li>Manage multiple AWS accounts and restrict and manage services for accounts</li>
	</ul>
  <li><b style="color:#f08f18">Amazon Cognito</b></li>
	<ul>
		<li>Add user authentication to web and mobile applications</li>
	</ul>
  <li><b style="color:#f08f18">AWS Artifact</b></li>
	<ul>
		<li>Provides access to AWS security reports and online agreements</li>
	</ul>
  <li><b style="color:#f08f18">AWS Key Management Service</b></li>
	<ul>
		<li>Create and manage encryption keys, control encryption for all applications and services</li>
	</ul>
  <li><b style="color:#f08f18">AWS Shield</b></li>
	<ul>
		<li>Protection for DDoS on applications running on AWS</li>
	</ul>
</ul>

### AWS Cost Management Service Category
<ul>
	<li><b style="color:#f08f18">AWS Cost and Usage Report</b></li>
	<ul>
		<li>Comprehensive AWS service costs and usage data</li>
	</ul>
  <li><b style="color:#f08f18">AWS Budgets</b></li>
	<ul>
		<li>Set custom budgets for AWS services and alerts</li>
	</ul>
  <li><b style="color:#f08f18">AWS Cost Explorer</b></li>
	<ul>
		<li>Visualize, understand and manage AWS service usage overtime</li>
	</ul>
</ul>

### AWS Management & Governance Service Category
<ul>
	<li><b style="color:#f08f18">AWS Management Console</b></li>
	<ul>
		<li>Web based user interface used to manage your AWS account</li>
	</ul>
  <li><b style="color:#f08f18">AWS Config</b></li>
	<ul>
		<li>Track service inventory and changes</li>
	</ul>
  <li><b style="color:#f08f18">Amazon CloudWatch</b></li>
	<ul>
		<li>Monitor resources and applications</li>
	</ul>
  <li><b style="color:#f08f18">AWS Auto Scaling</b></li>
	<ul>
		<li>Automatically scale resources to meet demand</li>
	</ul>
  <li><b style="color:#f08f18">AWS CLI</b></li>
	<ul>
		<li>Unified tool to manage AWS services</li>
	</ul>
  <li><b style="color:#f08f18">AWS Trusted Advisor</b></li>
	<ul>
		<li>Optimize performance and security</li>
	</ul>
  <li><b style="color:#f08f18">AWS Well-Architected Tool</b></li>
	<ul>
		<li>Provides help to review and manage workloads</li>
	</ul>
  <li><b style="color:#f08f18">AWS Cloud Trail</b></li>
	<ul>
		<li>Tracks user activity and API usage across accounts</li>
	</ul>
</ul>

--- 

## Module 4 : AWS Cloud Security

[ To the top ](#contents)

--- 

## Module 5 : Networking and Content Delivery

[ To the top ](#contents)

--- 

## Module 6 : Compute

[ To the top ](#contents)

--- 

## Module 7 : Storage

[ To the top ](#contents)

--- 

## Module 8 : Databases

[ To the top ](#contents)

--- 

## Module 9 : Cloud Architecture

[ To the top ](#contents)

--- 

## Module 10 : Auto-Scaling and Monitoring

[ To the top ](#contents)

---
