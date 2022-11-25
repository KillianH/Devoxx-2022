# [Istio](https://istio.io/)
#istio #k8s #serviceMesh #java
## [What's istio](https://istio.io/latest/about/service-mesh/)

- Secure service to service communication
- Service discovery
- Load balancing
- Routing / fail overs
- Policy layer access control rate limiting
- Automatic metrics  

## Istio architecture

- Control plane (config etc)
- Data plane (pod / consul ingress / egress)

## Demo

- Prepare a cluster (4 nodes min + cpu++ recommended )

- Install istio : Single curl ? -> istioctl to manage & install istio [Getting Started](https://istio.io/latest/docs/setup/getting-started/)

- **Egress can be skipped if no external traffic is needed**  

- Install Kiali / Zipkins + others created in the istio namespace (prometheus/grafana)

- JDL = JHister Domain language
	- Used to define a bunch of random stuff and create all kube ressources

- Istio proxy = consul proxy

- Manual deploy = happen at the deployment level  

- Automatic deploy = pod level
  

### [Virtual services from istio](https://istio.io/latest/docs/concepts/traffic-management/#virtual-services)
Define how trafic is routed to apps
Istio can merge similar routing rules (can do weird things sometimes)

<div style="page-break-after: always;"></div>

### [Destinations rules from istio](https://istio.io/latest/docs/concepts/traffic-management/#destination-rules)
Applied after routing is decided from istio. (Load balancer / circuit breaking etc)  

### [Gateways from istio](https://istio.io/latest/docs/concepts/traffic-management/#gateways)
Can be ingress or egress gateway

### [Istio service entries](https://istio.io/latest/docs/concepts/traffic-management/#service-entries)
Manage service external to the mesh

### [Sidecars](https://istio.io/latest/docs/concepts/traffic-management/#sidecars)
-   Fine-tune the set of ports and protocols that an Envoy proxy accepts.
-   Limit the set of services that the Envoy proxy can reach.

### Delay & Fault
- Can specify a delay on virtual service to test how the mesh is behaving with bad response time
- Can specify a fault on virtual service to test how the mesh is behaving with lot of faulty responses

### Auth / Security
+ Can do MTLS all over the data plane for E2E traffic encryption
+ Can handle oauth (easier to use a plugin)

### Is a service mesh worth it ?
**Pros**
- kube native microservice
- Reduced resp for dev
- No need to write / maintain code 
- AB canaray release etc
**Cons**
- Complex to debug
- Higher resource usage / running costs
- Business logic related policies might be trickier

[Slides](https://speakerdeck.com/deepu105/build-and-deploy-cloud-native-java-microservices-on-kubernetes-with-istio-service-mesh)