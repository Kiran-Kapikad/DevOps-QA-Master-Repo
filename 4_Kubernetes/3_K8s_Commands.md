# Common Kubernetes (kubectl) Commands

This section lists essential `kubectl` commands used for interacting with Kubernetes clusters. These commands cover basic to intermediate usage in real DevOps scenarios.

---

## 🔹 Cluster Information

```bash
kubectl cluster-info              # Show master and service info
kubectl version                   # Display client and server versions
kubectl config view               # Show kubeconfig details
```

---

## 🔹 Working with Nodes

```bash
kubectl get nodes                 # List all nodes
kubectl describe node <node>     # Detailed info about a node
```

---

## 🔹 Working with Pods

```bash
kubectl get pods                  # List all pods in current namespace
kubectl get pods -A               # List all pods across namespaces
kubectl describe pod <pod-name>   # Detailed pod info
kubectl delete pod <pod-name>     # Delete a pod
kubectl logs <pod-name>           # View logs from a pod
kubectl exec -it <pod-name> -- bash  # Access shell inside a pod
```

---

## 🔹 Working with Deployments

```bash
kubectl get deployments           # List deployments
kubectl create -f deployment.yaml # Create deployment from YAML
kubectl apply -f deployment.yaml  # Apply/update deployment
kubectl rollout status deployment/<name>   # Check rollout status
kubectl rollout undo deployment/<name>     # Rollback deployment
kubectl delete deployment <name>           # Delete deployment
```

---

## 🔹 Working with Services

```bash
kubectl get svc                   # List services
kubectl expose deployment <name> --type=NodePort --port=80  # Create service
```

---

## 🔹 Namespaces

```bash
kubectl get ns                    # List namespaces
kubectl create ns <name>          # Create a new namespace
kubectl delete ns <name>          # Delete a namespace
```

---

## 🔹 Useful Debugging

```bash
kubectl get events                # View cluster events
kubectl top pod                   # Show pod resource usage
kubectl describe <resource> <name>  # Inspect any resource
```

---

## ✅ Summary

`kubectl` is your main interface to Kubernetes. Knowing these commands allows you to create, manage, monitor, and debug resources efficiently.

