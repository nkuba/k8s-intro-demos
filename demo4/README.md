# Kubernetes Demo 4 - Multiple Pods

Create three deployments: Web, Rest and DataBase.
Expose the service and check connections between pods.

## Steps
1. Validate list of Services, Deployments and Pods are empty.
```bash
kubectl get services
kubectl get deployments
kubectl get pods
```

2. Create Web deployment and service from YAML file
```bash
kubectl apply -f web-dep-srv.yaml
```

3. Validate Deployment, Pod and Service were created
```bash
kubectl get deployments -o wide
kubectl get pods -o wide
kubectl get services
```

4. Open exposed web page in a browser `http://<NODE_IP>:30080/`

5. Create Rest deployment from YAML file
```bash
kubectl apply -f rest-dep.yaml
```

6. Validate Deployment and Pod were created
```bash
kubectl get deployments -o wide
kubectl get pods -o wide
```

7. Open exposed web page in a browser `http://<NODE_IP>:30080/` - Rest Data are not pupulated

8. Expose Rest deployment from YAML file
```bash
kubectl apply -f rest-srv.yaml
```

9. Open exposed web page in a browser `http://<NODE_IP>:30080/` - Rest Data are pupulated

10. Create DB deployment from YAML file
```bash
kubectl apply -f db-dep.yaml
```

11. Open exposed web page in a browser `http://<NODE_IP>:30080/` - DB is not connected

12. Validate Deployment and Pod were created
```bash
kubectl get services
```

13. Expose DB deployment from YAML file
```bash
kubectl apply -f db-srv.yaml
```

14. Open exposed web page in a browser `http://<NODE_IP>:30080/` - DB is connected

15. Clean Up
```bash
kubectl delete -f .
```