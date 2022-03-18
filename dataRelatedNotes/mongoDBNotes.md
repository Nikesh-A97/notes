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