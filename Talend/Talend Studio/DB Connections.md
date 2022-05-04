# Database connections
##### Steps to connect DBs
- Define the type of DB you want to connect to
- Provide the connection info and credentials
- Set the table schema
- Operations on table for the jobs

##### Information on DB components
- DB components are dynamic and can be changed any time 
- Defining the schema is a key setting
- Two data type columns, one is Java and the other is a DB type
- `tDBOutput` allows you to output as a DB table
- Limited amount of DB connections, can be shared, or close them when done
- `tDBcommit` to save the output to a DB
- production DBs must be managed by DB admins only
