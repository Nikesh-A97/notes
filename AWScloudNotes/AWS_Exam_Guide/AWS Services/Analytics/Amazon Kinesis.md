# Amazon Kinesis
---
- Collect, process and analyze real-time while streaming data

##### Kinesis Video Streams
- Stream videos to AWS for analytics and processing
- Access to APIs
- Stores data for 24 hours by default and up to 7 days

##### Kinesis Data Streams
- Stream and process and analyze real-time data
- Can store data for later processing
- Alternative to Apache Kafka

##### Kinesis Data Firehose
 - Serverless service to capture transform and load streaming data into data stores
 - Allows realtime analysis with BI tools
 - Can be used with KDS
 - Data store options include S3, Redshift, Elastic Search Service
 - Synchrinously replicates data across three AZs

##### Kinesis Data Analytics
- Used to process and analyze real-time data that is being streamed
- Output to the standard amazon data stores
- Take in data from strems and firehose