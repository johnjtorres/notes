June 26, 2022

# [CCIE R&S Instructor JP Discussing BGP States](https://www.youtube.com/watch?v=2JlD1ZaWbRo)

## Phase 1 = TCP
1. Idle
  - Attempt to establish TCP connection w/ port 179 with neighbor.
  - Listen for TCP connections from peer.
  - ConnectRetry timer starts 120 sec.
2. Connect
  - Wait for TCP connection to be established
3. Active
  - Attempt another TCP connection

--- 
## Phase 2 = BGP
4. OpenSent
  - OPEN message
    - BGP version
    - AS number
    - Hold time
    - BGP ID
  - If error, send notification and go to Idle state
  - If successful, BGP starts sending keepalives
5. OpenConfirm
  - BGP peers waiting for keepalives
6. Established
  - Exchange of updates
  - Update/keepalive resets the hold time
  - Default keepalive = 60s
  - Default hold time = 180s

