# Controlling Execution
---
##### File management
Some components for file management are
- `tFileList`
	- List files in a directory
- `tFileDelete`
	- Deletes files or a directory
- `tFileArchive`
	- Compresses files or a directory
---
##### Iterations 
- Components such as `tFileList` can be connected using only an **Iterate ** row 
- The iterate row is used to loop a process on files contained in the directory
- Other components can loop on rows contained in a file or on DB entries
- No main row option for connecting `fFileList`
- `tIterateToFlow` is used gather iterations in a processable Flow
- `tUnite` component is used to merge iterations after they are processed
- ![[iterations.png]]
---
##### Component Variables
- Each component has an associated list of predefined component variables
- These variables are used to keep track of component execution
- In a job, variables assigned to components are listed in the Outline view
- ![[componentVariables.png]]
- During Job execution the values of variables change and can be used by other components for dynamic configuration
- To get the list of component variables, while in a text fiel, type the component and press CTRL + SPACEBAR
- ![[componentVariables_2.png]]
---
##### Triggers
- Transfer control from one component or subJub to another
- Allows the implementation od different execution paths based on the **status** of a component/subjob or **specfic conditions** 
- Trigger connections do not carry data
---
##### Master Jobs
A master Job orchestrates child jobs
- Used for complex jobs that must be sequentialy
- Easy to use
- Done by using the `tRunJob` component
- Can be placed in the designer like any other component
- Offers three posibilites and do not need to have all variables for each context
- ![[masterJobs_1.png]]
---
##### Exporting Jobs
- Can export jobs in order to share, have as a back-up in case of removal or corruption
- Must be packaged with all dependencies to work in another Studio Instance
- ![[exportingJobs_1.png]]
---
##### Importing Jobs
- Select items prior to import
- Select **Overwrite existing Item** as needed to clear errors and warnings
- Resolve all errors in order to "Finish"