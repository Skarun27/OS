
## Routing Protocols

#### Distance Vector Protocol (DVP)
1. **Mechanism**: Routes are determined by the number of hops between the source and destination.
2. **Pros**: Simplicity, suitable for small networks.
- **Cons**: Slow to converge, prone to routing loops, inefficiency in large networks.
3. **Decision Factors**: Primarily hop count; does not consider path bandwidth, delay, or reliability.

#### Link State Protocol (LSP)
1. **Mechanism**: Each router builds a complete map of the network topology to calculate the shortest path to every destination.
2. **Pros**: Fast convergence, more effective at finding the most efficient route, avoids routing loops.
3. **Cons**: Requires more memory and processing power than DVP.
4. **Decision Factors**: Path cost based on various metrics like bandwidth, delay, reliability, and load.

#### Border Gateway Protocol (BGP)
1. **Mechanism**: Routes between autonomous systems (ASes) by sharing reachable networks and making decisions based on policies, not just path metrics.
2. **Pros**: Enables the global internet by managing inter-AS routing, highly scalable and flexible in policy enforcement.
3. **Cons**: Complexity, vulnerability to misconfiguration and malicious attacks.
4. **Decision Factors**: Policy (e.g., business agreements), path attributes (e.g., AS-path length, origin type, MED), not just physical distance or hop count.

### Factors Affecting Routing Decisions

1. **Hop Count**: The number of intermediate devices (routers) a packet must pass through. Used by DVPs like RIP. Lower hop count is preferred, but doesn't account for link quality or bandwidth.

2. **Path Cost**: Used by LSPs like OSPF, it considers various metrics to calculate a cost for each path. Lower cost paths are preferred. Metrics include:
   - **Bandwidth**: Higher bandwidth links are preferred as they can handle more data.
   - **Delay**: Lower delay (latency) paths are preferred for faster data delivery.
   - **Reliability**: More reliable links (e.g., less error-prone) are preferred.
   - **Load**: Links with lower utilization are preferred to avoid congestion.

3. **Policy Decisions**: In BGP, decisions can be based on non-technical factors, including:
   - **Business Relationships**: Prefer routes through partners or providers with favorable terms.
   - **Political Considerations**: Avoid routing through certain countries or regions.
   - **Economic Factors**: Choose routes that minimize cost.

4. **Administrative Weight**: Network administrators can manually assign preference to certain routes, overriding automatic routing decisions for specific management purposes.

### Summary

1. **DVP** is best for small networks, using hop count as the primary metric, leading to simplicity but potential inefficiency in route selection.
2. **LSP** excels in larger networks by considering multiple path metrics, enabling fast, efficient routing decisions but requiring more resources.
3. **BGP** is essential for the internet, focusing on policy-based routing across autonomous systems, accommodating a mix of technical and non-technical factors.