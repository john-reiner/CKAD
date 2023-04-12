# Service Accounts

To access the kubernetes API server you need an authentication token. The processes running inside a container use a service account to authenticate with the kubernetes API server. This provides an identity to your pods.

Each secret is mounted by default under the var/run/secrets/kubernetes.io directory. 
## Commands: 

| Description | Command |
| --- | ----------- |
| List all service accounts | `kubectl get serviceaccount` |
| Create a service account | `kubectl create serviceaccount <sa-name>` |
| describe a service account | `kubectl describe serviceaccount <sa-name>` |


creates a token automatically, stored as a secret token