# MapReduce
---

## What is Map Reduce ?
- An algorithm that processes data dispersed across the Hadoop cluster
- Data is processed locally on the slave nodes whenever possible
- Monitored and managed by the AM
- Resource manager decides how many mappers to use that depend on the size of the processed data and the memory block available on each mapper server

![Overview of the flow of a MapReduce job.](https://phoenixnap.com/kb/wp-content/uploads/2021/04/mapper-reducer-mapreduce-job-flow.png)

---
## Map phase 
- Ingests individual logical expressions of the data stored in HDFS data blocks
- Can span several data blocks and called input splits as key value pairs
- The mapper task goes through every key-value pair and creates new distinct k-v pairs
- Based on the key, the data is grouped, partitioned and shuffled to the reducer nodes

![The elements of a map phase of a MapReduce job.](https://phoenixnap.com/kb/wp-content/uploads/2021/04/mapreduce-map-phase-shuffle-sort-input-split-1.png)

---
## Shuffle and Sort Phase
- A process in which the results from all the map tasks are copied to the reducer nodes
- The only exchange of data between nodes during the map reduce process
- Output from the map is stored on the node locally not on HDFS
- Sorted by the values of the key
- This phase runs in parallel and grouped and sorted on reducer nodes

---
## Reduce Phase
- An optional phase where map outputs are sorted into a single reduce input file
- Aggregates the data in the file based on mapped keys
- Produces a new k-v pair and stored in HDFS by default
- Reduce tasks take place simultaneously
![Overview of the reduce task in a MapReduce job.](https://phoenixnap.com/kb/wp-content/uploads/2021/04/reduce-task-sort-shuffle-hadoop.png)