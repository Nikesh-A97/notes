# Amazon EBS
---
![[awsCloudNotes#Amazon EBS]]

##### EBS Volume types
| Type | Use case | Volume (TiB) | IOPS | Throughput (MiB/s) |
| --- | --- | --- | --- | --- |
| General SSD | Low-latency apps | <center>1 - 16</center> | <center>16,000</center> | <center>1,000</center> |
| Provisioned SSD | Intensive DB Workloads | <center>4 - 64</center> | <center>256,000</center> | <center>4,000</center> |
| HDD | Big Data & Logs | <center>0.125 - 16</center> | <center>500</center> | <center>500</center> |
| Cold HDD | Low-latency apps | <center>0.125 - 16</center> | <center>250</center> | <center>250</center> |
