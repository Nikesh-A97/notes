# Hadoop Architecture
---
## Overview of Hadoop
- The Hadoop framework allows you to manage and process big data
- HDFS is just a file system for large amounts of data
- YARN facilitates scheduled tasks
- Hadoop MapReduce helps programs perform computation
- Hadoop ecosystem is made up of these layers and processing tools
![[hadoop-ecosystem-projects-architecture.png]]

---
## Layers of Hadoop
![[hadoop-ecosystem-layers.png]]

### Distributed Storage Layer
- Hadoop Cluster --> $\{ n$ racks --> $\{m$ nodes
- Each node has own disk space, memory, bandwidth, processing
- Stores replicas for fault tolerant system

### Cluster resource management
- Hadoop needs to coordinate nodes perfectly
- Allocates different resources to different frameworks
- YARN is the tool that is used to do this

### Processing Framework Layer
- The processing layer consists of frameworks that analyze and process datasets
- The structured & unstructured data sets are mapped --> sorted --> merged --> reduced
- Frameworks such as Spark, Storm and Tez used for real time processing

### APIs
- Frameworks that simplify some things, security, new functionality

---
## HDFS
![[hdfs-components-namenode-datanode-datanode.png]]

### Name Node
- The name node is the central point which stores various information and metadata about a file
- Name nodes manage the data nodes, maintain block metadata  and control client access
- If a name node fails, HDFS will not be able to locate any data associated with the file
- A secondary name node is used as back-up incase the primary name node fails
- A secondary name node would need manual recovery
- A Standby name node is an automated failover case which runs along side the primary name node
- Cluster can only maintain one or the other
- Zookeeper is used to support high availability and redundancy by managing failovers

### Data Node
- Each data node stores blocks of data
- By default 3 copies of a data block is stored across multiple Data nodes
- The copies of data blocks cannot be located on the same rack
- Accepts instructions from the name node

### Rack Aware Placement Policy
![The data block replicas are place based on the default HDFS rack placement policy.](https://phoenixnap.com/kb/wp-content/uploads/2021/04/rack-placmement-policy-hdfs.png)

- The placement policy of the data blocks ensure high reliability by always storing at least one replica on a different rack

### YARN (Yet Another Resource Negotiator)
![YARN aechitecture with individual daemons.](https://phoenixnap.com/kb/wp-content/uploads/2021/04/yarn-daemons-hadoop-architecture.png)

#### Resource Manager
- The resource manager controls all the processing resources
- Designates resources to individudal applications on slave nodes
- No interest in failovers or individual  processing tasks

#### Node Manager
- Each slave has a Node manager and a data node storage service
- Tracks processing resources data and sends reports to the resource manager

#### Containers
- Processing resources in a Hadoop cluster are always deployed in containers
- Container processes on slave node are initially provisioned, monitored and tracked by the NodeManager on the specific slave node

#### Application Master
- Every container on a slave node has a dedicated application master 
- Sends messages to resource manager about current status of what it monitors
- Oversees the full lifecyle of an application
	- Requesting containers from RM --> Node Manager

#### Job History Server
- Allows users to retrieve information about applications that have completed their activity
- REST API  provides interoperability and can dynamically inform users on current and completed jobs