# Docker Images and Containers

Understanding Docker images and containers is essential for working with containerized applications. This section breaks down their roles, lifecycle, and basic commands.

---

## 🔹 What is a Docker Image?

A **Docker image** is a read-only template that contains the application code, runtime, libraries, environment variables, and configuration files required to run an application.

* It acts like a snapshot or blueprint.
* Built using a Dockerfile.
* Stored in registries like Docker Hub.

### Example:

```bash
docker build -t myapp:latest .
```

---

## 🔹 What is a Docker Container?

A **Docker container** is a runtime instance of a Docker image. It is a lightweight, executable package that runs isolated processes on a shared OS kernel.

* You can create multiple containers from the same image.
* Containers are mutable and can be started, stopped, and removed.

### Example:

```bash
docker run -d -p 5000:5000 myapp:latest
```

---

## 🔹 Image vs Container

| Feature       | Docker Image | Docker Container                |
| ------------- | ------------ | ------------------------------- |
| Type          | Static       | Running instance                |
| Lifecycle     | Built once   | Created, started, stopped       |
| Persistence   | Read-only    | Writable (runtime data)         |
| Creation Tool | Dockerfile   | `docker run` or `docker create` |

---

## 🔹 Container Lifecycle Commands

```bash
# Create & start container
docker run -d --name mycontainer myapp

# List running containers
docker ps

# List all containers (including stopped)
docker ps -a

# Stop a container
docker stop mycontainer

# Start a container
docker start mycontainer

# Remove a container
docker rm mycontainer
```

---

## 🔹 Inspecting Images and Containers

```bash
# List all local images
docker images

# View image history
docker history <image_id>

# Inspect image metadata
docker inspect <image_id>

# Inspect running container details
docker inspect <container_id>
```

---

## ✅ Summary

* **Docker Images** are static blueprints built from Dockerfiles.
* **Containers** are running instances of these images.
* Images are portable and immutable, while containers are isolated, temporary environments where applications run.

Understanding how to work with both is key to mastering Docker and containerization workflows.

