# SQL Notes

## Commands

- <b style="color:#0FBAF1"> SELECT </b> and <b style="color:#0FBAF1"> FROM </b>  
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
- <b style="color:#0FBAF1"> WITH </b> and <b style="color:#0FBAF1"> AS </b> 
  ```SQL
  -- Returns a sub-table of tableName called newTable with respect to the condition of WHERE
  WITH newTable  AS (
    SELECT * FROM tableName WHERE tableCol1 = someValue
  )
  SELECT * FROM newTable
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