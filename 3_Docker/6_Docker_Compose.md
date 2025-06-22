# Docker Compose

Docker Compose is a tool for defining and running multi-container Docker applications. With Compose, you define services, networks, and volumes in a single YAML file and manage them as a group.

---

## 🔹 Why Use Docker Compose?

* Manage multi-container applications easily
* Simplify development and testing workflows
* Share configuration across teams
* Reproducible environments

---

## 🔹 Installing Docker Compose

Most modern Docker installations include Docker Compose.
Check version:

```bash
docker-compose --version
```

If not installed, refer to: [https://docs.docker.com/compose/install/](https://docs.docker.com/compose/install/)

---

## 🔹 Basic Structure of docker-compose.yml

```yaml
version: '3'
services:
  web:
    build: .
    ports:
      - "5000:5000"
  redis:
    image: "redis:alpine"
```

---

## 🔹 Common Commands

```bash
docker-compose up           # Build, (re)create, start containers
docker-compose up -d        # Run in detached mode
docker-compose down         # Stop and remove containers, networks, volumes
docker-compose ps           # List containers
docker-compose logs         # View logs
docker-compose build        # Rebuild services
```

---

## 🔹 Environment Variables with Compose

You can use a `.env` file to pass variables into your Compose file:

```bash
# .env file
APP_PORT=5000
```

Use in YAML:

```yaml
ports:
  - "${APP_PORT}:5000"
```

---

## 🔹 Example: Flask App + Redis

```yaml
version: '3'
services:
  web:
    build: .
    ports:
      - "5000:5000"
    depends_on:
      - redis
  redis:
    image: redis:alpine
```

---

## ✅ Summary

Docker Compose simplifies the process of managing multi-container setups. It’s an essential tool for defining infrastructure as code and orchestrating services for local development and testing.

