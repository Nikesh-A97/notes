<style>
  img[alt$="#width30"]{
  width: 30%;
}
  img[alt$="#width20"]{
  width: 20%;
}
</style>
# SQL Notes

## Commands

<h3><b style="color:#0FBAF1"> SELECT </b> & <b style="color:#0FBAF1"> FROM </b></h3>

- Returns all (*) columns in the the table, <i style="color:#9b75d9">table_A</i>
  ```SQL
  SELECT 
    * 
  FROM 
    table_A
  ```
- Returns all the specified columns in the the table, <i style="color:#9b75d9">table_A</i>
  ```SQL
  SELECT 
    column_1, 
    column_2, ... 
  FROM 
    table_A
  ```
  
<h3><b style="color:#0FBAF1"> WHERE </b></h3>

- Returns a table with all columns that is filtered by the conditions in the <b><i style="color:#0FBAF1">WHERE</i></b> clause
  ```SQL
  SELECT 
    * 
  FROM 
    table_A 
  WHERE 
    <conditions>
  ```
  
<h3><b style="color:#0FBAF1"> ORDER BY </b></h3>

- By default, the ordering will be in <b><i style="color:#1bd517"> ascending </i></b> order   
  ```SQL
  -- orders the table elements according to colName
  SELECT 
    * 
  FROM 
    table_A 
  ORDER BY 
    column_name (ASC/DESC)
  ```

