# MySQL Docker Container Setup

This repository contains a Docker Compose configuration to set up a MySQL container.
Make sure you have Docker installed on your system before proceeding. Follow the steps below to get started:

## 1. Clone the Repository and Navigate to the Folder

```bash
git clone https://github.com/piyushhagarwal/docker_cheat_sheet.git
```
```bash
cd my_sql
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
docker exec -it mysql-container bash
```

## 4. Start the MySQL Client
Inside the container shell, you can start the MySQL client using the following command:
```bash
mysql -u username -p
```
Note that according to our compose file the username is `john` and the password is `john`.
```bash
mysql -u john -p
```
You can also login through `root` using following command and password as `password`.
```bash
mysql -u root -p
```
You will be prompted to enter the password.

## 5. Use the database
Once you are logged in to the MySQL client, you can start using the MySQL database. For example, you can switch to a specific database using the following command:
```bash
USE <database_name>;
```
Note that according to our compose file we have created `random-app` database
```bash
USE random-app;
```
If you are logged in through user, you wont be able to create any new databases.
Login by root to create new databases if needed.

## 6. Stop and remove the container.
Remember to stop and remove the container when you're done:
```bash
docker-compose down
```

Note that your data wont be deleted after you remove the container because a volume is created in your docker. See the `docker-compose.yml` file for more clearity.
