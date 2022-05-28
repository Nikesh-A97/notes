# Data Processing
---
##### `tMap`
- Used to transform data and join multiple inputs with multiple outputs
- `tMap` is often part of a solution to various data challenges
- ![[tMap.png]]
---
##### Design Practice with `tMap`
- ![[tMap_design.png]]
---
##### `tMap` Editor
- Divided into seperate panels that perform specific actions
- Inputs mapped to outputs
- ![[tMap_editor.png]]
- Schemas are updated directly in the tMap editor
- Can perform multiple actions to modify inputs
- ![[tMap_editor2.png]]
- ![[tMap_editor3.png]]
- ![[tMap_editor4.png]]
- ![[tMap_editor5.png]]
- Create or enter custom expressions
- On the left data is converted to uppper case, right, data is combined
- ![[Pasted image 20220503144820.png]]
- Define variables and insert into  expressions, and can aalso create them
---
##### Joins with `tMap`
- **Inner Join** returns rows that only appear in both tables
- **Left Outer Join** Returns all records from left with NULL values if no match on the right
- Data in the **Main** row is on the left side of the join
- When using a left outer join, data from the **Main** row is always protected even with non-matching records
---
##### Steps for joining data with `tMap`
1. Define multiple input sources 
	- ![[tMap_j1.png]]
2. Configure join
	- ![[tMap_j2.png]] 
3. Define multiple output sources
	- ![[tMap_j5.png]] 
4. Handle  Rejects 
	- ![[tMap_j6.png]] 
	- Rejects can be channeled to a seperate output for additional processing
---
##### Filtering data and capturing rejects
- `tMap` supports filters
- ![[tMap_r1.png]]
- Can be applied to inputs or outputs
- Can capture the rejected options
- ![[tMap_r2.png]]
---
##### Aggregating Data
- Compute values by collecting and grouping data
- Choose columns to keep aand calculation models for the values
- ![[tAgg_example.png]]
---
##### Steps to aggregate data with `tAggregateRow`
1. Define aggregation schema
	- ![[tAgg_1.png]] 
	- Take care when selecting a compatible data type
2. Define grouping criteria
	- ![[tAgg_2.png]] 
	- The Group By table is available on the basic settings tab for the component
3. Define Operations
	- ![[tAgg_3.png]]
	- The operations table is available on the basic settings tab 