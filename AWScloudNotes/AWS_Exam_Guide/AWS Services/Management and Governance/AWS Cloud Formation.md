# AWS Cloud Formation
---
- Collects AWS and third party resources and manages them
- Launches the resources collectively as a stack
- A template is used to achieve this
	- Creates, updates and deletes entire units of resources
	- Provides the capability to reuse the template
	- Can deploy ELB environments
- Example Template 
	- Security group, with 2 EC2 instances, with an S3 bucket and ELB
	- Cloud Formation will do this for you with costs shown 