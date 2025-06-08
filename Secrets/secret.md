## To create secrets

```bash
kubectl create secret generic

(then add the key-value pairs)
```


# Kubernetes Secrets: Complete Guide

##  What is a Secret?

A **Secret** in Kubernetes is used to store sensitive information such as:
- Passwords
- Tokens
- SSH keys
- API keys

Unlike ConfigMaps, Secrets encode the data in **base64** (not encrypted).

---

##  Types of Secrets

| Type                          | Description                                      |
|-------------------------------|--------------------------------------------------|
| `Opaque`                     | Default type for arbitrary key-value pairs       |
| `kubernetes.io/dockerconfigjson` | Docker registry credentials                   |
| `kubernetes.io/tls`           | TLS certs (`tls.crt` and `tls.key`)              |
| `bootstrap.kubernetes.io/token` | Used by kubelet for bootstrap authentication |

---

#  `kubectl` Commands for Kubernetes Secrets

##  Create Secrets

### From Literal Key-Value Pairs
```bash
kubectl create secret generic my-secret \
  --from-literal=username=admin \
  --from-literal=password=myPassword123
```


### View Secret with Encoded Data
```
kubectl get secret my-secret -o yaml
```

### Decode a Secret Value

```
kubectl get secret my-secret \
  -o jsonpath="{.data.username}" | base64 --decode
```

### Recreate a Secret

```
kubectl delete secret my-secret
kubectl create secret generic my-secret --from-literal=username=newuser
```

### Patch a Secret (Base64 Required)

```kubectl patch secret my-secret -p='{"data":{"username":"bmV3dXNlcg=="}}'
```

### Delete a Secret
```
kubectl delete secret my-secret
```
### Use Secret in a Pod (Test Command)
```
kubectl apply -f secret-pod.yaml
kubectl exec -it <pod-name> -- env | grep USERNAME
```


