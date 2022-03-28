# MongoDB Notes

## <b>Chapter 1 - What is MongoDB</b>

### <b>What is MongoDB</b>
<ul>
	<li><b style="color:#32a852">NoSQL DB</b></li>
	<p>A DB with no related tables of data</p>

  <li><b style="color:#32a852">NoSQL Document DB</b></li>
	<p>Data in MongoDB is stored as documents</p>

  <li><b style="color:#32a852">Collection of Documents</b></li>
	<p>Data in MongoDB is stored as documents</p>
</ul>

### <b>What is a document in MongoDB</b>
<ul>
	<li><b style="color:#32a852">Document</b></li>
	<p>Organize and store data as field - value pairs</p>

  <li><b style="color:#32a852">Collection</b></li>
	<p>Organized store of documents with common fields between documents</p>
</ul>

### <b>MongoDB Atlas</b>
<ul>
	<li><b style="color:#32a852">MongoDB Atlas</b></li>
	<p>A cloud DB with mongoDB at its core</p>

  <li><b style="color:#32a852">Clusters</b></li>
	<p>Groups of servers that store your data</p>

  <li><b style="color:#32a852">Replica Set</b></li>
	<p>A set of connected mongoDB instances that store the same data.
  <br>This is because if one instance becomes unusable, the remaining instance are still there</p>

  <li><b style="color:#32a852">Instance</b></li>
	<p>A single machine locally or in the cloud running a certain software</p>
</ul>

---

## <b>Chapter 2 Importing, Exporting & Querying Data</b>

### <b>What is a Valid JSON document</b>
<ul>
	<li><b style="color:#32a852">Document - JSON</b></li>
	<ul>
    <li>Start and end with <code>{}</code></li>
    <li>Separate <b style="color:#32a852">key</b> and <b style="color:#32a852">value</b> with  <code>:</code> </li>
    <li>Separate <b style="color:#32a852">key : value </b> pairs with  <code>,</code> </li>
    <li><b style="color:#32a852">keys</b> surrounded by <code>" "</code> </li>
  </ul>
</ul>

### <b>Pros and Cons</b>
<table>
  <tr style="color:#32a852">
    <th>Advantages</th>
    <th>Disadvantages</th>
  </tr>
  <tr>
    <td>Friendly</td>
    <td>Text-Based</td>
  </tr>
  <tr>
    <td>Readable</td>
    <td>Space-Consuming</td>
  </tr>
  <tr>
    <td>Familiar</td>
    <td>Limited</td>
  </tr>
</table>

### <b>BSON</b>
Bridges the gap between binary representation of the JSON format
<table>
  <tr style="color:#32a852">
    <th></th>
    <th>JSON</th>
    <th>BSON</th>
  </tr>
  <tr>
    <th style="color:#32a852">Encoding</th>
    <td>UTF-8 String</td>
    <td>Binary</td>
  </tr>
  <tr>
    <th style="color:#32a852">Data</th>
    <td>String, Bool, Number, Array</td>
    <td>String, Bool, Number(Data Types), <br> Array, Date, Binary</td>
  </tr>
  <tr>
    <th style="color:#32a852">Readability</th>
    <td>Human & Machine</td>
    <td>Machine Only</td>
  </tr>
</table>

### <b>Import and Export</b>

#### <b>Export</b>
- BSON
  ```
  mongodump --uri "<Atlas Cluster URI>"
  ```
- JSON
  ```
  mongoexport --uri "<Atlas Cluster URI>"
              --collection = <collection name>
              --out = <filename>.json
  ```
```
mongoimport --db dfx --collection trainees --file dfxDataImport.json
```

