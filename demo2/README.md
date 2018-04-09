# Demo 2: Scaling and updates​ - YAML manifests

Create deployment of `hello-web` application and expose it as a `NodePort` service.
Use YAML manifests to create resources.
Update container image version for the application and scale it.

## Steps

1. Validate list of Services, Deployments and Pods are empty.
```bash
kubectl get services
kubectl get deployments
kubectl get pods
```

2. Create a deployment
```bash
kubectl apply -f deployment-web.yaml
```

3. Validate Deployment and Pod were created
```bash
kubectl get deployments -o wide
kubectl get pods -o wide
```

4. Create a service
```bash
kubectl apply -f service-web.yaml
```

5. Scale the deployemnt to `5` replicas
```bash
kubectl scale deployment hello-web --replicas=5
```

6. Validate Deployment and Pods were created
```bash
kubectl get deployments -o wide
kubectl get pods -o wide
```

7. Check if `Hostname` returned by the service changes in requests
```bash
curl http://<NODE_IP>:<SRV_PORT>/
```

8. Update image version to `2.2`
* Start watch commands in two terminals
```bash
terminal-1:$ kubectl get deployment --watch
terminal-2:$ kubectl get pods --watch
```
* Update to **invalid** image version
```bash
kubectl set image deployment/hello-web hello-web=nkuba/hello-web:2.0
```
* Update to **valid** image version
```bash
kubectl set image deployment/hello-web hello-web=nkuba/hello-web:2.2
```
9. Clean up
```bash
kubectl delete -f .
```