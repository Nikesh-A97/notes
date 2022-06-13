# Jenkins

### What is Jenkins ?
- A continuous integration tool that allows continuous development, test and deployment of newly created codes
- Continuous Build & Integration
  - Commit changes to source code
  - Code is pulled whenever there is a commit made to the source code
  - All the changes made to the source code is built continuously

### What is Continuous Integration
- Code is sent by devs to a repo which is then sent to a CI server
- The CI server has tests (by testers) to check code for errors
- If there's an error it can be fixed by devs
- If not then it can be released and deployed

### Typical CI Tools (Open Source)
- Bamboo 
  - CI tool that runs multiple builds in parallel for faster compilation
- Buildbot 
  - Framework for automating software build, test and release
- Gump
  - Build and test all open source Java projects
- Travis CI
  - Hosted distributed cont. integration service used to build and test software hosted on GitHub
- Jenkins
  - Central tool to automate software development

### Feature of Jenkins
- Self contained Java-based program ready to run on all OS
- Easy configurations to setup and configure via the web interface
- Has hundreds of plugins and can create custom ones as well
- Very extensible, and highly configurable
- It can easily distribute work across multiple machines helping in faster builds, tests & deployment

### Jenkins Pipeline
- Development -> Code commit -> Build -> Test -> Release -> Deploy -> Production
- This process is automated

### Jenkins Architecture 
- Developers commit changes to the source code
- Jenkins server checks and pulls any new code from the repo at regular intervals
- The Build Server builds the code into an executable file. Feedback is sent if build fails
- Then jenkins deploys the build on to a test server. Usually written in Selenium 

### Jenkins Parent - Child Architecture
On request of the (parent) server the workload sent from the code repo is distributed amongst the children.
These children run build version of code for different OS versions or multiple versions

- Remote Source Code Repo
  - Jenkins Server (Parent)
    - Jenkins (windows) Child
    - Jenkins (linux) Child
    - Jenkins (mac) Child

---

## Some Jenkins Configs 

### Manage Jenkins

#### Configure System

- Number of Executors
  - The number of jobs that can be executed in parallel