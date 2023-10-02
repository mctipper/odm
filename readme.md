  
# ODM Playground  
  
Simply playground with multiple databases to safely play.  

## Setup

`docker compose up --build -d` will build all the necessary containers. Security and structure isn't very important.  
`docker-compose.yml` is just expanded upon the one provided by [ODM Quickstart](https://docs.open-metadata.org/v1.1.x/quick-start/local-docker-deployment), adding in additional databases.  

When adding new connections in OpenMetaData use `host.docker.internal` and NOT `localhost`.

## Links  

OpenMetaData: [`localhost:8585`](localhost:8585) admin / admin  
Airflow: [`localhost:8080`](localhost:8080) admin / admin  

## Databases  

Amended version from [SQL Server Tutorial](http://www.sqlservertutorial.net/load-sample-database/), split between 3 databases.  
Files in `db_init` dir create and populate data.

### Products  

Postgresql  
Port: 5432  
postgres_user / postgres_password  

### Sales  

Mariadb
Port: 33020  
root / root

### Orders

Mysql  
Port: 33030  
root / root  

nb. this database contains the 'orders' tables from SQL Server Tutorial. As well as a couple of _views_ generated in the database init sql file.

TODO - generate and populate a table in this database outside of db init files, utilising multiple databases. Basic python script should be enough, no need to bother with ORM or anything just a few pandas manip queries and upload the result should be enough really.
