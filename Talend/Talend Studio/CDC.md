# Change Data Capture
---
##### What is CDC
- A process that identifies and tracks changes to changes in a DB
- Used to maintain synchronization
- It is impractical to dump and load entire DB to update so CDC is used instead
----
##### CDC Architecture
![[cdc_1.png]]
![[cdc_3.png]]
![[cdc_2.png]]

----
##### CDC DB Support
- Supports all major DBs
- Supports **Trigger**, **Redo** and **XStream** (not all modes are supported with all DBs)
---
##### Setting up 
![[cdc_steps_1.png]]
![[cdc_steps_2.png]]
![[cdc_steps_3.png]]
![[cdc_steps_4.png]]