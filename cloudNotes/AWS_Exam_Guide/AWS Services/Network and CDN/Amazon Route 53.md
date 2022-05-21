# Amazon Route 53
---
- A manged DBS used to help clients or users how to reach any server by domain name
- Public Hosted Zone : 
	- How traffic routed on the internet
- Private Hosted Zone
	- How traffic routed within a VPC

##### Routing policies
- Simple
	- Redirect traffic to a single resource
	- Dows not support health checks
- Weighted
	- Specify a weigth with a resource
	- Supports health checks
- Failover
	- If primary resource down, re-route to health one
- Routes to closes geo location or based on resource location
- Routes can depend on latency
- DNS response across multiple IP addresses  