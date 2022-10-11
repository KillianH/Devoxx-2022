# Kustomize with style
#k8s #kustomize #sops

Two ways to deploys :
- Pull from repository
- Push to the cluster through CI/CD

Helm Hell - Helm is not the solution

## Kustomize
### Peace of mind features
- Decoupe par app
- Then create recipe kustomization and include the list of yaml to deploy
- Advanced features included in kustomize cli that aren't available in kubectl
- Kustomize can generate configmaps (configMapGenerator)
	- A digest of the content is added at the end of the name of the configmap
- Set the namespace in the kustomization
- Can add suffix prefix
- List images 
- Replicas
- Can use helm chart in kustomize

### Deploy multiple different applications
- Overlays : override the base kustomize
	- Can reference a repository
- PatchesStrategicMerge : Only need to define the minimum info needed to override a definition
- Patches: define a path / value / ... an apply it to a ressource. (Mostly ingress)
- Components : provide extra features on demand (ex: openldap)
	- Remove duplication on specific features set needed
- Can extend kustomize with go (yay)
- Transformers (ex get a secret from [sops](https://github.com/mozilla/sops) and deploy a clear version)

