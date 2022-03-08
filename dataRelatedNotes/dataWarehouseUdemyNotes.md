# Data Warehouse Fundamentals for Beginners

## <b>Data warehousing concepts</b>

### <b>What is data warehouse ?</b>
- Essentially just a large store of data accumulated from a wide range of sources
- Data Warehouse <b style="color:Red">&#8800;</b> Database 
- Data is <b style="color:Green;">copied</b> <b>not</b> <b style="color:Red">moved</b>
- Data is <b style="color:#f08f18">restructured</b> and <b style="color:#f08f18">re-organized</b>
- Why ? - To support data driven decision making.
#### <b>Rules for Data warehousing (Bill Inmon 1990)</b>
- <b style="color:#0FBAF1">Integrated</b> 
  <p>data from multiple source systems --> data warehouse</p>
- <b style="color:#0FBAF1">Subject Oriented</b> 
  <p>Regardless of data , must be re-organized.</p>
- <b style="color:#0FBAF1">Time Variant</b> 
  <p>Contains current and historical data. Look at change over time</p>
- <b style="color:#0FBAF1">Non - Volatile </b> 
  <p>Remains stable between refreshes and does not change</p>

### <b>Reasons to build a data warehouse</b>
- <b style="color:#0FBAF1">Data Driven Decisions</b>
  <p>Need a view of past, present, future and the unknown for business decisions. Tell something important from the data. Also known as <b>BI</b></p> 
- <b style="color:#0FBAF1">One stop Shopping</b>
  <p>Easier to access data as the data is <b b style="color:#f08f18">integrated</b> from multiple sources</p>

### <b>Data Virtualization</b>
- <b style="color:#0FBAF1">Read only</b>
  <p>Cannot change the data at the source</p>
- <b style="color:#0FBAF1">Do not copy</b>
  <p>Data accessed at source whenever needed and manipulated</p>
<p>Useful when there are 
  <b b style="color:#f08f18">simple transformations</b>,
  <b b style="color:#f08f18">small # of data sources</b> and a
  <b b style="color:#f08f18">relaxed response time</b>  
</p>

### <b>Data Lake VS Data Warehouse</b>
<p>To simply put it, a data lake is vast pool of <b style="color:#f08f18">raw, unstructured</b> data and a data warehouse has <b b style="color:#f08f18">structured</b> processed data</p>

- <b style="color:#0FBAF1">Data Warehouse</b>
  <p>A data warehouse is built on-top of RDBMS or MDBMS </p>

- <b style="color:#0FBAF1">Data Lake</b>
  <p>A data lake is built on-top of a big data environment</p>

### <b> Big Data and 4Vs </b>
#### <b>The four Vs for Big Data</b>
- <b style="color:#0FBAF1">Volume</b>
  <p>Helps handle extremely large volumes of data</p> 
- <b style="color:#0FBAF1">Velocity</b>
  <p>Supports the rapid intake of big data</p> 
- <b style="color:#0FBAF1">Variety</b>
  <p>Different variety in the types of data, such as audio files, emails and complex documents</p>
- <b style="color:#0FBAF1">Veracity</b>
  <p>The quality of the data to be analyzed, how <b style="color:#f08f18">reliable/significant</b> the data is</p>
<p>Data warehousing typically deal with more structured data like dates or small character strings but it can deal with other types of data with the help of extra tools</p>

### <b> Data Warehousing + Lakes + Virtualization </b>
- <p>Warehousing along with Lakes and Virtualization can all be a part of decision making and analytics</p>

### <b> Simple End to End data warehousing environment </b>
<p> Data from sources is copied and transformed to a data warehouse via a process called <b style="color:#f08f18">ETL</b></p>

- <b style="color:#0FBAF1">Extract</b> the data from the source by copying
- <b style="color:#0FBAF1">Transform</b> Transform the data to make it understandable and useable
- <b style="color:#0FBAF1">Load</b> Load the data into systems, creating a warehouse to be used by end users

----

