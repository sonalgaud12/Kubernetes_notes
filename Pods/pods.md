# Kubernetes Pods  

Pods are the smallest deployable units in Kubernetes and run inside nodes.  

## Key Features of Pods  

- A **node** can have multiple Pods.  
- To deploy more Pods, new nodes can be created.  
- Pods have a **one-to-one relationship** with containers, but they are not restricted to a single container.  
  - Additional **helper containers** can be included for tasks like managing user data.  
- Pods within the same node can share:  
  - **Storage**  
  - **Information**  
- Pods in the same node are part of the same **network namespace**, allowing them to communicate easily.  



# Kubernetes Pod Management Commands

## 1. View Pods  
- List all Pods in the default namespace:  
  ```bash
  kubectl get pods
  ```
- List Pods in a specific namespace:  
  ```bash
  kubectl get pods -n <namespace>
  ```
- View detailed information about a Pod:  
  ```bash
  kubectl describe pod <pod-name>
  ```

## 2. Create a Pod  
- Create a Pod using a YAML file:  
  ```bash
  kubectl apply -f pod-definition.yml
  ```

## 3. Delete a Pod  
- Delete a specific Pod:  
  ```bash
  kubectl delete pod <pod-name>
  ```
- Delete all Pods in a namespace:  
  ```bash
  kubectl delete pods --all -n <namespace>
  ```

## 4. Check Logs  
- View logs for a Pod:  
  ```bash
  kubectl logs <pod-name>
  ```
- View logs for a specific container in a Pod:  
  ```bash
  kubectl logs <pod-name> -c <container-name>
  ```

## 5. Execute Commands in a Pod  
- Access the shell of a Pod’s container:  
  ```bash
  kubectl exec -it <pod-name> -- /bin/bash
  ```
- Run a command inside a Pod:  
  ```bash
  kubectl exec <pod-name> -- <command>
  ```

## 6. Debugging Pods  
- Check events related to a Pod:  
  ```bash
  kubectl describe pod <pod-name>
  ```
- Check the Pod status:  
  ```bash
  kubectl get pods <pod-name> -o wide
  ```

## 7. Monitor Pods  
- Watch changes in Pod states:  
  ```bash
  kubectl get pods -w
  ```
