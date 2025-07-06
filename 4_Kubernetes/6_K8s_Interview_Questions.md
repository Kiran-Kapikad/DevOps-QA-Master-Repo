# Kubernetes Interview Questions and Answers

This document includes commonly asked Kubernetes interview questions and concise answers to help you prepare for real-world DevOps, SRE, or Cloud roles.

---

## ❓ General Kubernetes

### 1. What is Kubernetes?
Kubernetes is an open-source container orchestration platform that automates deployment, scaling, and management of containerized applications.

### 2. What are the main components of Kubernetes architecture?
- Control Plane: API Server, Scheduler, Controller Manager, etcd
- Node Components: kubelet, kube-proxy, container runtime

### 3. What is a Pod?
A Pod is the smallest deployable unit in Kubernetes, which can contain one or more containers that share storage/network and run in the same context.

### 4. What is the difference between ReplicaSet and Deployment?
- **ReplicaSet** ensures a specified number of pod replicas.
- **Deployment** manages ReplicaSets and provides rolling updates and rollbacks.

### 5. How does Kubernetes perform service discovery?
It uses DNS and environment variables via the kube-dns or CoreDNS service. Each Service is assigned a stable IP and DNS name.

---

## 🛠️ Practical Concepts

### 6. What is a ConfigMap and how is it used?
A ConfigMap allows you to decouple configuration data from application images. It can be injected into Pods as environment variables or mounted as files.

### 7. What is a Secret and how is it different from ConfigMap?
Secrets store sensitive data like passwords or tokens in base64-encoded form. Unlike ConfigMaps, access to Secrets can be restricted and audited.

### 8. How do you perform a rolling update?
Update the Deployment with a new image version or spec. Kubernetes automatically replaces pods in a controlled manner.

```bash
kubectl set image deployment/myapp myapp=myapp:v2
```

### 9. How do you scale a Deployment?
```bash
kubectl scale deployment myapp --replicas=5
```

### 10. How do you troubleshoot a failed pod?
- `kubectl describe pod <name>`
- `kubectl logs <pod-name>`
- Check events, status, and container errors.

---

## 🚀 Advanced Topics

### 11. What is a StatefulSet?
Used to manage stateful applications. Provides stable network IDs, persistent volumes, and ordered scaling.

### 12. What is a DaemonSet?
Ensures that all (or some) nodes run a copy of a pod. Commonly used for log collection or monitoring agents.

### 13. What is the difference between NodePort, ClusterIP, and LoadBalancer?
- **ClusterIP**: Internal access only.
- **NodePort**: Exposes service on a port across all nodes.
- **LoadBalancer**: Exposes externally via cloud provider’s load balancer.

### 14. What is a Namespace?
A logical cluster partition used to isolate resources between teams, projects, or environments.

---

## ✅ Final Tip

Always back your answers with:
- Real scenarios (e.g., scaling, logging, debugging)
- Hands-on command familiarity
- YAML snippet understanding

This sets you apart as a job-ready candidate.

