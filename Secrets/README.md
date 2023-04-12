# Secrets

Like a configMap, secrets are used to store sensitive information. Secrets use the same 2 step process for implementation as a config map. Must specify data in an encoded format.

## Imperative

`kubectl create secret generic <secret-name> --from-literal=<key>=<value>`

`kubectl create secret generic app-secret --from-literal=API_KEY=123456789ten`
`kubectl create secret generic app-secret --from-literal=API_KEY=123456789ten --from-literal=KEY=Value`

## Declarative

```
apiVersion: v1
kind: Secret
metadata:
  name: app-secret
data:
  DB_HOST: bXlzcWw=
  DB_USER: cm9vdA==
  DB_Password: cGFzc3dyZA==
```

## Encode Secrets

`echo -n '<string to encode>' | base64 `
`echo -n 'root' | base64 `

## Commands

| Description | Command |
| --- | ----------- |
| View all Secrets | `kubectl get secrets`|
| Describe a Secret | `kubectl describe secret <secret-name>`|
| Describe a Secret with values | `kubectl get secret <secret-name> -o yaml`|


## Decoding Secrets

`echo -n '<string to decode>' | base64 --decode`

## Pod injection

```
apiVersion: v1
kind: Pod
metadata:
  name: simple-webapp-color
  labels:
    name: simple-webapp-color
spec:
  containers:
  - name: simple-webapp-color
    image: nginx
    ports:
      - containerPort 8080
    envFrom:
      - secretRef:
          name: app-config
```
## Secrets in Pods as Volumes:
```
volumes:
  - name: app-secret-volume
    secret:
      secretName: app-secret
```

When using secrets a volumes each file mounted has the name as the key and the value is the content. 

`ls /opt/app-secret-volume`
`cat /opt/app-secret-volume/secretName`
`app-secret`

## Notes on Secrets 

* Secrets are not encrypted. Only encoded.
  * Do not check-in Secret objects to SCM along with code.
* Secrets are not encrypted in ETCD
  * Enable encryption at rest
* Anyone abel to create pods/deployments in the same namespace can access the secrets