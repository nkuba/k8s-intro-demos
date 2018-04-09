# Kubernetes Demo 0: Minikube

Install and start `minikube` cluster.

## Steps

1. Navigate to http://kubernetes.io, search documentation for `minikube install` and go to the `Install Minikube` page

2. Walk through steps listed on the page
* Install Hypervisor
* Install `kubectl`
* Configure `kubectl` autocompletion
* Install `minikube`

3. Start and explore `minikube` cluster with following commands
```bash
minikube start
minikube status
kubectl cluster-info
kubectl get nodes
minikube dashboard
minikube stop
```