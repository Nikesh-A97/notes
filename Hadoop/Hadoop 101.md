# Hadoop 101
---
## What is hadoop ?
- An open source project
- A framework written in Java
- Optimized to handle x-structured data
- Batch and parallel processing
- Uses map reduce
- Data is replicated across clusters
- Not suitable with OLTP, OLAP, DSS
- Not a replacement for RDBMS

### What it's not used for
- Not to process transactions
- Not good for work that cannot be parallelized
- Not food for low latency data access
- Not good for processing lots of small files
- Not good for intensive calculations

---
## Hadoop Architecture

### Terminology
- Node is just a computing unit
- A rack is a collection of nodes
- A cluster is a collection of racks

### Architecture
-  Two main components
	- HDFS
- MapReduce Engine
	- Framework for performing calculations
	- Built-in resource manager and scheduler

#### HDFS
- Runs on top of the existing file system
- Not POSIX compliant
- Designed to tolerate high component failure rate through replication
- Designed to handle large files
- Large streaming data access patterns
- No random access
- Uses blocks to store files

#### HDFS file Blocks
- Default block size is 64MB (128MB is recommended)
- Size of a file can be larger than any single disk in cluster
	- A single file is spread across multiple nodes
- Only the needed space is used if the file can fit inside a block
- Duplicates of blocks are spread across nodes

### HDFS CLI
All commands take path URIs as arguments
- The FileSystem (FS) shell is invoked by
	- `hdfs dfs <args>`
- Copy files from LFS to HDFS
	- `copyFromLocal / put`
- Copy files from HDFS to LFS
	- `copyToLocal / get`
- Get all files in directories that match the source pattern and merge sort them to one LFS
	- `getMerge`
- Set replication factor of a file, can be executed recursively, specify to wait until achieved
	- `setRep`

---
## Hadoop Administration
#### Adding and removing nodes
- Can be performed from the Ambari Web Console
- Need and IP address or hostname of node
- must be reachable