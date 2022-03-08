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