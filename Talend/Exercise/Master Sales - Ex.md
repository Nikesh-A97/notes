# Creating master sales table from different sources
### Setting Up a Customer Table
##### Overview of the final job
- ![[simpleDBConnection.png]]
##### Steps to create
1. The `tDBConnection` is created from the metadata that has the *"SalesDB"*
2. The next component is a `tFileInputDelimited` from the *"SalesCustomer"* schema from the metadata
3. The `tDBOutput` then loads then creates and inserts the data from the customers file
4. Finally the `tDBCommitAndClose` will close the DB connection 