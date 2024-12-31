### YAML in Kubernetes  

Kubernetes uses YAML files as input for defining various resources such as Pods, Replicas, Deployments, Services, etc.  

#### Structure  

```yaml
apiVersion: v1  # Version of the API  

kind: Pod       # Type of object being created  

metadata:       # Metadata about the object (in the form of a dictionary)  
  name: myapp-pod  
  labels:  
    app: myapp  
    type: front-end  

spec:           # Specification of the resource (in the form of a dictionary)  
  containers:   # List/Array of containers  
    - name: nginx-container  
      image: nginx  
