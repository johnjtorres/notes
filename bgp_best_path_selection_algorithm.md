June 25, 2022

# [BGP Best Path Selection Algorithm](https://www.cisco.com/c/en/us/support/docs/ip/border-gateway-protocol-bgp/13753-25.html)

## Why routers ignore paths?
- marked as not synchronized
- NEXT_HOP inaccessible
- local AS seen in AS_PATH (eBGP)
- bgp enforce-first-as
- marked as received-only

## How the Best Path Algorithm Works
1. weight
2. local preference
3. local path
4. shortest AS_PATH
5. IGP > BGP > Incomplete
6. lowest MED
7. eBGP > iBGP
8. lowest IGP metric
9. oldest path
10. lowest RID
11. lowest cluster list length
12. lowest neighbor address