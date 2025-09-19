## Kubernetes Cluster Setup & Deployment

This project demonstrates a basic Kubernetes deployment using an Nginx container. The configuration is defined in `pod.yaml` as a Deployment with 2 replicas of Nginx. 

### Prerequisites
- [kubectl](https://kubernetes.io/docs/tasks/tools/) installed
- Access to a Kubernetes cluster (local: [Minikube](https://minikube.sigs.k8s.io/docs/), [Kind](https://kind.sigs.k8s.io/), or cloud provider)

### Steps to Create Cluster and Deploy

1. **Create a Kubernetes cluster using Kind:**
	[Kind](https://kind.sigs.k8s.io/) is a tool for running local Kubernetes clusters using Docker containers.
	Install Kind if you haven't already: Use the kind documentation
	Create a cluster:
	```powershell
	kind create cluster --name my-cluster
	```

2. **Apply the deployment configuration:**
	```powershell
	kubectl apply -f pod.yaml
	```

3. **Check the status of the deployment and pods:**
	```powershell
	kubectl get deployments
	kubectl get pods
	```

4. **Expose the deployment (optional):**
	```powershell
	kubectl expose deployment my-nginx --type=NodePort --port=80
	```
	To access the service, get the port and use Docker's IP:
	```powershell
	kubectl get service my-nginx
	```

5. **View pod logs (optional):**
	```powershell
	kubectl logs <pod-name>
	```

2. **Apply the deployment configuration:**
	```powershell
	kubectl apply -f pod.yaml
	```

3. **Check the status of the deployment and pods:**
	```powershell
	kubectl get deployments
	kubectl get pods
	```

4. **Expose the deployment (optional):**
	```powershell
	kubectl expose deployment my-nginx --type=NodePort --port=80
	minikube service my-nginx
	```

5. **View pod logs (optional):**
	```powershell
	kubectl logs <pod-name>
	```

### Description of `pod.yaml`
The `pod.yaml` file defines a Kubernetes Deployment named `my-nginx` with 2 replicas. Each pod runs the official Nginx image and exposes port 80. The deployment ensures high availability and easy scaling of the Nginx service.

---
# Kubernetes_basic_cluster
This repo understand basic of k8s 

