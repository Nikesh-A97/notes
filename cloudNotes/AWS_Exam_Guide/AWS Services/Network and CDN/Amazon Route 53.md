# Amazon Route 53
---
- A manged DBS used to help clients or users how to reach any server by domain name
---
##### Hosted Zone
- Public Hosted Zone : 
	- How traffic routed on the internet
- Private Hosted Zone
	- How traffic routed within a VPC
---
##### Routing policies
- Simple
	- Redirect traffic to a single resource
	- Dows not support health checks
- Weighted
	- Specify a weigth with a resource
	- Supports health checks
- Failover
	- If primary resource down, re-route to healthy one
- Geo-location
	- Routes traffic to the closest geographical location your users are in
- Geo-proximity
	- Routes traffic based on the location of resources to the closest region within a geogrpahic area 
- Latency Based
	- Routes traffict to the destination with the lowest latency
- Multi-value
	- Distributes DNS across multiple IP address
---
##### Records  supported
- A
	- Hostname <--> IPv4
- AAAA
	- Hostname <--> IPv6
- CNAME
	- Hostname <--> Hostname
- Alias
	- Hostname <--> AWS resources  
---
| Route 53 CNAME | Route 53 Alias |
| --- | --- |
|Points a hostname to any hostname|Points a hostname to AWS Resource|
|non-root domains|root and non-root domains|
|charges for CNAME queries|charge for alias queries|
|points to any dns record|points to an ELB,CF Dist, EB env, S3 bucket, static website|
