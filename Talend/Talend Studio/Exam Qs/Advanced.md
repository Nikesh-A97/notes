# Exam questions
---
## Git Workflow

**Which git development line supports the continuation for ongoing development ?**
- <span style="color:#32A852">Master </span>

**Which Git command can be used to fetch and download the latest file content from a remote branch or repository and immediately update the local repository to match that content ?**
- <span style="color:#32A852">Pull and Merge Branch </span>

**Where can a developer establish a connection to a remote project ?**
- <span style="color:#32A852">Talend Studio Manage Connection window </span>

**Talend Administration Center can only centralize the management access and administration of Talend Studio Projects ?**
- <span style="color:#32A852">False </span>

**Git Allows multiple developers to work on the same project?**
- <span style="color:#32A852">True </span>

**Talend studio Jobs can be managed using a revision control software?**
- <span style="color:#32A852">True </span>

**Developers can connect to remote projects when permissions are granted in Talend Administration Center**
- <span style="color:#32A852">True </span>

----
## Jobs

**The JobServer service must run on the developer's machine to execute Job within Talend Studio ?**
- <span style="color:#32A852">False </span>


**Which procedure can be used to stop the execution of the Job in progress and remove the displayed monitoring information from the Designer workspace?**
- <span style="color:#32A852">Click the Kill and Clear buttons in the Debug Run tab </span>

**How to compare and view jobs ?**
- <span style="color:#32A852">Right click job --> Compare Job --> Compare View --> Select Jobs to compare</span>

**Text information for a Job?**
- <span style="color:#32A852">Add a note in the design workspace</span>
- <span style="color:#32A852">Edit comments in the doc tabs for different components</span>


----
## Joblets

**How does refactoring components to a joblet impact the performance of a job?**
- <span style="color:#32A852">It has no drawbacks on the Job performance </span>
  - <span style="color:#32A852">At runtime, Joblet code is integrated into the Job itself</span>


**Where in Talend Studio can you find Joblets?**
- <span style="color:#32A852">Repository --> Joblet Designs</span>
- <span style="color:#32A852">Pallette --> Joblet Designs</span>

**Generic INPUT component for Joblet design ?**
- <span style="color:#32A852">Carrying data into Joblet</span>


----

## Subjob

**How do you prevent a sub-job from running without deleting it**
- <span style="color:#32A852">Right click a component in the sub-job and click Deactivate current sub-job</span>



----

## Parallelization

**At Job Runtime a developer wants to execute only a section of subjob in parallel, what component should be added to the Job workspace?**
- <code style="color:#32A852">tParallelize</code>


**Automatic parallelization divides the Job execution into multiple threads using four steps, partition --> collect --> de-partition --> and recollect ?**
- <span style="color:#32A852">True </span>


**What is the result of setting multithread execution ?**
- <span style="color:#32A852">Each subjob runs simultaneously rather than sequentially </span>


**Which of the following is true regarding parallel execution for DBs with Talend Studio?**
- <span style="color:#32A852">It is independent of multithread execution</span>
- <span style="color:#32A852">Must run on a system with multiple cores/processors for it to be an advantage</span>
- <span style="color:#32A852">Parallel execution is for the component itself and the containing subjob</span>
- <span style="color:#32A852">You set it on specific DB components</span>

----
## CDC

**What is the default mode of a CDC components in Studio**
- <code style="color:#32A852">Trigger</code>
  - The trigger mode is mostly used for maintaining the integrity of the information on the DB

**A Subscriber uses information captured in a change data capture database to update other databases**
- <span style="color:#32A852">True</span>

**The purspose of CDC DB component is**
- <span style="color:#32A852">To retrieve the changed records from a specific table based on CDC information</span>

**What is CDC**
- <span style="color:#32A852">Store DB changes so that you can then modify another DB with the changed records</span>

**Name of the table in the CDC DB that stores actual change ?**
- <span style="color:#32A852">tdcd_followed by the name of the monitored table</span>


**What happens when you create CDC under CDC Foundation for a db connection table?**
- <span style="color:#32A852">Create tables in the CDC DB to hold information about changed records</span>

**What happens when you Add CDC for a db connection table**
- <span style="color:#32A852">Create tables in the CDC DB to hold information about changed records</span>
- <span style="color:#32A852">Create entries in the CDC DB tables identifying what types of changes to monitor</span>

**A CDC tsubscribers table stores**
- <span style="color:#32A852">Name of the subscriber</span>
- <span style="color:#32A852">What kinds of change to monitor</span>
- <span style="color:#32A852">When the subscriber was created</span>

----

## Debugging

**Which button do you click to resume execution until the next breakpoint in the Traces Debug interface**
- <code style="color:#32A852">Breakpoint</code>

----

## Components

**Which statement defines a <code>tRowGenerator</code> component ?**
- <span style="color:#32A852">Generates as many records as required using random values take from a list</span>


**Which is required for a <code>tFileInputDelimited</code> component ?**
- <span style="color:#32A852">File Name, Field Separator, Schema</span>


**Components required to integrate Java code in Talend Job ?**
- <code style="color:#32A852">tJava</code> 
- <code style="color:#32A852">tJavaRow</code>
- <code style="color:#32A852">tJavaFlex</code>


**Which options are configured in the <code>tMemorizeRows</code> component ?**
- <span style="color:#32A852">The columns to memorize</span>
- <span style="color:#32A852">The number of rows to memorize</span>


**How do you see an error for a component ?**
- <span style="color:#32A852">From the problems view</span>
- <span style="color:#32A852">Place mouse over the error symbol in the design workspace</span>


**Which component helps process data by filtering out duplicate entries and then dumping the duplicates in a separate output flow component ?**
- <code style="color:#32A852">tUniqRow</code>


**Accurate description of <code>tUniqRow</code> component ?**
- <span style="color:#32A852">Output contains a single row for each unique combination of values in the columns listed in the Unique key table</span>


**Accurate description of <code>tAggregateRow</code> component ?**
- <span style="color:#32A852">The calculations specified in the Operations table are performed for each unique combination of values in the columns listed in the Group by table</span>


**Purpose of <code>tReplicate</code> component ?**
- <span style="color:#32A852">Duplicate incoming schema into identical output flows</span>

**Which component is associated with <code>tLogCatcher</code> component ?**
- <code style="color:#32A852">tDie</code>
- <code style="color:#32A852">tWarn</code>

----

## Views

**Which tab of the Component View do you enable the comment indicator ?**
- <span style="color:#32A852">Documentation</span>

**Which is required for a <code>tFileInputDelimited</code> component ?**
- <span style="color:#32A852">File Name, Field Separator, Schema</span>


----

## Context

**Pass value for context variable at runtime using a file or DB, what is Schema ?**
- <span style="color:#32A852">key;value</span>

**Purpose of a context group ?**
- <span style="color:#32A852">To organize a set of variables in the repository</span>



----

## DBs

**How do you create an SQL query from Talend Studio without using a component?**
- <span style="color:#32A852">Repo --> DB connection schema --> Edit queries</span>
- <span style="color:#32A852">Repo --> Generic schema --> Edit queries</span>

**How can you determine the previously unknown schema of a database table from within Talend Studio?**
- <span style="color:#32A852">db connection --> retrieve schema</span>


----

## Remote Server

**What extra information do you see in the Run view console output when you run a job on the remote server?**
- <span style="color:#32A852">Sending Job to server</span>
- <span style="color:#32A852">Deploying Job on server</span>



----