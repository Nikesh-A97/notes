# Using Git in Talend Studio
##### Git in a Talend Project
- The project is stored and synchronized on the remote repository
- A worrking version is stored in the local repository on every developer machine
---
##### Git working tree, index, commit
**Working Tree**
- Files that you are currently working on

**Index**
- Staging area stores all changes before commit operation
- Changes made in working tree and not commited they need to be staged first

**Commit**
- Records changes that were made to files
- Can see every change made and view all changes

---
##### Git in Talend Projects
- Talend supports
	- GitHub (recommended)
	- GitLab
	- BitBucket
	- Gitblit
- Branches and actions are displayed in a menu on top of the Studio Repository
- Devs can develop on remote branches
	- Similar to one with an SVN repo
- Devs can create their own local branches
	- Push to own branches
	- In control of merging to master branch when needed
- Unlike SVN repositories it is not the role of the Talend Admin to create and manage branches
----
##### Why Git for Talend
- Compliant with other Java dev cycles
- Devs can work locally and merge when their items are ready
- Lighter than SVN branches
- Allows isolation of deveoplment and unit tests