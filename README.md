

##  Docker Learning Repository (Practical DevOps)


# Docker Practical Learning Repository 

This repository is created for **learning Docker through hands-on practice** as part of my **DevOps learning journey**.

The goal of this repository is to understand Docker fundamentals by:
- Writing Dockerfiles
- Building Docker images
- Running containers
- Managing containers using CLI and Portainer
- Understanding container lifecycle and best practices



##  What I Am Learning

- Docker architecture (Client, Daemon, Images, Containers)
- Dockerfile instructions
- Building images with `docker build`
- Creating and running containers with `docker run`
- Container persistence using volumes
- Running applications inside containers
- Basic container management (start, stop, remove)
- Using Portainer as a Docker GUI



##  Technologies Used

- **Docker Engine**
- **Docker CLI**
- **Dockerfile**
- **Node.js (for sample containers)**
- **Ubuntu Linux**
- **Portainer (Docker UI)**



##  Project Structure

```

docker-learning/
│
├── hello-docker/
│   ├── Dockerfile
│   ├── hello.js
│   └── README.md
│
└── README.md

````


## Example: Simple Node.js Docker App

### hello.js

```js
console.log("Hello Docker! This is my first container ");
````

### Dockerfile

```dockerfile
FROM node:20-alpine

WORKDIR /app

COPY . .

CMD ["node", "hello.js"]
```



##  Build Docker Image

Run this command inside the project folder:

```bash
docker build -t hello-docker .
```



##  Run Docker Container

```bash
docker run --rm hello-docker
```

Expected output:

```
Hello Docker! This is my first container 
```


##  Useful Docker Commands

| Command                  | Description             |
| ------------------------ | ----------------------- |
| `docker images`          | List Docker images      |
| `docker ps`              | List running containers |
| `docker ps -a`           | List all containers     |
| `docker build -t name .` | Build image             |
| `docker run image`       | Run container           |
| `docker stop container`  | Stop container          |
| `docker rm container`    | Remove container        |



##  Portainer (Docker GUI)

To manage Docker using a web interface:

```bash
docker volume create portainer_data

docker run -d -p 9000:9000 \
  --name portainer \
  --restart=always \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v portainer_data:/data \
  portainer/portainer-ce
```

Access Portainer at:

```
http://localhost:9000
```






## Next Steps

* Docker Compose
* Multi-container applications
* CI/CD pipelines with Docker
* Kubernetes basics







