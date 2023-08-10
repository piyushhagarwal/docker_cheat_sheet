# Postgres Docker Container Setup

This repository contains a Docker Compose configuration to set up a Postgres container.
Make sure you have Docker and Docker compose installed on your system before proceeding. Follow the steps below to get started:

## 1. Clone the Repository and Navigate to the Folder

```bash
git clone https://github.com/piyushhagarwal/docker_cheat_sheet.git
```
```bash
cd postgres
```
## 2. Build the Docker Container
Run the following command to build and start the MySQL container in the background:
```bash
docker-compose up -d
```
`-d` flag is to run the container in the detach mode.

## 3. Access the Container's Shell
To access the bash shell within the running container, use the following command:
```bash
docker exec -it <container_name_or_id> bash
```
For example:
```bash
docker exec -it postgres-container bash
```

## 4. Start the Postgres Client
Inside the container shell, you can start the Postgres client using the following command:
```bash
psql -U username -d database
```
Note that according to our compose file the username is `myuser` and the database is `mydb`.
```bash
psql -U myuser -d mydb
```

## 5. Use the database
Once you are logged in to the Postgres client, you can start using the MySQL database. For example, you can switch to a specific database using the following command:
```bash
\c <database_name>;
```
Note that according to our compose file we have created `mydb` database
```bash
\c mydb;
```
## 6. Stop and remove the container.
Remember to stop and remove the container when you're done:
```bash
docker-compose down
```

Note that your data wont be deleted after you remove the container because a volume is created in your docker. See the `docker-compose.yml` file for more clarity.
