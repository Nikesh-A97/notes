# Java Code and Routines
##### Writing Java code in the components
- Java code can be written in *any* editable field in Talend Studio
	- The use of context or global variables and system routines are Java code in components
- Can use Java code as long as it fits within one line of instruction
- Cannot use entire blocks of code
- Can use the `tLibraryLoad` component to import Java libraries
---
##### `tJava` component
- Allows you to enter personlized code in order to integrate into your Talend job
- The code is only executed **once** and can be triggered by ...
	- Main row
	- `onComponent`
	- `onSubjob`
	- loop
	- if
- **Cannot** access rows of data
- Some scenarios 
	- Printing out a variable content
	- Setting a context or global variable

---
##### `tJavaRow` component
- Code that applies to each row of the flow
- **Can** access the rows of data and process them
- Used to generate code to map input data flow into output data flow
---
##### `tJavaFlex` component
- Enables you to add complex structured code
	- Split into *Start*, *Main* and *End* code
- **Can** access rows of data and process them
- Propogate data automatically
- Due to the way the code is split it can...
	- Instantitate objects and variables in the **Start** section of the code
	- Process rows of data in the **Main** section by using instances and variables
	- Destroy objects and clean the environment in the **End** section
---
##### Creating Routines
- Libraries of variables and calss methods that can be called within the Jobs
- Creating a new routine library generates a complete class skeleton
- Routines offer a very flexible solution to handle complex processing with Java code
- Routine libraries are stored and shared in the repository; thus they can be reused 
---
