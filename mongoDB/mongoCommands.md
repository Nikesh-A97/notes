# Commands

---
## Basic Shell Commands

- List all databases
  
  ```
  show dbs
  ```

- Switch to a database in order to query collections in them
  
  ```
  use <db-name>
  ```

- Show all collections in the current DB
  
  ```
  show collections
  ```

---
## Cursors
- A Cursor is populated with the results of the applied methods, like `.find({})`
- Cursor methods are applied to the results not on the DB
- Cursor methods are appended to the query method at the end

### Cursor Methods

- Append a `.count()` to get the number of documents in the cursor
  
  ```js
  db.<collection-name>.<query-method>( {...} ).count();
  ```

- Append a `.pretty()` to make the output look cleaner
  
  ```js
  db.<collection-name>.<query-method>( {...} ).pretty();
  ```

- Append a `.limit(n)` to limit the output displayed
  
  ```js
  db.<collection-name>.<query-method>( {...} ).limit(n);
  ```

- Append a `.sort({...})` to sort the output that depends on a condition
  
  ```js
  db.<collection-name>.<query-method>( {...} ).sort({});
  ```
  
  ```js
    cursor.sort( { "<field-name>" :  1 } ); //sorts  ascending
    cursor.sort( { "<field-name>" : -1 } ); //sorts descending
  ```
- Note that `.sort({...})` and `.limit()` used together will always assume `.sort({}).limit(n)`

---
## CRUD Operations


---
### [Create](https://www.mongodb.com/docs/manual/tutorial/insert-documents/)


---
### [Read](https://www.mongodb.com/docs/manual/tutorial/query-documents/) 
- Find document(s) with a basic query condition

  ```js
  db.<collection-name>.find( {"<field>" : "<value>"})
  ```

- Find the first document of the search
  
  ```js
  db.<collection-name>.findOne({ ... })
  ```
- Use operators in the queries to filter search conditions
- Use Cursor methods to refine search results

#### Nested Documents
- To search for an exact match on a nested document, match the structure
  
  ```js
  (...).find(
    { "field1" : 
      { "nestedField1" : "value" }}
  )
  ```

- To query a value in a nested field, use dot notation and include the full path
  
  ```json
    {"field1.nestedField1" : {"$<operator>" : "value"}}
  ```


---
### [Update](https://www.mongodb.com/docs/manual/tutorial/update-documents/)



---
### [Delete](https://www.mongodb.com/docs/manual/tutorial/remove-documents/)


---
## Operators

---
### Comparison Operators

- All comparison operators follow the same format

  ```json
  {"<field>" : {"$<comp-op>" : "<value>"}, ...}
  ```
- The operators are as follows
  
  | Operator | Meaning |
  | -------- | ------- |
  | `$eq`    | $=$     |
  | `$ne`    | $\neq$  |
  | `$lt`    | $\lt$   |
  | `$lte`   | $\leq$  |
  | `$gt`    | $\gt$   |
  | `$gte`   | $\geq$  |

- When no operators are defined, there is an implicit `$eq`
  
  ```json
  {"<field>" : {"$eq" : "<value>"}}
  // Is the same as
  {"<field>" : "<value>"}
  ```

---
### Logical Operators

- Logical Operators all follow the same format
- Statements must be in an array
 
  ```json
  { "$<logic-op>" : [{<statement>}, {<statement>}, ...] }
  ```

- The following logical operators are
  
  | Operator | Meaning                  |
  | -------- | ------------------------ |
  | `$and`   | Match All statements     |
  | `$or`    | Find all that holds true |
  | `$nor`   | Negate `$or`             |
  | `$not`   | Doesn't work             |

- `$and` is implicitly used, for example when listing multiple statements
  
  ```json
  { "$and" : [
    {"<field_1>" : "<value_1>" },
    {"<field_2>" : "<value_2>" } 
  ]}
  // Is the same as
  {{"<field_1>" : "<value_1>" , "<field_2>" : "<value_2>" }}
  ```

---
## Arrays


---
## Aggregation


---
### Expressive Query


---
### Match

---

