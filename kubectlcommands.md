
# Kubernetes Commands for Pod and Cluster Management

## 1. To Deploy a Pod  
Deploy a simple Pod using the `kubectl run` command:  
```bash
kubectl run hello-minikube
```

## 2. To Get Cluster Info  
To get general information about the cluster:  
```bash
kubectl cluster-info
```

## 3. To List All the Nodes in the Cluster  
List all nodes in the cluster:  
```bash
kubectl get nodes
```

## 4. To Define an Image for a Pod  
Run a Pod with a specified image:  
```bash
kubectl run nginx --image nginx
```
(This pulls the image from Docker Hub.)

## 5. To Get Information About a Pod  
Describe a specific Pod to get detailed information:  
```bash
kubectl describe pod webapp
```

## 6. To Delete a Pod  
Delete a specific Pod:  
```bash
kubectl delete pod webapp
```

## 7. To Create a Pod Manifest File  
Use the `--dry-run=client -o yaml` option to create a manifest file for a Pod:  
```bash
kubectl run redis --image=redis123 --dry-run=client -o yaml > redis-definition.yaml
```

## 8. To Create a Resource from a Manifest File  
Use `kubectl create -f` to create the resource from the manifest file:  
```bash
kubectl create -f redis-definition.yaml
```

## 9. To Verify Resource Creation  
To verify if the Pod is created, run:  
```bash
kubectl get pods
```

## 10. To Edit and Update a Pod  
Use the `kubectl edit` command to update the Pod image:  
```bash
kubectl edit pod redis
```
Alternatively, if using a manifest file, update the image directly in the YAML file (using `vi` or `nano`) and run:  
```bash
kubectl apply -f redis-definition.yaml
```

## 11. To Describe a Pod  
To see detailed information about a specific Pod:  
```bash
kubectl describe pod newpods-<id>
```

Or, to view the Pod placement on a node:  
```bash
kubectl get pods -o wide
```

## 12. To Export a Pod Definition to a YAML File  
Export the YAML definition of a Pod:  
```bash
kubectl get pod <pod-name> -o yaml > pod-definition.yaml
```

## 13. To Get All the Namespaces  
List all Pods in the `kube-system` namespace:  
```bash
kubectl get pods --namespace=kube-system
```

## 14. To Count the Number of Namespaces  
Run the command to get the exact number of namespaces:  
```bash
kubectl get ns --no-headers | wc -l
```

## 15. To Set a Namespace for a Context  
Set the default namespace for the current context:  
```bash
kubectl config set-context $(kubectl config current-context) --namespace=dev
```

## 16. To Get Pods in a Specific Namespace  
Get Pods from the `research` namespace:  
```bash
kubectl -n research get pods
```

## 17. To Create a Pod in a Specific Namespace  
Create a Pod in the `finance` namespace:  
```bash
kubectl run redis --image=redis -n finance
```

## 18. To Find a Specific Pod  
Search for a specific Pod across all namespaces:  
```bash
kubectl get pods --all-namespaces | grep blue
```
Or, to get Pods across all namespaces:  
```bash
kubectl get pods -A
```

## 19. To Find a Specific Service in a Namespace  
Get the service from the `marketing` namespace:  
```bash
kubectl get svc -n=marketing
```

## 20. To Create pod using image 

```bash 
kubectl run nginx --image=nginx
```

## 21.  create a new pod with your changes using the temporary file
```bash
kubectl create -f /tmp/kubectl-edit-ccvrq.yaml
```
