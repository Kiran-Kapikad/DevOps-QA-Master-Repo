# Dockerized Flask App

This is a simple Flask application containerized using Docker.

---

## 🔹 Project Structure

```
.
├── app.py
├── requirements.txt
├── Dockerfile
├── .dockerignore
└── README.md
```

---

## 🔹 How to Run

### 1. Build the Docker Image
```bash
docker build -t flask-docker-app .
```

### 2. Run the Container
```bash
docker run -d -p 5000:5000 flask-docker-app
```

### 3. Access the App
Open your browser and visit:
```
http://localhost:5000
```

You should see:
```
Hello from Dockerized Flask app!
```

---

## 🔹 Files Explained

- `app.py`: A simple Flask application
- `requirements.txt`: Python dependencies (Flask)
- `Dockerfile`: Instructions to build the Docker image
- `.dockerignore`: Ignore unnecessary files while building image

---

## ✅ Summary

This example shows how to build and run a basic Flask app in a Docker container. It’s a foundational project for DevOps portfolios.