- Orders `column_1` first then whilst retaining the order, it will sort `column_2` next [[sql_table_examples#ORDER BY|example]]
  ```SQL
  SELECT 
    * 
  FROM 
    tableName 
  ORDER BY 
    column_1 ASC 
    column_2 DESC
  ```

<h3><b style="color:#0FBAF1"> LIMIT </b></h3>

- Limits the table to the number specified (does not modify actual table, just how you view it)
  ```SQL
  SELECT 
    * 
  FROM 
    table_A 
  LIMIT 2
  ```

<h3><b style="color:#0FBAF1"> MIN </b></h3>

- Find the minium value of the specified `column_name`
  ```SQL
  SELECT 
    MIN(column_name) 
  FROM 
    table_A
  ```

<h3><b style="color:#0FBAF1"> MAX </b></h3>

- Find the maxium value of the specified `column_name`
  ```SQL
  SELECT 
    MAX(column_name) 
  FROM 
    table_A
  ```

<h3><b style="color:#0FBAF1"> COUNT </b></h3>

- Aggregates and counts the number of rows in the specified column
- Can also add conditions inside the <b style="color:#0FBAF1">COUNT( )</b> clause for further filtering
  ```SQL
  SELECT 
    COUNT(*) 
  FROM 
    table_A
  ```

<h3><b style="color:#0FBAF1"> AND </b></h3>

- Used to chain multiple conditions
  ```SQL 
  SELECT 
    * 
  FROM 
    table_A 
  WHERE 
    column_1 <op> condition_1 
    AND 
    column_2 <op> condition_2 
    .
    .
    .
  ```

<h3><b style="color:#0FBAF1"> BETWEEN </b></h3>

- Used as an operator for some conditions
  ```SQL
  -- BETWEEN is inclusive
  SELECT 
    COUNT(*) 
  FROM
    table_A 
  WHERE 
    column_1 BETWEEN condition_1 AND condition_2
  
  -- The above query is the same as
  SELECT 
    COUNT(*) 
  FROM 
    table_A 
    WHERE 
      column_1 >= condition_1 
      AND 
      column_2 <= condition_2
  ```

<h3><b style="color:#0FBAF1"> AS </b></h3>

- Used to rename and refer to the column as the new name
  ```SQL
  SELECT 
    column_name AS column_new_name
  FROM 
    table_A
  ```
  
<h3><b style="color:#0FBAF1"> CASE WHEN THEN ELSE </b></h3>

- Create a new tbale column with own name and values that depend on conditions
  ```SQL
  -- create a new table col with own name and values that depend on conditions
  SELECT 
    CASE
      WHEN condition_1 THEN result_1
      .
      .
      .
      WHEN condition_n THEN result_n
      ELSE default_result
    END AS column_name
  FROM 
    table_A
  ```

<h3><b style="color:#0FBAF1"> WITH </b> and <b style="color:#0FBAF1"> AS </b></h3>

- Used to create a new table that is created with SQL SELECT - FROM query
  ```SQL
  -- The example below can have anything inside the WITH - AS to create a sub - table
  WITH table_B  AS (
    SELECT 
      * 
    FROM 
      table_A 
    WHERE 
      <condition>
  )

  SELECT 
    * 
  FROM 
    table_B
  ```

<h3> Cast (<b style="color:#0FBAF1"> :: </b>)</h3>

- Casts the given column current data type to the given dataType
  ```SQL
  SELECT 
    COUNT(*)
  FROM 
    table_A
  WHERE
    column_name::dataType <some condition>
  ```


<h3> <b style=""> Order of execution for a query </b> </h3>

- Order of Execution for a basic query
  ```SQL 
  /*
    Order of execution
    FROM --> WHERE --> GROUP BY --> SELECT --> DISTINCT --> ORDER BY --> LIMIT
  */
  SELECT
    *
  FROM 
    table_A
  WHERE
    <conditions>
  GROUP BY 
    column_1
  ORDER BY 
    column_2 
  LIMIT 20
  ```

- Order of execution with joins
	```SQL
		/*
			Order of Execution with Joins
			FROM - What SQL engine will look at first
			JOIN - Join tables are merged with the main table to form a "big table"
			WHERE - Filters are applied to the "big table"
			GROUP BY - Splits the "big table" into the groups specified
			SELECT - Columns are selected, and functions are calculated
			DISTINCT - Filters out any duplicate values
			ORDER BY - sorts the final results in the "big table"
			LIMIT - Limits the rows in the final "big table" result
		*/
		SELECT
			DISTINCT(<column_name_1>),...
			/*other functions (aggregate, window) or columns*/
		FROM
			table_A a
		INNER JOIN
			tabale_B b
			ON
				a.<col_name> = b.<col_name>
				AND
					<conditions>...
		WHERE
			<conditions>...
		GROUP BY 
			<col_name>, ...
		ORDER BY 
			<col_name / ref>, ...
		LIMIT <#number>
	```


---
## Joins

<b style="color:#0FBAF1"> Syntax for joining</b>
  ```SQL 
  SELECT 
    *
  FROM 
    table_A a
  <INNER / LEFT / RIGHT / CROSS> JOIN 
    table_B b
  ON 
    a.<col> = b.<col>
    AND
      <conditions>...
  ```

<b style="color:#0FBAF1"> LEFT JOIN</b>

![left_join #width20](left_in_join.png)

<b style="color:#0FBAF1"> RIGHT JOIN</b>

![right_join #width20](right_in_join.png)
	
<b style="color:#0FBAF1"> INNER JOIN</b>

![in_join #width20](in_join.png)

----

## Window Functions

- <h3><b style="color:#0FBAF1"> ROW_NUMBER </b> ( )</h3>
 
  ```SQL
  -- Returns the same amount of rows, groups them and assigns an index that depends on the grouping
  SELECT
    ROW_NUMBER() OVER (PARTITION BY colName1)
  FROM
    table_A
  ```

----

## SQL Recap

### Revenue & Analytics

- <b style="color:#0FBAF1"> ROI - Return of Investment </b>
  ```SQL 
  WITH revenue AS (
    SELECT
      utm_campaign,                   /* Total made in revenue from users*/
      SUM(amount) AS total_revenue       
    FROM
      purchases p
    INNER JOIN
      users u
      ON
        p.user_id = u.id              /* Join tables on id */
        WHERE
          refunded = FALSE            /* Remove refunds */
          AND                       
          utm_campaign IS NOT NULL    /* Remove NULLS */
    GROUP BY
      1                             
  ), spends AS (
    SELECT
      utm_campaign,                   /* Total spent in marketing */
      SUM(amount) AS total_spend
    FROM
      marketing_spends
    GROUP BY
      1
  )

  SELECT 
    s.utm_campaign,                   /* ROI is the r - s / s  */
    total_spend,
    total_revenue,
    (total_revenue - total_spend) / total_spend AS ROI
    FROM 
      spends s
    LEFT JOIN 
      revenues r
      ON 
        s.utm_campaign = r.utm_campaign
  ```

- <b style="color:#0FBAF1"> ARPU - Average Revenue per User </b>
  ```SQL
  /* Free and Paying Users are counted, only distinct ones are counted */
  SELECT
    SUM(amount) / COUNT(DISTINCT(u.id)) AS ARPU
  FROM
    users u
  LEFT JOIN
    purchase p
    ON
      u.id = p.user_id
      AND
      refunded = FALSE
  WHERE
    utm_campaign IS NOT NULL
  ```

- <b style="color:#0FBAF1"> CPA - Cost Per Acquisition</b>
  ```SQL
  WITH spends AS (
    /* The amount spent on each source campaign */                  
    SELECT
      utm_source,
      SUM(amount) AS total_spend
    FROM
      marketing_spends
    GROUP BY 1
  ), 
    total_users AS (
      /* The number of users that signed up with the source */
      SELECT
        utm_source,
        COUNT(*) AS users_count
      FROM
        users
      WHERE
        utm_source IS NOT NULL
      GROUP BY 1
    )
  
  /* Join both tables together on the source and find the CPA */
  SELECT
    s.utm_source
    total_spend / users_count AS CPA
  FROM
    spends s
  INNER JOIN
    total_users u
    ON
      s.utm_source = u.utm_source
  ```
- <b style="color:#0FBAF1"> CPA - Cost Per Acquisition</b>

## AB Testing Vocab

### AB testing
<ul>
	<li>Testing two different versions of a variable.</li>
  <li>For example 2 different versions of a webpage or website and testing various different features with users</li>
</ul> 

### Name and Launch Date
<ul>
	<li>An AB test has a name : X vs Y</li>
  <li>A date that is associated with the tests in order to keep track of the tests</li>
</ul> 

### Variations, control variation
<ul>
	<li>Often A-B tests are run to test new features</li>
  <li>Therefore one of the versions is a control variation that you compare against.</li>
</ul> 

### Categorization
<ul>
	<li>This is the process of showing users different variations</li>
  <li>Behind the scenes users are randomly assigned to either use A or B versions of the variable</li>
  <li>This allows to later use it for analysis</li>
</ul> 

### Uplift
<ul>
	<li>The name given to a value for a certain metric that has improved in the A-B test</li>
  <li>For example, “the latest AB-test had an uplift of 15% in purchase rate”</li>
</ul> 

### Cohort Size
<ul>
	<li>The size of the group of people taking the A-B tests</li>
</ul> 

----

## SQL and Regex
- Regular expressions differ slightly in SQL DBs but pattern syntax is the same (POSIX).
- The boolean operator for matching regex in for PostgreSQL or Redshift is `~`

<h3>Tilde (<b style="color:#0FBAF1"> ~ </b>)</h3>

- Filters depending on the regex pattern that was used

  ```SQL
  SELECT
    *
  FROM
    table_name
  WHERE
    table_col ~ '<regex_pattern>'
  ```  

<h3><b style="color:#0FBAF1"> SUBSTRING </b><b>(<code>text_input</code>, <code>regex</code>)</b></h3>

- Extract a part of a text that matches the regex
  ```SQL
  -- The example below will return 'xyz.com'
  SELECT
    SUBSTRING('abc@xyz.com', '@(\w+.\w)')
  ```

<h3><b style="color:#0FBAF1"> REGEXP_REPLACE </b><b>(<code>text_input</code>, <code>regex</code>, <code>new_text</code>)</b></h3>

- Replace a part of the text that matches the regex

  ```SQL
  -- The example below will return '***@xyz.com'
  SELECT
    REGEXP_REPLACE('abc@xyz.com', '(.+)@', '***@')
  ```

<h3><b style="color:#0FBAF1"> REGEXP_MATCHES </b><b>(<code>text_input</code>, <code>regex</code>)</b></h3>

- All groups returned matched by a regex

  ```SQL
  -- The example below will return '{foo,bar}'
  SELECT
    REGEXP_MATCHES('foobar', '(foo)(bar)')
  ```
  ```SQL
  -- The example below will return '{foo,NULL}'
  SELECT
    REGEXP_MATCHES('foo', '(foo)(bar)?')
  ```

- Non - matching group
  ```SQL
  -- The example below will return '{foo}'
  SELECT
    REGEXP_MATCHES('foobar', '(foo)(?:bar)')
  ```
  ```SQL
  -- The example below will return '{foo}'
  SELECT
    REGEXP_MATCHES('foo', '(foo)(?:bar)?')
  ```

<h3><b style="color:#0FBAF1"> SPLIT_PART </b><b>(<code>text_input</code>, <code>delimiter</code>, <code>part_to_select</code>)</b></h3>

- Selects the part you want to keep that is separated by the delimiter
  ```SQL
  -- The example below will return 'def'
  SELECT
    SPLIT_PART('abc,def,ghi', ',', 2)
  ```



<h3>Caret (<b style="color:#0FBAF1"> ^ </b>)</h3>

- Matches the start of the text
  ```SQL
  -- The example below will return 'abc'
  SELECT
    SUBSTRING('abc@xyz.com', '^\w+')
  ```
- Negation if used inside `[]`
  ```SQL
  -- The example below will return '@'
  SELECT
    SUBSTRING('abc123@xyz.com', '[^\w]')
  ```

<h3>Dollar sign (<b style="color:#0FBAF1"> $ </b>)</h3>

- Matches the end of text

  ```SQL
  -- The example below will return 'net'
  SELECT
    SUBSTRING('abc@xyz.net', '[^\w+]')
  ```

<h3>Dot (<b style="color:#0FBAF1"> . </b> )</h3>

- Matches any character

  ```SQL
  -- The example below will return 'ab'
  SELECT
    SUBSTRING('abc@xyz.net', '.b')
  ```

<h3>Backslash (<b style="color:#0FBAF1"> \ </b>)</h3>

- A special character used for escaping other characters and other cases

  - `\n` : new line
  - `\d` : any digit (`[0-9]`)
  - `\D` : any non - digit (`[^0-9]`)
  - `\w` : any word character (`[a-zA-Z0-9_]`)

```SQL
SELECT
  SUBSTRING()
```

<h3>Curly brackets (<b style="color:#0FBAF1"> { } </b>)</h3>

- Used to specify a range

  - `a{n}` : exactly `n` number of <b>a</b> characters 
  - `a{n, }` : `n`  or more <b>a</b> characters 
  - `a{n, m}` : between `n` and `m` , <b>a</b> characters inclusive

```SQL
SELECT
  SUBSTRING()
```

<h3>Question mark, Asterisk, Plus (<b style="color:#0FBAF1"> ? </b>, <b style="color:#0FBAF1"> + </b>, <b style="color:#0FBAF1"> * </b>)</h3>

- Used to specify a range

  - `?` : matches previous token either 0 or 1 times 
  - `*` : matches previous token between 0 and &#8734;
  - `+` : matches previous token between 1 and &#8734;

```SQL
SELECT
  SUBSTRING()
```

<h3>Square Brackets (<b style="color:#0FBAF1"> [ ] </b>)</h3>

- Set of characters to match a single character
- Can define a range of characters

```SQL
SELECT
  -- The example below will return 'aclg'
  SUBSTRING('aclgeohn', '[a-l]+')
```

<h3>Parentheses (<b style="color:#0FBAF1"> ( ) </b>)</h3>

- Define a group of characters
- Allows special characters to be attached
- Multiple search patterns within a single regex and can be manipulated separately

  - `(<expr>)` : matches the first instance of the expression 

```SQL
SELECT
  SUBSTRING()
```

<h3>Pipe (<b style="color:#0FBAF1"> | </b>)</h3>

- Logical OR
- Specify multiple search patterns in a single group
```SQL
SELECT
  SUBSTRING()
```

----
## SQL at Work

- <b style="color:#0FBAF1"> 1 = 1 </b>
  ```SQL
  -- Use 1 = 1 to easily comment conditions to not let 'AND's hang
  SELECT 
    *
  FROM 
    tableA
  WHERE
    1 = 1
    AND
    tableCol1 <op> condition
    AND
    ...
  ```

  - <b style="color:#0FBAF1"> RANDOM() </b>
  ```SQL
  -- Generates a random number between [0, 1)
  SELECT 
    RANDOM() as random_number
  ```

----

## Manipulating and updating tables

- <b style="color:#0FBAF1"> INSERT INTO </b>
  ```SQL
  -- Generates a random number between [0, 1)
  INSERT INTO users (email, first_name, last_name, country)
  VALUES ('foo@example.org', 'Foo', 'Foo', 'by'), 
          ('bar@example.org', 'Bar', 'Bar', 'us');
  ```

- <b style="color:#0FBAF1"> UPDATE </b>
  ```SQL
  UPDATE users
  SET 
    signup_date = created_at::date,
    status = 'free'
  WHERE
    id IN (8391, 8392)
  ```

- <b style="color:#0FBAF1"> UPDATE </b>
  ```SQL
  DELETE 
  FROM users
  WHERE
    id IN (8391, 8392)
  ```