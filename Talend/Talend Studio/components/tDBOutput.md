# `tDBOutput`
---
##### What does it do ?
- Outputs incoming data to a database
- Perform different actions on the way the table should be created and updated

---
##### Basic Component View
Similar to the tDBInput but with a bit more features
- ![[db_out_1.png]]
- Can *Use an existing connection* if there is a connection open
- Make sure to have *Auto Commit* enabled on `tdbConnection` or a `tdbCommit` component to save the data in the DB
- The *sunglasses* tp the  left of the *Table* field opens up SQL builder
---
##### Actions on Table
- **Default** : 
	- No operation is carried out
- **Drop and Create table** : 
	- The table is removed and created again
- **Create a table** :
	- The table does not exist and gets created
- **Create atable if not exists** : 
	- The table is created if it does not exist
- **Drop a table if exists and create** :
	- The table is removed if it already exists and created agian
- **Truncate table** :
	- The table content is quickly deleted
	- Will not be able to rollback operation    

##### Actions on Data
- **Insert** :
	- Add new entries to the table
	- Duplicates will cause the Jobs to stop 
- **Update** :
	- Make changes to existing entries
	- Job **fails** if **all** schema columns are **keys**
- **Insert or update** : 
	- **Insert record first** then if does exist an update is made
- **Update or insert** :
	- **Update record first** then if does not exist, insert
- **Delete** :
	- Remove entries corresponding to the input flow
- **Replace** :
	- Add new entries to the table
	- If old row = new row for primary/unique key -> old row deleted -> new row inserted
- **Insert or update on duplicate key or unique index** :
	- Add entries if inserted value does not exist
	- Update if exist and no risk of violating a unique index or primary key
- **Insert Ignore** :
	- Add only new rows to prevent duplicate key errors

---