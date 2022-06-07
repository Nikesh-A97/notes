# Context Variables
- These variables are used to run Jobs with different configurations that depends on the execution context. 
---
##### What is a Context
- A Job always runs a specific context
- Different **Configurations** can be represented by several contexts
- Context is used to configure a Job for the standard environments of the SDLC such as development, test and production
---
##### Context Examples
- In a development env. a Job will use local resources and replicas of DBs
- In a production env. the same Job will run using Cloud resources and production DBs instead
- In a test env. a Job does not connect to the production or replica DB but to a specific set of data
---
##### Context Variables
- Are used in a job
- Take on the value depending on the context in which the Job is being run
- Specify the value to use by changing the context in which you run the Job
---
##### Defining Context Variables
1. Manage Contexts
	- Create new contexts and rename default ones
	- ![[context_1.png]]
2. Select default context environment
	- ![[context_2.png]]
3. Add Variables
	- ![[context_3.png]]
	- Can also import variables using Context Groups 
4. Select Values
	- ![[context_4.png]]
	- Context values are either assigned values statically or interactively
---
##### Best Practices
- **Never** activate a prompt for the production context as the Job must run in the production env. without human intervention
- Always use the same context names, helps when merging contexts from different sources
- Document your settings by using the comment column in the context table
---
##### Using Context Variables
- Access a context vairbale by using the following construction `context.VariableName`
- ![[context_5.png]]
- Repository context variables are attached to context groups
- Can be used across multiple jobs
- ![[context_6.png]]
---
##### Creating Variables for a DB
- Export all parameters in a new context group when editing DB metadata
- ![[context_7.png]]
---
##### Running a Job in a context
- In the Run view, specify the execution context
- The context, variables and values are shown
- When the context changes the values are updated but cannot be changed
- ![[context_8.png]]
---
##### Updating context variables
- Using the  `tCnotextLoad` component you can overwrite the variable values for a Job
- You can load these new values from a Flow, for instance by reading the delmited file
- This allows you to update the variable values from outside the Job by modifying the file
- Using the `tContextDump` component you can export the variable values of a Job
