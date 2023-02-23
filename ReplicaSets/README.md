# ReplicaSets

## Commands 

| Description | Command |
| --- | ----------- |
| List all replicasets | `kubectl get replicasets` |
| Create a new replicaset from file | `kubectl create -f <replicaset-file-name>.yaml` |
| Scale a replicaset | `kubectl scale --replicas=<desired-number> replicaset <replicaset-name>` |
| List replicaset details | `kubectl describe replicaset <replicaset-name>` |
| Delete replicaset | `kubectl delete <replicaset-name>` |

## Example YAML file

```
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: <replicaset-name>
  labels: 
    <replicaset-label-key>: <replicaset-label-value>
spec:
  replicas: <amount-desired>
  selector: 
    matchLabels:
      <matchlabel-key>: <matchlabel-value>
  template:
    metadata:
      labels:
        <pod-label-key>: <pod-label-value>
    spec:
      containers:
        - image: <container-image>
          name: <container-name>
    
```