# Introduction to Kubernetes (K8s)

Kubernetes, also known as **K8s**, is an open-source container orchestration platform for automating deployment, scaling, and management of containerized applications.

---

## 🔹 Why Kubernetes?

Before Kubernetes, deploying containers manually or with basic Docker tools was difficult at scale. Kubernetes solves this by:

* Automating container deployment
* Managing load balancing and traffic distribution
* Enabling rolling updates and rollbacks
* Rescheduling containers if they fail
* Handling storage and secrets

---

## 🔹 Key Features

* **Self-healing:** Auto-restarts, replaces, and reschedules failed containers
* **Scaling:** Automatically scale applications up/down
* **Service Discovery & Load Balancing**
* **Automated Rollouts & Rollbacks**
* **Secret & Config Management**
* **Storage Orchestration**

---

## 🔹 Kubernetes vs Docker

* Docker is a **containerization platform** (runs containers)
* Kubernetes is a **container orchestrator** (manages multiple containers across multiple hosts)
* You can use Docker with Kubernetes (e.g., Docker images managed by Kubernetes)

---

## 🔹 Core Concepts (Just Named Here — Covered Later)

* Pod
* Node
* Cluster
* Deployment
* ReplicaSet
* Service
* Namespace
* ConfigMap & Secret

---

## 🔹 Use Cases in DevOps

* CI/CD automation
* Blue/green deployments
* Canary deployments
* Auto-scaling microservices
* Infrastructure as code (with Helm or YAML)

---

## ✅ Summary

Kubernetes is essential for managing containerized applications at scale. It ensures high availability, fault tolerance, scalability, and repeatability, making it a foundational tool in DevOps and cloud-native architecture.

