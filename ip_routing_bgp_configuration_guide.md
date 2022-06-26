June 26, 2022

# [IP Routing: BGP Configuration Guide](https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/iproute_bgp/configuration/xe-16/irg-xe-16-book/configuring-a-basic-bgp-network.html)

## BGP Peer Session Establishment

1. Idle - waiting for start event
2. Connect - peer trying to establish TCP connection
3. Active - BGP process trying to estabish TCP session
4. OpenSent - TCP done, send an OPEN message
  - If an error occurs with the BGP peering process, a notification is sent and the session transitions to the idle state
5. OpenReceive - Received OPEN message from peer
6. Established - Initial keepalive received, exchange updates