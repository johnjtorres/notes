---
Date: June 22, 2022
Article: https://www.cisco.com/c/en/us/support/docs/ip/enhanced-interior-gateway-routing-protocol-eigrp/16406-eigrp-toc.html
---

# EIGRP

## I. EIGRP Theory of Operation<br>

### a. Neighbor discovery and maintenance

- Routers become neighbors when they see eachother's hellos.
- Timers
  - Hello time: rate at which hellos are sent. (5s high bw, 60s low bw)
  - Hold time: amount of time without receiving a hello before neighbor is marked dead. (3x hello)

### b. Building the Topology Table

- Contains information used to build distances and vectors.
- Used to calculate the best loop-free path which is then used to feed the RIB.

### c. Metrics

- Minimum bandwidth
- Total delay

### d. Feasible Distance, Reported Distance, and Feasible Successor

- Feasible Distance: lowest distance to destination.
- Reported Distance: distance reported by neighbor.
- Feasible Successor: next-hop for a path whose reported distance is less than the feasible distance.

---

## II. Split Horizon and Poison Reverse<br>

- Split Horizon: never advertise a route out the interface that route was learned.
- Poison Reverse: when a route is learned, advertise the route as unreachable out the same interface through which is what learned.

---




