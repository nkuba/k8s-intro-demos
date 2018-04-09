# Kubernetes Demo 1: Pod, Deployment, Service​ - use kubectl CLI

Create a deployment of `hello-web` application and expose it as a `NodePort` service.
Perform operations with `kubectl` CLI.

## Steps

1. Validate list of Services, Deployments and Pods are empty.
```bash
kubectl get services
kubectl get deployments
kubectl get pods
```

2. Create a deployment
```bash
kubectl create deployment --image=nkuba/hello-web:1.0 hello-web
```

3. Validate Deployment and Pod were created
```bash
kubectl get deployments -o wide
kubectl get pods -o wide
```

4. Expose the deployment
```bash
kubectl expose deployment hello-web --type=NodePort --port=3080
```

5. Check on which port the deployment was exposed
```bash
kubectl get service hello-web
```

5. Open Web Browser and validate that application is working
`http://<NODE_IP>:<SRV_PORT>/`

6. Clean Up
```bash
kubectl delete service hello-web
kubectl delete deployment hello-web
```