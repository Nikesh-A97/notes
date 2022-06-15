# Docker

## Containers
- A container is a way to package application with all the necessary dependencies and configs
- Containers are portables --> makes development and deployment more efficient

### Where do containers live ?
- They are stored in the container repository
- Private repositories
- Public repository for Docker

### In application development containers are useful because...
- Own isolated environment
- Packaged with all needed configuration
- One command to install the app
- Developers and Operations work together to package the application in a container
- No environmental configuration needed on server

### Container breakdown
- Layers of images
- The base is a Linux base Image as it is small in size
- Application image at the top

## Docker VS Virtual OS
- OS have 2 layers , the kernel and application
- Both are virtualization tools
- Docker virtualize the application layer only and uses host kernel
- VM virtualize both layers