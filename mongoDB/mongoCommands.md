# Commands

---
## Basic Shell Commands

- List all databases
  
  ```
  show dbs
  ```

- Switch to a database in order to use it
  
  ```
  use <db-name>
  ```

- Show all collections in the current DB
  
  ```
  show collections
  ```

---
## Find

- Find document(s) with a basic query condition

  ```js
  db.<collection-name>.find( 
    {"<field>" : "<value>"})
  ```

- Append a `.count()` to a query to get the number of documents returned for the query result
  ```js
  db.<collection-name>.find( {...} ).count();
  ```

- Find the first document
  ```js
  db.<collection-name>.findOne({ ... })
  ```

---
## CRUD Operations

### Create

### Update

### Delete


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
  | `$neq`   | $\neq$  |
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

## Aggregation

---
### Expressive Query




---
### Match
