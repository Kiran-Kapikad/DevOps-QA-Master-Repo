# Dockerfile Explained

A **Dockerfile** is a text file that contains instructions to build a Docker image. It automates the image creation process by defining the environment and how the application runs inside a container.

---

## 🔹 Basic Syntax of a Dockerfile

```dockerfile
# Start from a base image
FROM python:3.9-slim

# Set the working directory
WORKDIR /app

# Copy dependency file and install
COPY requirements.txt .
RUN pip install -r requirements.txt

# Copy source code
COPY . .

# Run the application
CMD ["python", "app.py"]
```

---

## 🔹 Common Dockerfile Instructions

| Instruction | Description |
|-------------|-------------|
| `FROM` | Specifies the base image to use |
| `WORKDIR` | Sets the working directory inside the container |
| `COPY` | Copies files from host to container |
| `RUN` | Executes a command during build |
| `CMD` | Sets default command to run when container starts |
| `EXPOSE` | Informs Docker which port the container listens on |
| `ENV` | Sets environment variables |
| `ENTRYPOINT` | Configures a container to run as an executable |

---

## 🔹 Example with Explanation

```dockerfile
FROM node:18-alpine            # Use Node.js base image
WORKDIR /usr/src/app           # Set container working directory
COPY package*.json ./          # Copy dependency files
RUN npm install                # Install dependencies
COPY . .                       # Copy all source code
EXPOSE 3000                    # Inform Docker the app uses port 3000
CMD ["node", "server.js"]      # Command to run the app
```

---

## 🔹 Docker Ignore File

To avoid sending unnecessary files while building an image, use `.dockerignore` (like `.gitignore`):

```bash
node_modules
*.log
Dockerfile
.dockerignore
.git
```

---

## 🔹 Tips for Writing Dockerfiles

- Use small base images (e.g., `alpine`) for efficiency
- Combine commands using `&&` to reduce image layers
- Keep layers minimal for better caching
- Avoid copying sensitive files

---

## ✅ Summary

A Dockerfile is the heart of container image creation. Understanding how to build and structure it efficiently leads to better performance, security, and reproducibility in Docker-based workflows.

