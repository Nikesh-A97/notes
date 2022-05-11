# Joblet
---
##### What is a Joblet and why use one ?
- A component that replaces a group of components
- Often need to resuse a portion of a Job in other Jobs
- Some parts of Job may be complext so abstract it out to show less makes overall job less confusing
- ![[joblet_1.png]]
- It allows for reuse in the same or other jobs
- Easy to monitor the job
- No performance issues as the joblet is integrated into the Job itself
---
##### How to create a Joblet
- It can be created from scratch in a simlar way to how standard Jobs are created (from the repository window)
- From existing jobs by selecting the components and refactoring to Joblet
---
##### Working with Joblets
There are four Joblet specific components
- Input 
	- Data in
- Output 
	- Data out
- Trigger Input 
	- Can be used to start the Joblet
- Trigger Output 
	- Can be used to start a subjob after the Joblet
---
##### A comparison of Joblet and `tRunJob`
 | Joblet                                               | `tRunJob`                                           |
 | ---------------------------------------------------- | --------------------------------------------------- |
 | Design-time factoring                                | Run-time factoring                                  |
 | Similar to a macro that is pulled in at compile time | Calls specified Job at run-time                     |
 | Use Joblets if you have a common design to share     | Use a `tRunJob` to trigger or pass data across Jobs |
 
 ---
 