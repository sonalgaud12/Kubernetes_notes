# Kubernetes Replica  

Replicas help us run multiple instances of a single Pod in a Kubernetes cluster.

## Types of Replica Management  
1. **Replication Controller**  
2. **Replica Set**  

Both serve the same purpose of maintaining the desired number of Pod replicas, but they differ in implementation and features.

---

## Replication Controller  

### Creating a Replication Controller  
To create a replication controller, use the following command:  
```bash
kubectl create -f rc-definition.yml
```




## Listing Replication Controllers
To list all replication controllers:

```bash
kubectl get replicationcontroller
```

### Replica Set

Updating a Replica Set
To replace or update an existing ReplicaSet:

```bash
kubectl replace -f replicaset-definition.yml
```

## Scaling a Replica Set
To scale the number of replicas in a ReplicaSet:

```bash
kubectl scale --replicas=6 -f replicaset-definition.yml
```

## Checking the API Version of a ReplicaSet
To verify the API version used for ReplicaSets:

```bash
kubectl api-resources | grep replicaset
kubectl explain replicaset | grep VERSION
```

## Creating a ReplicaSet
After verifying and correcting the apiVersion in the YAML file, create the ReplicaSet using:

```bash
kubectl create -f /root/replicaset-definition-1.yaml
```
