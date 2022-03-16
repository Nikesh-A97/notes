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
</ul>

---