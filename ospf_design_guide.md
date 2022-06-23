June 23, 2022

# [**OSPF Design Guide**](https://www.cisco.com/c/en/us/support/docs/ip/open-shortest-path-first-ospf/7039-1.html#anc1)

## **What do we mean by link-states?**

- Link = interface on a router
- Link state would be all of the information pertaining to that interface such as the IP address, mask, attached neighbors.

## **Shortest Path First Algorithm**

1. Exchange link-state advertisements with neighbors
2. Copy LSAs received to link-state db and pass the LSAs along to other neighbors.
3. Run the Shortest Path First algorithm on the link-state database to build shortest path tree to every destination.
4. Result is ip address, cost, and next-hop are installed in the routing table.

## **OSPF Cost**
- Inversely proportional to bandwidth
- cost = 100_000_000/bandwidth(bps)

## **Areas and Border Routers**
- Routers within an area will have the same link-state database to limit the propagation of LSAs.
- Area Border Routers have interfaces in backbone area and non-backbone areas.
- Internal Routers have all interfaces in one area.
- Autonomous System Border Routers redistribute routes from other protocols into OSPF.

## **The Backbone and Area 0**
- Intra-area routes are routes that belong within an area. (O)
- Inter-area routes are routes from a different area. (O IA)
- External routes are routes redistributed into OSPF. (O E1 or O E2)

## **Neighbors**
- Parameters must match to become neighbors
  - Area ID
  - Authentication
  - Hello and Hold timers
  - Area stub flag

## **Adjacencies**
- Routers will become adjacent only with DR and BDR on a multi-access segment.

## **DR Election**
1. Highest OSPF interface priority
2. Highest RID
3. Repeat for BDR

## **Building the Adjacency**
| State | Description |
| ----- | ----------- |
| Down | Nothing has happened yet. |
| Attempt | Nothing received from neighbor on NBMA neighbor.|
| Init | Hello packet received from neighbor, but two-way communication not established. |
| 2-way | Router sees itself in neigbor's hellos. DR/BDR election. |
| Exstart | Elect master/slave for database exchange. |
| Exchange | Exchange DBD packets. |
| Loading | Send Link-State Requests/Acks |
| Full | Fully adjacent |

## **OSPF and Route Summarization**
- Combine multiple route advertisements into one at an ABR.
- Better to summarize a route going into the backbone area.

## **Inter-area Summarization**
`area` _area-id_ `range` _address-mask_
- _area-id_ is the area containing the summarized routes.

## **External summarization**
`summary-address` _network mask_
- Only performed on ASBR summarizing routes redistributed into OSPF.
 