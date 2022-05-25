# Amazon VPC
---
- Service that allows users to create a virtual dedicated network for resources

##### Subnet
- Private
	- Does not have access to the internet
- Public
	- Does have acess to internet
- VPN only
	- Does not have internet access but has access to the Virtual private gateway for a VPN 

##### Some info
- Components such has VPN tools, Subnets, route tables, NAT instances
- Spans across multiple AZs
- First four IPs and last one is reserved per subnet
- Monitor resources using CloudWatch
- Every EC2 instance has a default VPC
- Uses Secutiry groups and NACL for secutrity

### How it works
##### Internet & NAT Gateways
- Internet Gateways : VPC --> Internet
- Pub Subnet route to IGW
- NAT Gateway & Instance help Priv Subnet access Internet

##### Network ACL & Security Groups
- NACL
	- A firewall that controls traffic to and from a subnet
	- Can have ALLOW and DENY rules
	- Attached at Subnet Level
	- Rules only include IP addresses
- Security Groups
	- A firewall that controls traffiic to and from an ENI / an EC2 Instance
	- Can have only ALLOW rules
	- Rules inlcude IP addresses and other security groups 

|Security Groups|Network ACL|
|---|---|
|Operates at the instance level|Operates at teh subnet level|
|Supports allow rules only|Supports allow rules and deny rules|
|Stateful, return traffic auto allowed|Stateless return traffic explicitly allowed|
|Evaulate rules before allow|Process rules in order to allow|
|Applies to an instance only|Applies to all instances in the subnet|

----
##### VPC Peering
- Connect two VPC privately using AWS Network
- Behaves as if they were in the same network
- No overlapping CIDR ranges
- Peering non transitive : A <- -> B & A <- -> C $\neq$ B <- -> C
---
##### VPC Endpoints
- Connect to AWS using a private network
- Enhanced security & low latency 
- VPC Endpoint Gateway : S3 & DynamoDB
- VPC Endpoint Interface : The rest