## <b>Data warehousing Architecture</b>
### <b>Centralized data warehouse</b>
- A single data warehousing environment
- All data goes into a <b style="color:#f08f18"> single </b> database
- Advantage is that it's all together in one place
### <b>Data Mart</b>
- <b style="color:#f08f18"> Dependent </b> data marts depend on the data warehouse to obtain specific data
- <b style="color:#f08f18"> Independent </b> data marts does not require a data warehouse and draws from 1 or more sources.
  | <b style="color:#0FBAF1">Dependent</b> | <b style="color:#0FBAF1">Independent</b> |
  | -------------------------------------- | ---------------------------------------- |
  | data from warehouse                    | data from applications / systems         |
  | uniform                                | not uniform                              |
  | architecturally straightforward        | "spaghetti" architecture                 |

### <b>Data Warehouse VS Independent Data Mart</b>
They are basically the same except for the number of data sources
  | <b style="color:#0FBAF1">Data Warehouse</b> | <b style="color:#0FBAF1">Data Mart</b> |
  | ------------------------------------------- | -------------------------------------- |
  | Many sources (```50+```)                    | Few sources (```1-6```)                |

### <b>DW Architectural Options</b>
dataWarehouseTree.png

#### <b> Centralized </b>
- Default option, one stop shopping, modern tech
- High cross-org cooperation, data governance, ripple effects

#### <b> Centralized - EDW </b>
- Building a DW to satisfy the analytical needs for an enterprise
- Can go further to use relational or specialized databases

#### <b> Centralized - Data Lake </b>
- Sometimes a Data Lake is required
- Platforms such has Hadoop, AWS S3


#### <b> Component-Based </b>
- Divide data into multiple components, isolating environments from changes
- Mix-match tech
- Bolt together components 
- Inconsistent data, difficult to cross-integrate.

#### <b> Component-Based - Architected</b>
- Built with DWs + DMs or just DMs
- With DWs + DMs, the DMs would be dependent or front-end DMs (reverses order of data flow for DMs and DWs)  

#### <b> Component-Based - Un Architected</b>
- Built with DMs
- DW Bus , follows conformed dimensions, follows apples ->  to apples
- Considers all DMs in decision making.

### <b>Cube and MDBMS</b>
- Not a relational database (RDBMS)
- Dimensionally aware
- Fast query times
- "modest" data volumes (`<100GB`>)
- less flexible data structures
- nowadays take advantage of both RDBMS and MDBMS and can be used together

### <b>Operational Data Store (ODS)</b>
- Similar to a DW but only focuses on current operational data
- Realtime data comes in, instead of waiting for the next data refresh to update the database.
- <i>"Tell me what is happening right now"</i> is the focus of an ODS
- ODS and DW can coexist and users would pick depending on their needs
- Another option would be data would go into ODS then to a DW
- Can be used with all the other options (DWs, DLs and DVs)

### <b>The layers in a DW</b>
<p> A data warehouse has the following two layers <p>
<ul>
  <li> <b style="color:#0FBAF1">Staging</b> </li>
  <p> A <i>"landing zone"</i> for incoming data from the source</p>
  <li> <b style="color:#0FBAF1">User Access</b> </li>
  <p> Where users access the DW and DMs to obtain data for analytics and decision making</p>
</ul>

#### <b> The Staging Layer </b>
<ul>
  <li>Data needs to be pulled from source systems quickly and non-intrusively </li>
  <li>Focus on the <b style="color:#f08f18">E</b> more than <b style="color:#f08f18">T</b> of <b style="color:#f08f18">ETL</b> when integrating data from the source </li>
</ul>

#### <b> Different types of staging layers </b>
<ul>
  <li> <b style="color:#0FBAF1">Non - Persistent</b> </li>
  <p> After ETL and the user access layer has the data, the staging layer is emptied out </p>
  <p> Less storage but would require to go back to source if QA is required </p>
  <li> <b style="color:#0FBAF1">Persistent</b> </li>
  <p> The same as non - persistent except the data in the staging layer is kept </p>
  <p> More storage but do not need to go back to source however there is a risk of ungoverned access </p>
</ul>

---