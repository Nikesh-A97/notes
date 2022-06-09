# Creating master sales table from different sources
### Setting Up a Customer Table
##### Overview of the final job
- ![[ms_1.png]]
##### Steps to create
1. The `tDBConnection` is created from the metadata that has the *"SalesDB"*
2. The next component is a `tFileInputDelimited` from the *"SalesCustomer"* schema from the metadata
3. The `tDBOutput` creates a table in the DB and inserts the data from the customers file
4. Finally the `tDBCommit` will close the DB connection 

### Loading Shop Data
##### Overview of the final job
![[ms_2.png]]
![[ms_3.png]]
##### Steps to create
- Similar to previous task but added parallelization for 1 way
- Other way uses `tUnite`

### Performing a `tMap` table join
- ![[ms_4.png]]
##### `tMap` In
- Both table joins are Inner & Unique match joins
- ![[ms_5.png]]
##### `tMap` Out
- ![[ms_6.png]]
##### Steps to create
- The *"SalesStaging"* table is the main input table
	- Headers are : Shopname, CustomerID, ProductID, Quantity
- The *"SalesCustomers"* is the first lookup table
	- Headers are : CustomerID, CustomerName, CustomerAddress ...
- The *"SalesProducts"* is the second lookup table
	- Headers are: ProductID, ProductName

The result of the double inner join is that we get a table with what customer bought which proudct and the quantity.

### Catching rejects and performing calculations
