# Kubernetes Demo 3 - Multiple containers in one Pod

Create multi container deployment (two containers in one Pod: WebApp and DataBase).
Expose the service and check connection between containers.

## Steps
1. Validate list of Services, Deployments and Pods are empty.
```bash
kubectl get services
kubectl get deployments
kubectl get pods
```

2. Create resources from YAML file
```bash
kubectl apply -f dep-srv-web.yaml
```

3. Validate Deployment, Pod and Service were created
```bash
kubectl get deployments -o wide
kubectl get pods -o wide
kubectl get services
```

4. Validate Pod details
```bash
kubectl describe pod <hello-web-POD-NAME>
```

5. Open exposed web page in a browser `http://<NODE_IP>:30080/` and check DB connection status

6. Clean Up
```bash
kubectl delete -f dep-srv-web.yaml
```