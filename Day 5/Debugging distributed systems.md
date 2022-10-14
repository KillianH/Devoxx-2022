## Characterictis of distributed systems
- concurrency of components
- lack of a global clock
- Independent failure of components

## Fallacies of distributed computing
- Network is reliable
- Latency is zero
- Bandwith is infinite
- Network is secure
- Topology doesn't change
- There is one admin
- Transport cost is zero
- The network is homogeneous

## Structured approach
### Observe document
- Inspect log / errors / metrics / tracing
- Draw path from source to target.
- Document what you know
- Can we reproduce in a test ?
	- By injecting errors
- Tools
	- Whiteboard
	- Documentation
	- Tracing / logging / metrics
	- Tests
### Mininal reproducer
- Maximise the amount of debugging cycles
- Focus on short development iterations / feedback loops
- Get close to the action
- Tools
	- IDE / Shell script / SSH tunel / curl
### Debug client side
- Focus on eleminating anything that could be wrong on the client side
- Are we connecting to the right host ?
- De we send the right message ?
- Do we receive a response ?
- Not much different from local debugging
- Tools
	- IDE, Debugger, logging
### Check DNS and routing
- DNS
	- make sure you know what IP address the hostname should be resolved to
	- Verify that the client have the same result
- Routing
	- Verify you can reach the target machine
- Tools
	- host
	- nslookup
	- dig
	- etc...
### Check connection
- Can we connect to the port
- Do we get a reject or a drop ?
- Does the connection open and stay open ?
- Are we talking TLS ?
- What is the connection speed between us ?
- Tools
	- ifperf
	- telnet
	- nc
	- curl
### Inspect traffic / messages
- Do we send the right request ?
- Do we receive the right response ?
- How do we know ?
- How do we handle TLS ?
- Any load balancers or proxies in between ?
- Tools
	- tcpdump
	- curl
	- wireshark
	- network tab in browser
	- tls proxy
### Debug server side
- Inspect the remote host
- Can we attach a remote debugger ?
- Profiling
- Java flight recorder
- Strace
- Tools
	- ssh tunnel
	- debugger
	- strace
### Wrap up & post mortem
- Document the issue
	- Timeline
	- What did we see ?
	- Why did it happen ?
	- What was the impact ?
	- How did we find out ?
	- What did we do to mitigate and fix ?
	- What should we do to prevent repetition ?
- Tools
	- Whiteboard / documentation
### Summary
- Observe and document
- Create minimal reproducer
- Debug client side
- Check dns
- Check connection
- Inpect traffic
- Debug server side
- Wrap up 