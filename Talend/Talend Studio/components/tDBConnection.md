# `tDBConnection`
---
##### What does it do ?
- Connect to a DB

---
##### Basic Component View
![[db_con_0.png]]
- Advanced setting also has an *Auto commit* feature
---
##### Metadata Connection View
Steps to create a metadata DB connection
1. *Repo* --> Rš *Db Connection* --> *Create folder* (optional) --> Rš *Create Connection*
	- 
2. Fill in **Name**, **Purpose**, **Description**
- ![[db_con_1.png]]
3. Fill in DB connection parameters
- ![[db_con_2.png]] 
4. š *Test Connection* --> š*Export as context* (optional)  -->š*Finish*
- ![[db_con_3.png]]

---
##### Creating a table schema from a DB connection
Steps to retrieve a schema

1. Rš *{connectionName}* --> š*Retrieve Schema*
2. Set filters --> š*Next*
- ![[db_con_schema_1.png]]
3. Select the tables for schemas to be generated for
- ![[db_con_schema_2.png]] 
4. Check all schemas --> š*Finish* 
- ![[db_con_schema_3.png]]
5. View data to check
-  ![[db_con_schema_4.png]]

---
##### An example DB connection Job
![[db_con_ex_1.png]]