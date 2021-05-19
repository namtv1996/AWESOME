# AWESOME
Awesome-Namtv1996 - Including utilities, notes collected by me during software development, throuh the projects I have worked on
# DOCKER
Pull and run command sqlserver images
```power shell
docker pull mcr.microsoft.com/mssql/server 
```
```power shell
docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=Ichiba12345@" -p 1433:1433 --name sql1 -d mcr.microsoft.com/mssql/server
```
