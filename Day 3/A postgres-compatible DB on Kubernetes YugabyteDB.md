# A postgres-compatible DB on Kubernetes: YugabyteDB
#k8s #postgres

## Archictecture
Cluster with 4 nodes
- Local storage on nodes. The db will distribute the data
- 3 master (small pods) (admin clients)
- n server (persistent volume) (app clients)
- Statefull set in every availability zones

## Failure case with replication factor 3
One node fails without sql processing
- New shards leaders will be elected to another node
With sql processing
- Wait 3s to elec new leaders on another node
When connected to a pod that died
- App will get an error and will retry to connect to another if you have a pool of connection

## Feature
Fully compatible with postgres / open source
