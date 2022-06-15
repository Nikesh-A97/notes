# Amazon ElastiCache
---
- Web Service used to manage and run in-memory data stores
- Suited for OLAP
- in-memory cache for sub-milisecond latency

##### ElastiCache for Redis
- Useful for gaming  apps, geo services, caching sessions and replication
- Data is persistent
- not multi-threaded
- supports multi-AZ

##### ElastiCache for Memecached
- Building apps that require caching layers
- Data is not persistent
- supports multi-threading
- does not support multi AZ failover
- does not support snaphsots