### <b>Some Commands</b>
<ul>
	<li><code>show dbs</code></li>
	<p>Shows all dbs in the clusters</p>
  
  <li><code> use &lt;dbName&gt; </code></li>
	<p>Switches to the database of the dbName provided</p>

  <li><code> show collections</code></li>
	<p>shows all collections in the current db </p>

  <li><code> db.&lt;collectionName&gt;.find({"&lt;key&gt;" : "&lt;value&gt;"}, ...) </code></li>
	<p>finds the documents which depend on the filter in find</p>

  <li><code> it </code></li>
	<p>iterates through a cursor which is a pointer to a result set of a query</p>

  <li><code> .count()</code></li>
	<p>append on a <code>.find()</code> to count the number of documents which match the criteria</p>

  <li><code> .count()</code></li>
	<p>append on a <code>.find()</code> to count the number of documents which match the criteria</p>

  <li><code> .pretty()</code></li>
	<p>append on a <code>.find()</code> to make result shown look easier to read</p>

  <li><code> db.&lt;collectionName&gt;.findOne() </code></li>
	<p>finds the first document in the collection</p>

  <li><code> db.&lt;collectionName&gt;.insert({"&lt;key&gt;" : "&lt;value&gt;", ...}, ...) </code></li>
	<p>Insert documents into the collection, cannot insert something with the same <code>_id</code></p>

  <li><code> ...updateMany({"&lt;key&gt;" : "&lt;value&gt;", ...}, {"$&lt;operator&gt;" : {"&lt;key&gt;" : "&lt;value&gt;", ...}}) </code></li>
	<p>Update many matching documents with the new document values and corresponding operator</p>

  <li><code> ...updateOne({"&lt;key&gt;" : "&lt;value&gt;", ...}, {"$&lt;operator&gt;" : {"&lt;key&gt;" : "&lt;value&gt;", ...}}) </code></li>
	<p>Update one matching documents with the new document values and corresponding operator</code></p>

  <li><code> ...deleteOne({"&lt;key&gt;" : "&lt;value&gt;", ...}) </code></li>
	<p>Update one matching documents with the new document values and corresponding operator</code></p>

  <li><code> ...deleteMany({"&lt;key&gt;" : "&lt;value&gt;", ...}) </code></li>
	<p>Update one matching documents with the new document values and corresponding operator</code></p>
</ul>

---

## <b>Chapter 3 - Creating and Manipulating Documents</b>

### <b>ObjectID</b>
<ul>
	<li><b style="color:#32a852">_id</b></li>
	<p>Every document has a unique <b style="color:#32a852">_id</b> value</p>
  
  <li><b style="color:#32a852">ObjectID()</b></li>
	<p>Default value for the <b style="color:#32a852">_id</b> field unless specified</p>
</ul>

```JSON
    {"_id" : ObjectID("52cdef7c4bab8bd675297d8a")}
    {"_id" : "123-ABC-45"}
  ```
### <b>Inserting multiple documents</b>
<ul>
	<li>When inserting multiple documents, they are inserted in the order that is listed in the arguments of the insert command</li>

  <li>If there is an error in the data being inserted, like a duplicate <code>_id</code>, the documents that come after the duplicate, are not inserted</li>

  <li>Can add <code>{[{...},{...}...], {"ordered": false}}</code> to continue inserting documents with unique <code>_id</code></li>  
</ul>

### <b>Updating documents</b>

### <b>Updating operators</b>
<ul>
	<li><b style="color:#32a852">$inc</b></li>
	<p>Increment a field(s) by a specified amount</p>
</ul>

```JSON
{"$inc" : {"<field1>" : <value>, ... }}
```
<ul>
	<li><b style="color:#32a852">$set</b></li>
	<p>Set a field(s) by the  specified amount. Any typos will result in an implicit creationn</p>
</ul>

```JSON
{"$set" : {"<field1>" : <value>, ... }}
```

<ul>
	<li><b style="color:#32a852">$push</b></li>
	<p>Adds an element to an array field</p>
</ul>

```JSON
{"$push" : {<field1> : <value1>, ... }}
```

### <b>Delete documents</b>

---

## <b>Chapter 4 - Advanced CRUD operations</b>

