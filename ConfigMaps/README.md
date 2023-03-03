# ConfigMaps

When you have alot of pod definition files, it may become difficult to manage the environment data stored within vairous files. 

We can take this information out of the pod definition file and manage it centrally using ConfigMaps.

There are 2 phases involved:

1. Create the ConfigMap(s)
2. Inject them into the pod. 

## Imperative
`kubectl create configmap <config-name> --from-literal=<key>=<value>`

`--from-literal` - specifies the key value pairs in the command iteslf. 


### Example: 

`kubectl create configmap my-app-config --from-literal=env=prod`

May get complicated if you have too many options. 
## Declarative

```
apiVersion: v1
kind: ConfigMap
metadata:
  name: app-config
data:
  ENV: developement
  APP_COLOR: blue
```

## Commands

| Description | Command |
| --- | ----------- |
| List all ConfigMaps | `kubectl get configmaps`|

