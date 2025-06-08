#  Kubernetes Multi-Container Pod

##  What is a Multi-Container Pod?

A Kubernetes **Pod can have multiple containers** that:
- Share the same **network namespace** (i.e., same IP and port space).
- Can communicate via `localhost`.
- Can **share volumes** for data exchange.

Common use cases:
- Sidecar containers (e.g., log forwarder, reverse proxy)
- Init containers
- Helper containers

---

##  Component Explanation: Multi-Container Pod

| Part              | Description                                                  |
|-------------------|--------------------------------------------------------------|
| `containers`      | Defines multiple containers in the same pod                 |
| `nginx-container` | Serves content from `/usr/share/nginx/html`                 |
| `sidecar-container` | Writes HTML file to shared volume (`/shared`)           |
| `volumeMounts`    | Mounts the same volume at different paths                   |
| `emptyDir`        | A temporary shared volume created per Pod lifecycle         |



### Deploy the Pod

```
kubectl apply -f multi-container-pod.yaml
``` 

### View the Pod

```
kubectl get pods
kubectl describe pod multi-container-pod
```

### Inspect Logs (per container)
```
kubectl logs multi-container-pod -c nginx-container
kubectl logs multi-container-pod -c sidecar-container
```

### Exec into Containers
```
kubectl exec -it multi-container-pod -c nginx-container -- /bin/sh
kubectl exec -it multi-container-pod -c sidecar-container -- /bin/sh
```


