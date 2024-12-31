
# Kubernetes Deployment Commands

## 1. Create a Deployment  
To create a deployment with a specified container image:  
```bash
kubectl create deployment <deployment-name> --image=<image-name>
```
For example, to create a deployment named `nginx-deployment` using the `nginx` image:  
```bash
kubectl create deployment nginx-deployment --image=nginx
```

## 2. Scale a Deployment  
To scale a deployment to a specific number of replicas:  
```bash
kubectl scale deployment <deployment-name> --replicas=<number-of-replicas>
```
For example, to scale `nginx-deployment` to 3 replicas:  
```bash
kubectl scale deployment nginx-deployment --replicas=3
```

## 3. Expose a Deployment as a Service  
To expose a deployment as a service to allow access to the Pods:  
```bash
kubectl expose deployment <deployment-name> --type=<service-type> --port=<port> --target-port=<target-port>
```
For example, to expose `nginx-deployment` as a `ClusterIP` service on port 80:  
```bash
kubectl expose deployment nginx-deployment --type=ClusterIP --port=80 --target-port=80
```

## 4. Get Deployment Information  
To view information about a specific deployment:  
```bash
kubectl describe deployment <deployment-name>
```
For example, to describe `nginx-deployment`:  
```bash
kubectl describe deployment nginx-deployment
```

## 5. Update a Deployment  
To update the image of a deployment (e.g., change the image from `nginx:latest` to `nginx:1.21`):  
```bash
kubectl set image deployment/<deployment-name> <container-name>=<new-image>
```
For example, to update the image for the `nginx` container in the `nginx-deployment`:  
```bash
kubectl set image deployment/nginx-deployment nginx=nginx:1.21
```

## 6. Roll Back a Deployment  
To roll back to a previous deployment revision:  
```bash
kubectl rollout undo deployment/<deployment-name>
```
For example, to roll back `nginx-deployment` to the previous revision:  
```bash
kubectl rollout undo deployment/nginx-deployment
```

## 7. Get Deployments  
To list all deployments in the current namespace:  
```bash
kubectl get deployments
```

To list deployments in a specific namespace:  
```bash
kubectl get deployments -n <namespace-name>
```

## 8. Delete a Deployment  
To delete a deployment:  
```bash
kubectl delete deployment <deployment-name>
```
For example, to delete `nginx-deployment`:  
```bash
kubectl delete deployment nginx-deployment
```
