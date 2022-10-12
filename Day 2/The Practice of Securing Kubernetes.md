# The Practice of Securing Kubernetes
#k8s #kubescape
Kubescape open source software created by the company of the speaker

Focused on security of the control plane

## API auth
Client secrets :
- private key
- token auth
- static password
- OpenID Connect
Rotation is an important protection factor

ABAC / RBAC Attribute/Role base access control
Webhook based decision delegation
Node authorization
AlwaysAllow

## RBAC :
Role(ApiGroups/Resource/Verb) <-> RoleBinding <-> Subject (User/Group/ServiceAccount)

Use least privilege principle

## Admission controller
RBAC is simple but limited
Limit what configuration a resource can have
Fine grained policies can be implemented by Admission controllers

## Audit Loging
Can be integrated to prometheus
Webhook / cloud provider

Trust and secrets
API server TLS identity
Kubelet client TLS identity
ETCD SSL keys
Disable anonymous access

## ETCD
Store all k8s secrets
Access control -> tls auth
API server can be configured to encrypt data

## Kubelet authorization & authentication
Publish two listeners : port + read only port (hide/disable)
Anonymous auth (only for testing)
Cert based auth (mtls)
Token based auth (tls + token)

## Node sensitive files
CA bundle file
Private key + cert for the node
Token webhook secrets
chmod 600

## Network access
Kube node should not be accessible from the public internet
Including kubelet port(s)
The only place to enable is the incoming traffic (node ports)

## Node bootstrapping
Bootstrap protocol
