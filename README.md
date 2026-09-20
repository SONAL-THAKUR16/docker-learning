# 🐳 Docker Learning

My notes and practice while learning Docker.

## 📌 What is Docker?

Docker is a platform used to build, run, and manage applications inside containers.

Docker helps developers create a consistent environment for running applications.

## 🧩 Important Docker Concepts

### Docker Image

A Docker image is a packaged template containing the application, dependencies, and required configuration.

Example:

```bash
docker pull mysql
```

### Docker Container

A Docker container is a running instance of a Docker image.

A container provides an isolated environment where an application can run.

Example:

```bash
docker run --name mysql-db -e MYSQL_ROOT_PASSWORD=1234 -d mysql
```

### Docker Engine

Docker Engine is the part of Docker that creates and runs containers.

### Docker Hub

Docker Hub is a registry where Docker images can be stored and shared.

Example:

```bash
docker pull mysql
```

## 🛠️ Basic Docker Commands

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

### Search for an Image

```bash
docker search mysql
```

### Remove an Image

```bash
docker rmi mysql
```

### Show Running Containers

```bash
docker ps
```

### Show All Containers

```bash
docker ps -a
```

### Run a Container

```bash
docker run mysql
```

### Run Container in Background

```bash
docker run -d mysql
```

### Start Container

```bash
docker start mysql-db
```

### Stop Container

```bash
docker stop mysql-db
```

### Restart Container

```bash
docker restart mysql-db
```

### Remove Container

```bash
docker rm mysql-db
```

## 🔌 Port Binding

Port binding connects a port on the host computer to a port inside the container.

### Syntax

```bash
docker run -p <host_port>:<container_port> <image_name>
```

### Example

```bash
docker run -p 8080:80 nginx
```

Here:

```text
8080 → Host port
80   → Container port
```

## 🔑 Environment Variables

Environment variables can be passed to a container using `-e`.

Example:

```bash
docker run -e MYSQL_ROOT_PASSWORD=1234 mysql
```

Here:

```text
MYSQL_ROOT_PASSWORD → Variable name
1234                → Variable value
```

## 💻 Docker Exec

`docker exec` is used to execute a command inside a running container.

### Enter a Container

```bash
docker exec -it mysql-db /bin/bash
```

### Enter MySQL

```bash
docker exec -it mysql-db mysql -u root -p
```

## 📋 Container Logs

To view the logs of a container:

```bash
docker logs mysql-db
```

## 🔍 Inspect Container

To view detailed information about a container:

```bash
docker inspect mysql-db
```

## 💾 Docker Volumes

Docker volumes are used to store persistent data.

They are useful for databases because important data can remain even when a container is removed.

### Show Volumes

```bash
docker volume ls
```

### Create a Volume

```bash
docker volume create mysql-data
```

### Use a Volume

```bash
docker run --volume mysql-data:/var/lib/mysql mysql
```

### Remove a Volume

```bash
docker volume rm mysql-data
```

## 🌐 Docker Networks

Docker networks allow containers to communicate with each other.

### Show Networks

```bash
docker network ls
```

### Create a Network

```bash
docker network create my-network
```

### Remove a Network

```bash
docker network rm my-network
```

## 💽 Check Docker Storage

To check how much storage Docker is using:

```bash
docker system df
```

## 🐳 Docker Hub Commands

### Login to Docker Hub

```bash
docker login
```

### Logout from Docker Hub

```bash
docker logout
```

### Search for an Image

```bash
docker search mysql
```

### Pull an Image

```bash
docker pull mysql
```

## 🗄️ MySQL Using Docker

I practiced running MySQL using Docker.

### Pull MySQL Image

```bash
docker pull mysql
```

### Run MySQL Container

```bash
docker run --name mysql-db -e MYSQL_ROOT_PASSWORD=1234 -d mysql
```

### Check Running Container

```bash
docker ps
```

### Enter MySQL

```bash
docker exec -it mysql-db mysql -u root -p
```

## 🧪 SQL Practice

After entering MySQL:

### Create Database

```sql
CREATE DATABASE college;
```

### Select Database

```sql
USE college;
```

### Create Table

```sql
CREATE TABLE students (
    id INT,
    name VARCHAR(50),
    age INT
);
```

### Insert Data

```sql
INSERT INTO students VALUES (1, 'Sonal', 20);
```

### View Data

```sql
SELECT * FROM students;
```

### Show Tables

```sql
SHOW TABLES;
```

## ⚖️ Image vs Container

| Image | Container |
|---|---|
| Packaged template | Running instance |
| Used to create containers | Runs the application |
| Example: `mysql` | Example: `mysql-db` |

## 💾 Container vs Volume

| Container | Volume |
|---|---|
| Runs the application | Stores persistent data |
| Can be removed | Exists independently |
| Data can be temporary | Used to preserve important data |

## 🔄 Docker Workflow

```text
Docker Hub
    ↓
Docker Image
    ↓
Docker Container
    ↓
Running Application
```

## 📚 Docker Learning Structure

```text
docker-learning/
│
├── README.md
│
├── commands.md
│
├── mysql/
│   ├── README.md
│   └── docker-compose.yml
│
└── examples/
    └── Dockerfile
```

## 🎯 Learning Goal

Continue learning Docker and use it with web development and backend projects.

## 📖 Reference

I used the Apna College Docker Cheat Sheet for Docker commands and practice.

👉 [Docker Cheat Sheet - Apna College](https://lwfiles.mycourse.app/62a6cd5e1e9e2fbf212d608d-public/publicFiles/Docker%20CheatSheet%20ApnaCollege.pdf)


## 🚀 Future Topics

- Dockerfile
- Docker Compose
- Multi-container applications
- Docker with Node.js
- Docker with Django
- Dockerizing web applications
- Building and pushing your own Docker images
