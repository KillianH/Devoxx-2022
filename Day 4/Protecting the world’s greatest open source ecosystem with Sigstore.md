# Protecting the world’s greatest open source ecosystem with Sigstore
#sigstore

## Why no one check the integrity of signed artifacts ?
Because dev are lazy & don't want the toil associated to managing keys.

## TUF - The update framework
Provides a framework for distributing updates that is safe from a variety of attacks :
- Vuln to key compromises
- Malicious mirrors
- Roll back attacks
- Fast forward attacks

## Sigstore keyless signing
### Fulcio
- Embed your verified identity
- Short lived signing certificates
- Discard private keys after use
- Auditable Certificate Transparency logs
### Who signed this ?
- OIDC tokens are issued by various identity authorities for people or machines
### Rekor
Transparency log
### Clients
go / js / python / java