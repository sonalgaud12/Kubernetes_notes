## 1. Count of npods in namespace
 
  ```bash
 kubectl get pods --namespace=research
  ```

## 2. Create pod in a namespace 
``` 
kubectl run redis --image=redis -n finance
```