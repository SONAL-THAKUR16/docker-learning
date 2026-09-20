# 🐳 Docker Learning

## What is Docker?

Docker is a platform used to build, run, and manage applications inside containers.

## Docker Image

A Docker image is a packaged template used to create containers.

Example:

```bash
docker pull mysql
```

## Docker Container

A container is a running instance of a Docker image.

Example:

```bash
docker run --name mysql-db -e MYSQL_ROOT_PASSWORD=1234 -d mysql
```

## Basic Docker Commands

### Check Docker Version

```bash
docker --version
```

### Pull an Image

```bash
docker pull mysql
```

### Show Images

```bash
docker images
```

### Show Running Containers

```bash
docker ps
```

### Show All Containers

```bash
docker ps -a
```

### Stop Container

```bash
docker stop mysql-db
```

### Start Container

```bash
docker start mysql-db
```

### Enter MySQL Container

```bash
docker exec -it mysql-db mysql -u root -p
```

### Check Docker Storage

```bash
docker system df
```

## MySQL Using Docker

I practiced running MySQL using Docker.

```bash
docker pull mysql

docker run --name mysql-db -e MYSQL_ROOT_PASSWORD=1234 -d mysql

docker ps

docker exec -it mysql-db mysql -u root -p
```

## SQL Practice

After entering MySQL:

```sql
CREATE DATABASE college;

USE college;

CREATE TABLE students (
    id INT,
    name VARCHAR(50),
    age INT
);

INSERT INTO students VALUES (1, 'Sonal', 20);

SELECT * FROM students;
```

## Image vs Container

| Image | Container |
|---|---|
| Template | Running instance |
| Used to create containers | Runs the application |
| Example: `mysql` | Example: `mysql-db` |

## Learning Goal

Continue learning Docker and use it with web development and backend projects.
