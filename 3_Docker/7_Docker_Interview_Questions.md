# Docker Interview Questions and Answers

Here are commonly asked Docker interview questions with concise answers to help you prepare for DevOps, QA, or cloud-related roles.

---

### 1. **What is Docker?**

Docker is a platform used to develop, ship, and run applications in isolated environments called containers. Containers bundle code, dependencies, and system libraries into a single package for portability and consistency.

---

### 2. **What is the difference between a Docker image and a container?**

* **Image:** Blueprint or read-only template built using a Dockerfile.
* **Container:** Runtime instance of an image, which can be started, stopped, and deleted.

---

### 3. **What are the main components of Docker architecture?**

* Docker Engine
* Docker Daemon
* Docker Client (CLI)
* Docker Images
* Docker Containers
* Docker Hub / Registry

---

### 4. **How do containers differ from virtual machines?**

Containers share the host OS kernel, making them lightweight and faster. VMs have full OS overhead, making them bulkier and slower to boot.

---

### 5. **What is a Dockerfile?**

A text file with instructions to build a Docker image. It contains commands like `FROM`, `COPY`, `RUN`, `CMD`, etc.

---

### 6. **What is Docker Compose and when would you use it?**

Docker Compose is a tool used to define and manage multi-container applications using a YAML file. It simplifies local development and orchestration.

---

### 7. **How do you persist data in Docker containers?**

Using Docker volumes or bind mounts:

```bash
docker run -v myvolume:/data myapp
```

---

### 8. **What are some common Docker commands you use daily?**

```bash
docker build -t app .
docker run -d -p 5000:5000 app
docker ps -a
docker logs <container>
docker exec -it <container> bash
```

---

### 9. **What are Docker networks and why are they important?**

Docker networks enable containers to communicate with each other or external systems. They are important for service discovery, isolation, and security.

---

### 10. **How do you optimize Docker images?**

* Use smaller base images like `alpine`
* Combine `RUN` statements to reduce layers
* Use `.dockerignore`
* Clean up cache after installations

---

## ✅ Tips

* Always understand the scenario behind the question.
* Give real-world examples.
* Practice commands hands-on before interviews.

