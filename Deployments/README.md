# Deployments

## Commands 

| Description | Command |
| --- | ----------- |
| Create a deployment | `kubectl apply -f <deployment-file-name>.yaml` |
| List all Deployments | `kubectl get deployments` |
| View deployment rollout status | `kubectl rollout status <deployment-name>` |
| Scale a deployment | `kubectl scale --replicas=<desired-number> deployment <deployment-name>` |
| List deployment details | `kubectl describe deployments` |
| Delete deployment | `kubectl delete <deployment-name>` |

## Example YAML file

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: <deployment-name>
  labels:
    <deployment-lable-key>: <deployment-label-value>
spec:
  replicas: 3
  selector:
    matchLabels:
      <label-key>: <label-value>
  template:
    metadata:
      labels:
        <label-key>: <label-value>
    spec:
      containers:
      - name: <container-name>
        image: <container-image>
    
```