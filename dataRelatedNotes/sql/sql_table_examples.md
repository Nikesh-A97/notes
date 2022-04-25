# Tables
## table_A
id |name | age 
:---|---|---:
0 | John | 38
1 | John | 54
2 | John | 24
3 | Doe | 19
4 | Doe | 27
# Operations
## ORDER BY
```SQL
SELECT
	id,
	name,
	age
FROM 
	table_A a
ORDER BY
	2 ASC, 
	3 DESC
```
### ORDER BY - Result
id |name | age
:---|---|---:
4 | Doe | 27
3 | Doe | 19
1 | John | 54
0 | John | 38
2 | John | 24
