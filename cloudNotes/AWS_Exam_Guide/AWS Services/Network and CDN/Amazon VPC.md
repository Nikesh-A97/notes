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