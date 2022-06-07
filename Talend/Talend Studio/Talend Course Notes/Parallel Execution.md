# Parallel Execution
---
##### Parallel Options in Talend Studio
- Enable mulithreading Job - wide
- Use the `tParallelize` component to orchestrate subJobs
- Leveraging parallel execution options available for specific components
- Utilizing the automatic parallelization components into you job
----

##### Processing related terminology
**Sequential Processing**
- No subjob is run until the previous subjob is completed 
- Also known as **synchronus** computing
- ![[subjob_sync.png]]

**Parallel Processing**
- Subjobs run at the same time
- Also known as **asynchronous** computing
- ![[subjob_async.png]]

**Multi-threading
- All unconnected subJobs run at the same time
- Since they are running at the same time it's **asynchronous**
- ![[subjob_multi.png]]
- Settings are changed in the **Extra Tab** for the job view

---
##### Parallelization Options

**Multithreading**
- By default project settings are applied and need to be changed in the **Extra tab** in the **Job View**
- ![[parallel_multithreadOptions.png]]

**Using components that support parallelized operations**
- Many components can enable the parallelized operations
- ![[parra_1.png]]

**Automatic Parallelization
- In many situations Talend Studio can automate the parallelization of the portions of a subJob
- ![[parra_2.png]]

**Using dedicated components to implement parallelization
- Place and configure dedicated components to achieve parallelization
- Not recomemed as it has been sicceeded by *Set Parallelization* feature
Component | Purpose 
 --- | --- 
`tPartitioner` | **Split** data into multiple **threads**
`tCollector` | **Collect threads** and send to next component
`tDepartitioner` | Group **output** threads
`tRecollector` | **Capture results** and **output** to next **component**



---

##### `tParallelize` component
- Has triggers that allow connected subJobs to execute in parallel
- Provides greater control as compared to multi-threading the entire job
- Additional subJobss can run either in parallel or synchronously
- ![[tParallelizeExample.png]] 
