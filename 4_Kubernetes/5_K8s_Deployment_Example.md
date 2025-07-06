# Kubernetes Deployment Example (End-to-End)

This file provides a real-world, complete example of deploying a web application using Kubernetes objects including Deployment, Service, ConfigMap, and Secret.

---

## 🌐 Application Overview

We will deploy a **Flask web application** backed by Redis.

- Flask app (frontend)
- Redis (backend)
- Exposed via a **Service**
- Configuration via **ConfigMap**
- Password injection via **Secret**

---

## 📁 Directory Structure (for context)

```
k8s-app/
├── app-deployment.yaml
├── redis-deployment.yaml
├── app-service.yaml
├── redis-service.yaml
├── configmap.yaml
├── secret.yaml
```

---

## 🧾 Step 1: Create ConfigMap

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: app-config
data:
  APP_MODE: production
  APP_TIMEOUT: "5000"
```

---

## 🔐 Step 2: Create Secret

```yaml
apiVersion: v1
kind: Secret
metadata:
  name: redis-secret
type: Opaque
data:
  REDIS_PASSWORD: cmVkaXNwYXNz   # base64 of 'redispass'
```

---

## 🚀 Step 3: Redis Deployment

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: redis-deployment
spec:
  replicas: 1
  selector:
    matchLabels:
      app: redis
  template:
    metadata:
      labels:
        app: redis
    spec:
      containers:
        - name: redis
          image: redis
          args: ["--requirepass", "$(REDIS_PASSWORD)"]
          env:
            - name: REDIS_PASSWORD
              valueFrom:
                secretKeyRef:
                  name: redis-secret
                  key: REDIS_PASSWORD
```

---

## 🧠 Step 4: Flask App Deployment

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: flask-app
spec:
  replicas: 2
  selector:
    matchLabels:
      app: flask
  template:
    metadata:
      labels:
        app: flask
    spec:
      containers:
        - name: flask-container
          image: flask-app:latest
          ports:
            - containerPort: 5000
          envFrom:
            - configMapRef:
                name: app-config
```

---

## 📡 Step 5: Services

### Redis Service
```yaml
apiVersion: v1
kind: Service
metadata:
  name: redis-service
spec:
  type: ClusterIP
  selector:
    app: redis
  ports:
    - port: 6379
```

### Flask App Service (NodePort)
```yaml
apiVersion: v1
kind: Service
metadata:
  name: flask-service
spec:
  type: NodePort
  selector:
    app: flask
  ports:
    - port: 5000
      targetPort: 5000
      nodePort: 30001
```

---

## ✅ Apply Everything

```bash
kubectl apply -f configmap.yaml
kubectl apply -f secret.yaml
kubectl apply -f redis-deployment.yaml
kubectl apply -f app-deployment.yaml
kubectl apply -f redis-service.yaml
kubectl apply -f app-service.yaml
```

---

## 🧪 Test the App

Visit:
```
http://<NodeIP>:30001
```

Make sure the Flask app is communicating with Redis using the injected password and environment configs.

---

## 🎯 Summary

This example demonstrates:
- Deployments with environment variables
- Secure secret injection
- ClusterIP and NodePort Services
- Scalable, production-like layout

