# Advanced Exam questions
---
## Git Workflow

#### Which git development line supports the continuation for ongoing development ?
- Tag
- <span style="color:#32A852">Master </span>
- Switch
- Revision


#### Which Git command can be used to fetch and download the latest file content from a remote branch or repository and immediately update the local repository to match that content ?
- Commit
- Push
- <span style="color:#32A852">Pull and Merge Branch </span>
- Branch


#### Where can a developer establish a connection to a remote project ?
- Talend Studio using the Project Reference panel
- Talend Studio Run View
- <span style="color:#32A852">Talend Studio Manage Connection window </span>
- Talend Administration Center window


#### Talend Administration Center can only centralize the management access and administration of Talend Studio Projects ?
- True
- <span style="color:#32A852">False </span>


#### Git Allows multiple developers to work on the same project?
- False
- <span style="color:#32A852">True </span>


#### Talend studio Jobs can be managed using a revision control software?
- False
- <span style="color:#32A852">True </span>


#### Developers can connect to remote projects when permissions are granted in Talend Administration Center
- False
- <span style="color:#32A852">True </span>

----

## Jobs

#### The JobServer service must run on the developer's machine to execute Job within Talend Studio ?
- True
- <span style="color:#32A852">False </span>


#### Which procedure can be used to stop the execution of the Job in progress and remove the displayed monitoring information from the Designer workspace?
- Click the Advanced Settings tab and select Clear before running the job
- <span style="color:#32A852">Click the Kill and Clear buttons in the Debug Run tab </span>
- Click the Clear button in the Run view tab
- Click the Kill button in the Basic Run tab


----


## Joblets

#### How does refactoring components to a joblet impact the performance of a job?
- Speeds up the job at the expense of maintainability
- <span style="color:#32A852">It has no drawbacks on the Job performance </span>
  - <span style="color:#32A852">At runtime, Joblet code is integrated into the Job itself</span>
- It slows down the Job but improves maintainability
- Depending on various factors it can speed up or slow down the Job


#### Where in Talend Studio can you find Joblets?
- Repository --> Metadata --> Joblet Designs
- <span style="color:#32A852">Repository --> Joblet Designs</span>
- Repository --> Code --> Joblet Designs
- <span style="color:#32A852">Pallette --> Joblet Designs</span>


----

## Parallelization

#### At Job Runtime a developer wants to **execute** only a **section of subjobs** in **parallel**, what component should be added to the Job workspace?
- `tpartioner`
- <code style="color:#32A852">tParallelize</code>
- `tRowGenerator`
- `tDepartitioner`


#### Automatic parallelization divides the Job execution into multiple threads using four steps, partition --> collect --> de-partition --> and recollect ?
- <span style="color:#32A852">True </span>
- False

----


## CDC

#### What is the default mode of a CDC components in Studio
- Xstream
- <code style="color:#32A852">Trigger</code>
  - The trigger mode is mostly used for maintaining the integrity of the information on the DB
- Parallelization
- Redo/archive job

#### Where in Talend Studio can you store change data capture connections to be used in job
- Xstream
- <code style="color:#32A852">Trigger</code>
  - The trigger mode is mostly used for maintaining the integrity of the information on the DB
- Parallelization
- Redo/archive job

----

## Components

#### Which statement defines a <code>tRowGenerator</code> component ?
- Generates and sends threads to the components that follow it for parallel execution
- <span style="color:#32A852">Generates as many records as requrired using random values take from a list</span>
- Generates and sends threads using random values taken from list
- Generates and dispatches input records into a specific number of threads


----