### <b>Query Operators</b>
All query operators used the same syntax as
```JSON
{"<field>" : {"$<operator>" : <value>}, ...}
```
<code>$eq</code> issued as the  default operator when an operator is not specified
<table>
	<tr>
		<th>Operator</th>
    <th>Meaning</th>
	</tr>
  <tr>
		<td>$eq</td>
    <td>=</td>
	</tr>
  <tr>
		<td>$ne</td>
    <td>&#8800;</td>
	</tr>
  <tr>
		<td>$gt</td>
    <td>&gt;</td>
	</tr>
  <tr>
		<td>$lt</td>
    <td>&lt;</td>
	</tr>
  <tr>
		<td>$gte</td>
    <td>&geq;</td>
	</tr>
  <tr>
		<td>$lte</td>
    <td>&leq;</td>
	</tr>
</table>


### <b>Logic Operators</b>
<table>
	<tr>
		<th>Operator</th>
    <th>Meaning</th>
    <th>Syntax</th>
	</tr>
  <tr>
		<td>$and</td>
    <td>Match all</td>
    <td><code>{&lt;operator> : [{statement1}, {...},...]}</code></td>
	</tr>
  <tr>
		<td>$or</td>
    <td>At least one</td>
    <td><code>{&lt;operator> : [{statement1}, {...},...]}</code></td>
	</tr>
  <tr>
		<td>$nor</td>
    <td>Fail to match</td>
    <td><code>{&lt;operator> : [{statement1}, {...},...]}</code></td>
	</tr>
  <tr>
		<td>$not</td>
    <td>Negate</td>
    <td><code>{&lt;operator> : {statement1}}</code></td>  
	</tr>
</table>


---

# MongoDB - M100 Notes

---
# MongoDB - M320 Notes

## <b>Patterns</b>
---
### <b>Attribute Pattern</b>

#### <b style="color:#32a852">What is the pattern for ? </b>
<ul>
	<li>Lots of similar fields</li>
  <li>Want to search across many fields at once</li>
  <li>Fields present in only a small subset of documents</li>
</ul>

#### <b style="color:#32a852">How to use pattern ? </b>
<ul>
	<li>Break the field/value pairs into a document</li>
</ul>

```JSON
{
  {"colour" : "red", "size" : "large"},
  {"colour" : "blue", "size" : "small"}
}
/* gets transformed into */
{[
  {{"k" : "color", "v":"blue"},{"k" : "size", "v":"large"}},
  {{"k" : "color", "v":"red"},{"k" : "size", "v":"small"}}
]}
```

#### <b style="color:#32a852">Use case Examples? </b>
<ul>
	<li>Characteristics of a product</li>
  <li>Set of fields all having the same value type</li>
</ul>

#### <b style="color:#32a852">Pros/Cons </b>
<ul>
	<li>Easier to index</li>
  <li>Allow for non-deterministic field names</li>
  <li>Ability to qualify the relationship of the original field and value</li>         
</ul>

#### <b style="color:#32a852">Summary </b>
<ul>
	<li>Orthogonal Pattern to Polymorphism</li>
  <li>Organization for</li>
  <ul>
    <li>Common fields that need to be searched across</li>
    <li>Fields that are rare or to help manage an influx of unpredictable fields</li>
  </ul>
  <li>Reduces the number of indexes</li>  
  <li>Transpose the key/values as an array of sub-documents</li>       
</ul>

---
### <b>Extended Reference Pattern</b>

#### <b style="color:#32a852">How to manage Duplication </b>
<ul>
	<li><b style="color:#">Minimize</b></li>
	<ul>
		<li>Select the fields that do not change often</li>
    <li>Bring only fields you need</li>
	</ul>
  <li><b style="color:#">After source is updated</b></li>
	<ul>
		<li>What extended references to be changed</li>
    <li>When should the extended references be updated</li>
	</ul>
  <li><b style="color:#">Sometimes duplication may be better than a unique reference</b></li>
</ul>

#### <b style="color:#32a852">What is the pattern for ? </b>
<ul>
	<li>To avoid joining data at query time, data is pre-joined</li>
