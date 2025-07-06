# Kubernetes Architecture

Kubernetes follows a **master-worker** architecture. It consists of a control plane and a set of worker nodes.

---

## 🔹 High-Level View

```
+-------------------------+
|     Control Plane       |
+-------------------------+
|  API Server             |
|  Scheduler              |
|  Controller Manager     |
|  etcd (Key-Value Store) |
+-------------------------+
         ||
         ||
+-------------------------+
|      Worker Nodes        |
+-------------------------+
|  Kubelet                |
|  Kube Proxy             |
|  Container Runtime      |
+-------------------------+
```

---

## 🔹 Components of Control Plane

### 1. **API Server**

* Central point of communication with Kubernetes
* All commands go through the API server

### 2. **etcd**

* Distributed key-value store
* Stores cluster data, configuration, state, secrets

### 3. **Controller Manager**

* Controls the desired state of the system
* Handles node, replication, and endpoint controllers

### 4. **Scheduler**

* Assigns new pods to available nodes based on resource availability and policies

---

## 🔹 Components of Worker Node

### 1. **Kubelet**

* Agent running on each node
* Communicates with API server
* Ensures containers are running as expected

### 2. **Kube Proxy**

* Maintains network rules and service discovery
* Manages IP translation and load-balancing across pods

### 3. **Container Runtime**

* Runs containers (e.g., containerd, Docker, CRI-O)

---

## 🔹 Add-Ons (Optional But Common)

* **CoreDNS** – For service discovery (DNS-based)
* **Dashboard** – Web-based UI for managing clusters
* **Metrics Server** – Resource usage (CPU, memory) reporting

---

## ✅ Summary

Kubernetes architecture separates responsibilities between the control plane and worker nodes. This decoupling enables powerful orchestration, scalability, and fault tolerance. Understanding each component helps in debugging and managing real-world clusters.

