# Deployments

## Commands 

| Description | Command |
| --- | ----------- |
| List all Namespaces | `kubectl get namespaces` |
| Get all pods within a namespace | `kubectl get pods -n <namespace>` |
| Get all pods within all namespaces | `kubectl get pods --all-namespaces (-A)` |
| Scale a deployment | `kubectl scale --replicas=<desired-number> deployment <deployment-name>` |
| List deployment details | `kubectl describe deployments` |
| Delete deployment | `kubectl delete <deployment-name>` |

## Example YAML file

```

    
```