</ul>

#### <b style="color:#32a852">How to use pattern </b>
<ul>
	<li>Identify the fields on the lookup side</li>
  <li>Append those fields into the main object</li>
</ul>

#### <b style="color:#32a852">Use Case Examples ? </b>
<ul>
	<li>Mobile Applications</li>
  <li>Real-time Analytics</li>
</ul>

#### <b style="color:#32a852">Pros/Cons </b>
<ul>
	<li>Faster Reads, as the documents required are embedded in the main object</li>
  <li>Reduces the number of joins and lookups</li>
  <li>May introduce lots of duplication if extended reference fields that change a lot</li>
</ul>

---

### <b>Subset Pattern</b>
#### <b style="color:#32a852">What is the pattern for ? </b>
<ul>
	<li>To reduce the size of the working set that is too large to fit in RAM</li>
  <li>Usually, a large subset of the data from a document is rarely needed</li>
</ul>

#### <b style="color:#32a852">How to use pattern </b>
<ul>
	<li><b style="color:#">Split collection into 2 sub collections</b></li>
	<ul>
		<li>Most used part (small size) and least used part (larger size) of documents</li>
	</ul>
  <li><b style="color:#">Duplicate part of a 1-N or N-N relationships</b></li>
</ul>

#### <b style="color:#32a852">Use Case Examples ? </b>
<ul>
	<li>Lists of anything that contains a lot of data to process or read or take a substantial amount of memory</li>
  <li>For example a list of reviews</li>
</ul>

#### <b style="color:#32a852">Pros/Cons </b>
<ul>
	<li>Smaller working sets so documents retrieved faster</li>
  <li>More round trips from and to server, with more space used in disk as data is duplicated</li>
</ul>

#### <b style="color:#32a852">Summary </b>
<ul>
	<li>Reduces working set by splitting information</li>    
</ul>

---

### <b>Computed Pattern</b>

#### <b style="color:#32a852">Types of operations </b>
<ul>
	<li><b style="color:#">Mathematical Operations</b></li>
	<ul>
		<li>An example would be if you had to sum numerical data that changes/gets updated</li>
    <li>To reduce computations, sum data as it comes in (rolling sum) instead of calculating it from scratch</li>
    <li>Reduces the number of read and write operations</li>
	</ul>
  <li><b style="color:#">Fan Out Operations</b></li>
  To do many tasks to represent one logical task
  <ul>
		<li>It is better to fan out on writes by grouping data at write time so during read time, it does not need to fan out.</li>
  </ul>
  <li><b style="color:#">Roll up Operations</b></li>
  Merge data together
  <ul>
		<li>Grouping categories such as time based data from smaller to larger intervals </li>
    <li>Mathematical computations are roll-ups as well </li>
    <li>Doing these operations at write time, saves computational costs at read time </li>
  </ul>
</ul>

#### <b style="color:#32a852">What is the pattern for ? </b>
<ul>
	<li>To avoid repeating computational tasks at read time, especially if they are expensive</li>
  <li>Executed on data that is frequent and produces the same result</li>
</ul>

#### <b style="color:#32a852">How to use pattern </b>
<ul>
	<li>Perform the operations at write times, and store the result in an appropriate document and collection </li>
  <li>Keep the sources of data for computation if required later on, or for analytics </li>
</ul>

#### <b style="color:#32a852">Use Case Examples ? </b>
<ul>
	<li>IOT</li>
  <li>Event Sourcing</li>
  <li>Time Series Data</li>
  <li>Frequent Aggregation Framework queries</li>
</ul>

#### <b style="color:#32a852">Pros/Cons </b>
<ul>
	<li>Read queries are faster</li>
  <li>Saving on resource such as CPU and disk</li>
  <li>Use it when you need it, as it may add complexity</li>
</ul>

#### <b style="color:#32a852">Summary </b>
<ul>
	<li>Avoid performing similar operations many times</li>    
</ul>