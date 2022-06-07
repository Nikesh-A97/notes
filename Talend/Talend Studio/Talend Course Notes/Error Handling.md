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

---
##### Trigger Types
- Subjob triggers begin from the start component of a subjob and connects to the leftmost component of the other subjob
- Component triggers begin from the component and connect to the leftmost component of the other subjob 

<span style="color:red">OnSubjobError</span>
- Triggeres when an **error** occurs **anywhere** in the **subjob**

<span style="color:green">OnSubjobOk</span>
- Triggeres when the **subJob** is completed **without errors**

<span style="color:red">OnComponentError</span>
- Triggeres when an **error** occurs in the **component** the trigger starts from

<span style="color:green">OnComponentOk</span>
- Triggeres when an **error** occurs in the **component** the trigger starts from

<span style="color:orange">RunIf</span>
- Triggeres when the custom **condition** is met

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
