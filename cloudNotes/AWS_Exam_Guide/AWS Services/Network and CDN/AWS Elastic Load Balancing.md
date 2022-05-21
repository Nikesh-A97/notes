

# AWS ELB
---
- Allows traffic to get distributed across EC2 instances containers and virtual appliances
- Integrates with every AWS service
- Tightly integrated with EC2, EKS/ECS

##### Types of load balancers
- Classic
	- Less recomened as it's old
	- Routes TCP, HTTP or HTTPS
	- Used for class EC2 instances
- Application
	- routes HTTP and HTTPS at layer 7
	- Offers path, host, query-string, parameter, and source based routing
- Network
	- Routes TCP, UDP, and TLS at layer 4
	- Suitible for high performance and low latency
- Gateway
	- For third party networking appliances
	- Simples tasks to manage, scale and deploy virtual appliances  