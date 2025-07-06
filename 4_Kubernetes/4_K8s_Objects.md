# All-in-One Kubernetes Objects Guide

This document provides a complete understanding of Kubernetes objects, including single and multi-container Pods, multi-Pod deployments, multilevel relationships, Services, ConfigMaps, and Secrets — all with real-world YAML examples.

---

## 🔹 Multilevel Kubernetes Architecture

```
Deployment
   └── ReplicaSet
         └── Pod(s)
               └── Container(s)
```

- **Deployment** manages updates and ReplicaSets.
- **ReplicaSet** ensures the correct number of Pods.
- **Pods** host one or more containers.
- **Containers** run actual application processes.

---

## 🔹 1. Single-Container Pod

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: single-pod
spec:
  containers:
    - name: nginx
      image: nginx
```

---

## 🔹 2. Multi-Container Pod (Sidecar Pattern)

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: multi-container-pod
spec:
  containers:
    - name: main-app
      image: myapp:latest
    - name: log-watcher
      image: busybox
      command: ["sh", "-c", "tail -f /var/log/app.log"]
```

---

## 🔹 3. ReplicaSet

```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: nginx-rs
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
        - name: nginx
          image: nginx
```

---

## 🔹 4. Deployment (Multi-Pod Example)

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
        - name: nginx
          image: nginx:1.25
```

---

## 🔹 5. Real-World Multi-Pod Application Layout

```
Frontend Deployment (2 Pods)
   └── Service: frontend

Backend Deployment (3 Pods)
   └── Service: backend

Database Deployment (1 Pod)
   └── Service: database
```

All communicate over Kubernetes DNS-based networking.

---

## 🔹 6. Service

### ClusterIP (Default)
```yaml
apiVersion: v1
kind: Service
metadata:
  name: nginx-service
spec:
  type: ClusterIP
  selector:
    app: nginx
  ports:
    - port: 80
      targetPort: 80
```

### NodePort
```yaml
apiVersion: v1
kind: Service
metadata:
  name: nginx-nodeport
spec:
  type: NodePort
  selector:
    app: nginx
  ports:
    - port: 80
      targetPort: 80
      nodePort: 30080
```

### LoadBalancer (Cloud environments)
```yaml
apiVersion: v1
kind: Service
metadata:
  name: nginx-lb
spec:
  type: LoadBalancer
  selector:
    app: nginx
  ports:
    - port: 80
      targetPort: 80
```

---

## 🔹 7. ConfigMap

Inject configuration into Pods.

### ConfigMap Definition
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: app-config
data:
  APP_ENV: dev
  DEBUG: "true"
```

### Mount ConfigMap in Pod
```yaml
spec:
  containers:
    - name: myapp
      image: myapp:latest
      envFrom:
        - configMapRef:
            name: app-config
```

---

## 🔹 8. Secret

Securely inject sensitive data into Pods.

### Secret Definition
```yaml
apiVersion: v1
kind: Secret
metadata:
  name: app-secret
type: Opaque
data:
  DB_PASSWORD: cGFzc3dvcmQ=   # base64 for 'password'
```

### Use Secret in Pod
```yaml
spec:
  containers:
    - name: myapp
      image: myapp:latest
      env:
        - name: DB_PASSWORD
          valueFrom:
            secretKeyRef:
              name: app-secret
              key: DB_PASSWORD
```

---

## ✅ Summary Table

| Object       | Purpose                                      |
|--------------|----------------------------------------------|
| Pod          | Smallest deployable unit                     |
| ReplicaSet   | Maintains desired pod count                  |
| Deployment   | Manages rolling updates and rollbacks        |
| Service      | Exposes pods internally or externally        |
| ConfigMap    | Injects environment configs into pods        |
| Secret       | Injects sensitive data securely              |
| Multi-Pod    | Scales application across multiple services  |
| Sidecar Pod  | Supports primary containers (e.g., logging)  |

---

## 🎯 Use Case Example

**Scenario**: You deploy a Python web app (Flask) with:
- A Redis backend
- A logging sidecar
- Configs and secrets mounted via ConfigMap and Secret
- Internal communication using Services

This demonstrates:
✅ Multi-pod
✅ Multi-container
✅ Secure secrets
✅ Real DevOps-ready app layout

