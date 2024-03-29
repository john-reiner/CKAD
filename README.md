# CKAD
## These are my notes for studying for the CKAD Certification.

---

## Imperative Commands
Imperative commands help in getting one time tasks done quickly. You can also generate a definition template easily. 

### flags

`--dry-run` creates a resource `--dry-run=client` Will not create the resource, instead, tells you whether the resource can be created and if your command is right. 

`-o yaml` outputs the resource definintion in YAML format on screen. 

Use the above two in combination to generate a resource definition file quickly, that you can then modify and create resources as required, instead of creating the files from scratch:

`kubectl run nginx --image=nginx --dry-run=client -o yaml`

outputs: 

```
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: nginx
  name: nginx
spec:
  containers:
  - image: nginx
    name: nginx
    resources: {}
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}
```
## Other Examples of Imterpative Commands:

* `kubectl run my-nginx-pod --image=nginx-alpine`
* `kubectl run my-nginx-pod --image=nginx-alpine --labels="tier=frontend,app=my-app"`
* `kubectl create service my-nginx-service clusterip`
* `kubectl expose pod my-nginx-pod --port 8080 --name my-nginx-service`
* `kubectl create deplopyment my-frontend-deployment --image=nginx --replicas=3`
* `kubectl create namespace my-app`
