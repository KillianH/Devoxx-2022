# NewSQL, the holy grail of databases?
Focus on 
- #VoltDB
- #NuoDB

## VoltDB
### Partitionning
- In memory storage
- Distributed serialized processing
	- If transactions affect multiple partitions they can be processed in parrarel
	- Timestamp ordering
	- No need for locks
	- Deadlock not possible
- Replicating tables
	- Best case few write multiple reads
- Sql compliant but not quite 
- Does not implement forein key constraint

## NuoDB
- Partitioning is range based
- Multi version concurrency control
	- Needs high precision clock sync of the nodes
	- Readers do not block writers
	- Writers do not block readers
	- But deadlocks are possible
- Allows unique secondary indexes


## NewSQL can be
- Overkill
- Lack standards (diff features / limitations)
- Small community
- Lack of documentation

## When to use
- Large amount of data
- High volume of data
- Low impedance

## Is newsql the holy grail ?
### **No**

## What is the holy grail ?
- CAP Theorem
- New sql claims to be Consistent / Partitionned 
