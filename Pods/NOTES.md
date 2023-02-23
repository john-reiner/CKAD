# Pods

## Commands 

| Description | Command |
| --- | ----------- |
| List all pods | `kubectl get pods` |
| Create a pod from image | `kubectl run <yourpodname> —image <image-name>` |
| List pod details | `kubectl describe pod <pod-name>` |
| Delete pod | `kubectl delete <yourpodname>` |

## Example YAML file

```
apiVersion: v1
kind: Pod
metadata:
  name: <pod-name>
  labels: 
    <pod-label-key>: <pod-label-value>
spec:
  containers: 
  - image: <container-image>
    name: <container-name>
    
```