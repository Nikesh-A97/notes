# Handling Errors
----
##### Error handling
When a component encounters an error, for example the input file is missing you either
- **Stopping** as soon the error is encounterec
- **Continue** to completion despite the error
-----
##### Die on Error 
- is avaible for components which stops the Job if the component fails
----
##### Triggers 
- Transfer control from one component to another
- Allows implementation of different execution paths based on
		- the status of a component
		- other specific conditions
----
##### Kill Jobs in specific conditions
**Requirement**
- Kill a job even if no technical error has occured
- An example would be if an input file has less than a certain number of lilnes

**Soulution**
- Use a `tDie` component to kill the job
- Use a `Run If` trigger
- Configure the condition in the component view
---
##### Raising a warning
**Requirement**
- Raise a warning when a business rule is not followed
- An example would be if an output file has fewer lines than the input

**Solution**
- Use a `tWarn` component to raise the warning
- Use a `Run If` trigger
- Configure the condition
---
##### Logging level
Configure the logging level with `log4jlevel`
- Available on the Advanced settings tab of the Run view
- Specifies types of log messages to be displayed
- Can globally change the level for all Jobs in project properties
---
