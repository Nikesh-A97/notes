# Restoring the AdventureWorksDW
---
## Setting up SQL server on Docker
This will explain how I hosted the MSSQL Server on Docker. An assumption is made that DockerHub for Desktop is already installed

### Dockerfile setup
The code used in the `.dockerfile` to build the image. 
```DOCKER
#Orignal soruce (slighly edited)
#https://www.sentryone.com/blog/restoring-an-adventureworks-database-on-a-sql-server-on-linux-container

FROM mcr.microsoft.com/mssql/server:2019-latest

ENV ACCEPT_EULA=Y
ENV SA_PASSWORD=<any-password-to-login>

USER mssql

#Assumes DB backups are in the same folder as the dockerfile
COPY AdventureWorksDW2019.bak /var/opt/mssql
COPY AdventureWorks2019.bak /var/opt/mssql
```
The following code will
- Pull the MSSQL server image
- Set the required environment variables for the server
- Set the user
- Copy the files from local machine to the docker container

### Docker-Compose Setup
The code used to setup the container. I opted to use docker compose file to run the image. 
```yaml
version: '1'
services:
	ms-sql-server:
		image: mssqlserver:latest
		ports:
			- 1433:1433
```
TODO : INSTRUCTIONS ON HOW TO COMPOSE AND RUN A DIFFERENT WAY

---
## Connecting to the DW
There are different ways to connect to the DW and setup the DB. I will be using Microsoft SQL Server Management Studio (SSMS).

### Using SSMS to connect


### Restore the DB
There are several ways to restore the DW and can be done by using 
- SSMS GUI
- TSQL commands in SSMS or directly in the docker container

#### Using SSMS GUI

#### Using TSQL commands
Can copy paste the following code by opening up a SQL Query
```SQL
--Instructions adapted from 
--https://codingsight.com/restoring-sample-dw-database-adventureworksdw2019/

RESTORE DATABASE [AdventureWorks2019]
FROM DISK = '/var/opt/mssql/AdventureWorks2019.bak'
WITH 
	 MOVE 'AdventureWorks2017' TO '/var/opt/mssql/data/AdventureWorks2019.mdf'
	,MOVE 'AdventureWorks2017_log' TO '/var/opt/mssql/data/AdventureWorks2019_log.ldf'
	,FILE = 1
	,NOUNLOAD
	,STATS = 5
GO
```