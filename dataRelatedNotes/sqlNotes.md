# SQL Notes

## Commands

- <b style="color:#0FBAF1"> SELECT </b> & <b style="color:#0FBAF1"> FROM </b>  
  ```SQL
  -- This query returns all (*) columns in the table tableName.
  SELECT * FROM tableName

  -- This query returns specified table columns in tableName.
  SELECT tableCol1, tableCol2, ... FROM tableName
  ```
- <b style="color:#0FBAF1"> WHERE </b>
  ```SQL
  -- Returns the table with all columns but with the specified condition by WHERE
  SELECT * FROM tableName WHERE tableCol = someValue
  ```
- <b style="color:#0FBAF1"> ORDER BY </b> 
  ```SQL
  -- By default , the ordering will be ASC
  -- orders the table elements according to colName
  SELECT * FROM tableName ORDER BY colName (ASC/DESC)

  -- First orders by tCol1 then keeps that order and orders the sub rows by tCol2
  SELECT * FROM tableName ORDER BY tCol1 ASC tCol2 DESC
  ```
- <b style="color:#0FBAF1"> LIMIT </b>
  ```SQL
  -- Limits the table to the number specified
  SELECT * FROM tableName LIMIT 10
  ```
- <b style="color:#0FBAF1"> MIN </b> & <b style="color:#0FBAF1"> MAX </b>  
  ```SQL
  -- find the min value of the table row
  SELECT MIN/MAX(tableRow) FROM tableName
  ```
- <b style="color:#0FBAF1"> COUNT </b>
  ```SQL
  -- returns the number of records 
  SELECT COUNT(*) FROM tableName
  ```
- <b style="color:#0FBAF1"> AND </b>
  ```SQL
  -- chain multiple conditions 
  SELECT COUNT(*) FROM tableName WHERE tableCol1 <op> condition1 AND tableCol2 <op> condition2
  ```
- <b style="color:#0FBAF1"> AND </b>
  ```SQL
  -- chain multiple conditions 
  SELECT COUNT(*) FROM tableName WHERE tableCol1 <op> condition1 AND tableCol2 <op> condition2
  ```
- <b style="color:#0FBAF1"> BETWEEN </b>
  ```SQL
  -- between is inclusive
  SELECT COUNT(*) FROM tableName 
    WHERE 
      tableCol1 BETWEEN condition1 AND condition2
  -- is the same as
  SELECT COUNT(*) FROM tableName 
    WHERE 
      tableCol1 >= condition1 AND 
      tableCol1 <= condition2
  ```
- <b style="color:#0FBAF1"> AS </b>
  ```SQL
  -- use an alias
  SELECT 
    tableCol1 AS tableRowNewName
    FROM tableName
  ```
- <b style="color:#0FBAF1"> CASE, WHEN, THEN, ELSE </b>
  ```SQL
  -- create a new table col with own name and values that depend on conditions
  SELECT 
    CASE
      WHEN condition_1 THEN result_1
      WHEN condition_n THEN result_n
      ELSE default_result
    END AS aTableColName
  FROM tableName
  ```
- <b style="color:#0FBAF1"> WITH </b> and <b style="color:#0FBAF1"> AS </b> 
  ```SQL
  -- Returns a sub-table of tableName called newTable with respect to the condition of WHERE
  WITH newTable  AS (
    SELECT * FROM tableName WHERE tableCol1 = someValue
  )
  SELECT * FROM newTable
  ```
- <b style="color:#0FBAF1"> :: </b>
  ```SQL
  -- Casts the given tableCol current data type to the given dataType
  SELECT 
  COUNT(*)
    FROM tableName
    WHERE
    tableCol::dataType <some condition>
  ```