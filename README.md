# AWESOME
Awesome-Namtv1996 - Including utilities, notes collected by me during software development, throuh the projects I have worked on
## DOCKER
### Pull and run command sqlserver image on linux and amd64 platforms
```power shell
docker pull mcr.microsoft.com/mssql/server 
```
```power shell
docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=Abc123456@" -p 1433:1433 --name sql1 -d mcr.microsoft.com/mssql/server
```

### Pull and run command sqlserver image on macbook M1 chip
```power shell
docker pull mcr.microsoft.com/azure-sql-edge
```
```power shell
docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=Abc123456@" -p 1433:1433 --name sql_edge -d mcr.microsoft.com/azure-sql-edge
```
### Restore database sql server with .bak file on Azure Data Studio

Setp 1: Move the .bak file to the docker container (sql server container) 

- First, let's create a folder inside container with the command 
```power shell
sudo docker exec -it sql_edge mkdir /var/opt/mssql/backup
```
 'sql_edge' : is the name of container running in docker 
- Now copy the database .bak file into that folder
```power shell
sudo docker cp data.bak sql_egde:/var/opt/mssql/backup
```
Step 2: Open Azure Data Studio > click restore button > choose 'Restore from: Backup file' > choose 'Backup file path: /var/opt/mssql/backup' > choose database > click restore button > success!
