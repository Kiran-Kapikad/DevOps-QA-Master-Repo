# Common Docker Commands

This section covers the most commonly used Docker CLI commands with explanations and examples. These commands help manage images, containers, volumes, and more.

---

## 🔹 Docker Version & Info
```bash
docker --version        # Check installed Docker version
docker info             # Display system-wide Docker information
```

## 🔹 Working with Images
```bash
docker pull <image_name>                # Download image from Docker Hub
docker images                           # List all local images
docker rmi <image_id_or_name>           # Remove a Docker image
docker build -t <tag_name> .            # Build image from Dockerfile
```

## 🔹 Working with Containers
```bash
docker ps                               # List running containers
docker ps -a                            # List all containers (including stopped)
docker run -d -p 8080:80 <image>        # Run container in detached mode and map ports
docker exec -it <container_id> bash     # Access a running container’s shell
docker stop <container_id>              # Stop a running container
docker start <container_id>             # Start a stopped container
docker restart <container_id>           # Restart a container
docker rm <container_id>                # Remove a stopped container
```

## 🔹 Container Logs & Status
```bash
docker logs <container_id>              # Show logs of a container
docker inspect <container_id>           # Detailed container info
docker stats                            # Show live resource usage stats
```

## 🔹 Volumes & Storage
```bash
docker volume create <volume_name>      # Create a new volume
docker volume ls                        # List all volumes
docker run -v <volume_name>:/data ...   # Mount volume into container
```

## 🔹 Docker Networks
```bash
docker network ls                       # List all networks
docker network create <network_name>    # Create a user-defined bridge network
docker network inspect <network_name>   # View network details
```

## 🔹 System Cleanup
```bash
docker system prune                     # Remove all stopped containers, unused images & networks
docker image prune                      # Remove unused images
docker container prune                  # Remove stopped containers
```

## 🔹 Helpful Shortcuts
```bash
docker run --rm <image>                 # Remove container after it exits
docker exec -it $(docker ps -q) bash    # Access shell of the latest running container
```

---

## 📝 Tips
- Use `--help` with any command for detailed usage, e.g., `docker run --help`
- Use tags like `:latest`, `:alpine`, or specific versions while pulling images
- Combine with shell scripting to automate tasks

---

## ✅ Summary
Mastering these Docker commands is essential for daily development, debugging, and deployment tasks using containers. Practice them often to build fluency.

