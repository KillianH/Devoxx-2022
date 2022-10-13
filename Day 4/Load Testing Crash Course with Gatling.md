# Load Testing Crash Course with Gatling
#gatling #load-test

## Why you must do load-testing ?
QA conditions =! prod conditions
Large audience
Seasonal peaks
Fast growth
Application sprawl
Product launch

Poor UX (crash/slowdowns) = Losses (sales/brand damaged)

Operating costs = Expensive
Scaling out = Complex
The cloud won't take care of perf.

## What is load-testing ?
Trying to simulate artificial traffic.
Validate application meets perf requirements
- Analyse response times
- Discover bottlenecks
- Size your infrastructure

## What load-testing is not ?
- Webperf (pagespeed)
- Running headless browers at scale

## Build realistic performance test
- Stateless
	- Traffic is anonymous
	- Can be executed in any order
	- Can replay recorded traffic
- Statefull
	- Logicial flows
	- Implement scenarios
Focus on most critical features
Iterate and improve

## Type of traffic
Simulate public facing traffic -> gatling default behavior
Testing microservices -> Must use shareConnections()

## Type of model
Open system model : new jobs arrive independently of jobs completion.
- Users keep on arriving
- Concurrent users is an output
Closed system model : new jobs only arrive after jobs completion.
- Capped concurrent users
- Injection slows down to limit

## Type of test
### Capacity test
How your app scales
### Stress test
How your app behaves under sudden load peak
### Soak test
If your app degrades over time
### Smoke test
Making sure that your test work correctly

## Test data
Don't test your caches
- No static values
- Inject test data into virtual users

## How to not measure
Issue with average on response time
- tong tail and outliers
- multiple modes
Don't use standard deviation
Good metrics : percentiles (50% median value)
You cannot average percentiles
Don't assume distributions, measure them properly.
Percentiles can define acceptance criterias.

## Dev lifecycle
Old way
- 1-2 times a year
- After dev and func tests
- 2 weeks before go-live

Today
- Integration in CI/CD
## By who
Old way
- experts
- central team
Create bottleneck / no collaboration

Today
- Collaboration: dev, ops, QA
- Dev for crafting & maintaining

## Tooling
Provisioning 
Monitoring
Load generator

## Gatling
Open source (core)
Code oriented
Support a lot of protocols