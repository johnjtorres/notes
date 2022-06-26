June 26, 2022

# [INE Live Webinar: Introduction to BGP Path Attributes
](https://www.youtube.com/watch?v=Ly6wg4PdunM&t=669s)

## What are Path Attributes?
- Describe a prefix
- Best Path Algorithm, loop prevention, tagging, informative

## Types of Path Attributes
- Well-known mandatory
- Well-known discretionary
- Optional transitive
- Optional non-transitive

## Overview of the Best Path Algorithm
1. N: Next-hop, it should be reachable
2. W: Weight, bigger value is preferred*
    - local to router
3. L: Local Preference, bigger is preferred*
    - iBGP neighbors only
4. L: Locally Originated Routes
    - injected into BGP via network command or redistribution
5. A: AS_PATH length, smaller length is preferred*
    - last AS is the originating AS
    - AS Path prepending: artificially increasing AS_PATH
6. O: Origin, Prefer i > e > ?*
    - i: network command
    - e: egp (won't see this one)
    - ?: redistribute command
7. M: MED, smaller is preferred*
8. N: Neighbor type, preferrer eBGP over iBGP
9. I: IGP metric to next_hop, smaller value is preferred
10. O: Oldest (longest-known) eBGP route
11. L: Lowest neight BGP RID
12. L: Lowest neighbor IP address

* = Path Attributes
**NWLLA OMNI OLL**