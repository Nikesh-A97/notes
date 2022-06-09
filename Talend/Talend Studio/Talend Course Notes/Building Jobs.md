# Jobs
---
##### Exporting a Job
- Bundles a Job and its dependencies  into a shareable format
- Exported Job is only usable within Talend Studio
- Useful for collaboration, back-ups or training
---
##### Building a Job
- Bundles a Job and its dependencies in a stand-alone format
- Job can be run anywhere
- Delivers flexible deployment options
---
##### Building  a stand-alone Job
Builds an archive that contains
- **.jar** files
- Package or files needed for deployment
- **Contexts** and **variables**
- **.bat** files for Windows platform
- **.sh** for Linux platforms
---
##### Job versions
- Can control the version of the job with (`major.minor`) numbering scheme
- Can select the version when building the job
---
##### Building a Job as a Docker image
- To build a Docker image you mus provide
	- Connection to the docker host
	- Image name and tag
- The context usage and default context are configurable
- Studio uses a base image as a template to create a dedicated image that contains everything needed to run the Job in different environments
---
##### Docker topology
- **Image**
	- A package that contains the Job and everything needed to run it
- **Container**
	- A running instance of an image
- **Daemon**
	- A service installed on the Docker host
	- Responsible for images and containers mangement
- **Docker CLI**
	- A client used to interact with the Docker Daemon
---
##### Container Benefits
- ![[container_benefits.png]]