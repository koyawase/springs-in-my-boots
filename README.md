# springs-in-my-boots

Just learing how to build APIs using SpringBoot framework

## Docker notes

This project uses postgres hosted locally on Docker as the DB. Just so I can save some $$$ instead of having to host it...

After docker is installed and working on machine, run this command to create a postgres container 

`docker run --name container-name -e POSTGRES_PASSWORD=mysecretpassword -d -p 5432:5432 postgres:alpine` where you name the container and create your postrgres password.

run `docker ps` to see the container running

Use the `CONTAINER ID` given from previous `docker ps` command to SSH into the postgres container. e.g. `docker exec -it xxxxxxxxxxxx bin/bash`where xxxxxxxxxxxx is the CONTAINER_ID. Note that `docker exec -it` may not work on certain CLIs on windows, but it should work on powershell.

Once you have SSHed into container, enter postgres DB with command `psql -U postgres`.

From here you can now run SQL queries directly on the DB.

Create DB with `CREATE DATABASE springbootpostgresdb;`

Once DB is created, you can run the SpringBoot app locally throguh intelliJ or whatever IDE you're using and it will create the fist table from `src/main/resources/db/migrations` directory.

Run whatever SQL query you want now - e.g. `SELECT * FROM person`;
