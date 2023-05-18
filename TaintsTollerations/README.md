# Taints and Tolerations

taint is on the node 
toleration is on the pod 

taint 'repels' the pod from the node 
toleration negates the taint/repel for a pod

## example

`kubectl taint nodes node1`

```
apiVersion: 
kind: Pod 
metadata:
  name: tolerations-example
spec: 
  containers: 
  - name: nginx-container
    image: nginx

  tolerations:
    - key: "app"
      operator: "Equal"
      value: "blue
      effect: "NoSchedule"
```

`kubectl taint nodes node1 app=blue:NoSchedule`