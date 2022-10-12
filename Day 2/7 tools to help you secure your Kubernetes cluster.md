# 7 tools to help you secure your Kubernetes cluster
#vault #kubescore #kubiscan #falco #GCR #open-policy-agent #kubovisor
## Frequent cause for security issues

- Sensible data
- Infra
- Cluster config
- Authorizations
- Workload content or config
- Lack of policies
- Failed components or applications
- No respect of best practices

## Vault

Tool to manage secrets and protect sensitive data
Vault agent to inject secrets with annotations
What's wrong with kube secrets ?
can be encrypted at REST
but just encoded to base64

## KuboScore (SAAS)
Automated solution to perform an audit of your kube cluster
Score & scenarios are free
Detailed reports aren't

## KubiScan
Analyse risky RBAC permissions
Helps maintain the principle of Least privilege

## Falco
Detects threats at runtime by observing the behavior of app & containers

## GCR with vuln scanning
Container image registry with vuln scanning

## Open Policy Agent
Allows to apply fine-grained policies on the cluster

## KuboVisor
Easy to use tool to supervize your Kubernetes clusters
Subscription based