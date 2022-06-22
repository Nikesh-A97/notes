# Kafka
---

## What is Apache Kafka ?
- In terms of DBs we take the state of "things" and store them in DBs
- Think about events instead, they indicate a time that a "thing" took place
- It is difficult to store events in DBs, so they are stored in an ordered sequence called a log
- An event could include a description, time and date, and other information related information
- Apache Kafka is a way to manage logs
- In Kafka logs are known as **Topics**
- Kafka stores data in a fault-tolerant way (multiple locations)
- Topics can store data for any length of time
- Topics can have events with varying size
- Services are used to process events in real time for analytics
---

## Producers
- A **Producer** is an application you write to **put** data into a Kafka Cluster
- Kafka clusters sends **acknowledgements** to the app to let it know that an event has been received

### Kafka Clusters
- Clusters consists of Brokers that act together
- Each broker has it's own local storage and retention time

## Consumers
- A **Consumer** is an application you write to **read** data from a Kafka Cluster
- The consumers role is to transform the data and do whatever is required
  - Transform the data to be used for reports or dashboards
  - Gain insights on the data
  - Process the data and put in another Kafka Cluster for further use

### Decoupling Producers and Consumers
- Producers and Consumers are decoupled
- Slow consumers do not affect Producers
- Add Consumers without affecting Producers
- Failure of Consumer does not affect System

## Topics
- A **Topic** is a collection of related messages or events
- A sequence of events
- Any number of producers can write to any number of topics
- Any number of consumers can read from any number of topics
- Unlimited* number of topics

### Topics at a deeper level
- A topic is split up into partitions
- Each partition is allocated to a different brokers in the clusters
- Formally a partition is a log with strict ordering with immutability

### Logs
- New events in a log are always added to the end of the log
- Entries are immutable records of events
- events can be set to expire
- Reading events in logs doesn't destroy them

### Events
- Every event is a key - value pair, with some sort of structure for both
- Every event has a timestamp even if the original event did not have one, one is added
- An optional header

### Brokers manage partitions
- Partitions spread across Brokers
- Configurable Retention Policy
- Messages of Topic spread across Partitions
- Each broker manages multiple partitions
- Partitions are replicated across brokers

## Data retention policy 
- Default data stays for 1 week
- Configurable globally or per topic


