# Arguments

## Commands 

| Description | Command |
| --- | ----------- |
| Create a deployment | `kubectl apply -f <deployment-file-name>.yaml` |

## Example YAML file

```
apiVersion: v1
kind: Pod
metadata:
  name: <pod-name>
spec:
    containers:
    - name: <container-name>
    image: <container-image>
    args: ["<command>"]
```