# Node Selectors

```
apiVersion: v1
kind: pod
metadata: 
  name: myapp-pod
spec:
  containers: 
  - image: nginx
    name: myapp-container
  nodeSelector:
    labelKey: labelValue
```