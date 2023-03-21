# Security Contexts

List all users with their PID:
`ps aux`

```
apiVersion: v1
kind: Pod
metadata:
  name: web-pod
spec:
  ## Pod Level 
  # SecurityContext:
    # runAsUser: 1000
  containers:
    - name: ubuntu
      image: ubuntu
      command: ["sleep", "3600"]
      ## Container level
      securityContext:
        runAsUser: 1000
        ## Only supported at the container level
        capabilities:
          add: ["MAC_ADMIN"]
```

