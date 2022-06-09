# Database connections
---
##### Steps to connect DBs
- Define the type of DB you want to connect to
- Provide the connection info and credentials
- Set the table schema
- Set operations on table for the jobs
---
##### Information on DB components
- DB components are dynamic and the type can be changed any time 
- Defining the schema is a key setting
- Two data type columns, one is Java and the other is a DB type
- Limited amount of DB connections, can be shared, or close them when done
- production DBs must be managed by DB admins only
---
##### Some general components
- `tDBInput`  allows you to import a DB table and uses SQL to read the table
- `tDBOutput` allows you to create, clear or drop tables
- `tDBcommit` to save the output to a DB