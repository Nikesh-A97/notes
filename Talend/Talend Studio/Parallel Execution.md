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

**Automatic Parallelization
- In some situations, Talend Studio can automate parallelization of portions of a subJob

---

##### `tParallelize` component
- Has triggers that allow connected subJobs to execute in parallel
- Provides greater control as compared to multi-threading the entire job
- Additional subJobss can run either in parallel or synchronously
- ![[tParallelizeExample.png]] 
- Other components such as `tPartitioner`, `tCollector`, `tDepartitioner`, `tCollector` can be used but not recomended as a new feature **Set Parallelization** exists.