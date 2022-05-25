# AWS CodeDeploy
---
- Automate application deployment to compute services (EC2, Fargate, ECS, on-prem)

##### Deployment type
- In-place
	- All instances in deployment stopped -> updated -> re-deployed
	- usefile for ec2/on-prem
- Blue/green
	- Instances in deployment group are replaced by a new set of instances
	- Using ELB traffic gets rerouted from original environment to replacement environment