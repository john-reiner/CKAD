# Resource Requirements

## Example

```
apiVersion: v1
kind: Pod
metadata:
  name: example-rr
  labels: 
    name: example
spec: 
  containers:
    - name: example-rr-container
      image: simple-webapp-color
      ports:
        - containerPort: 8080
```