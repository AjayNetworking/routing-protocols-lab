# RIPv2 - Routing Information Protocol Version 2

## Overview

RIPv2 is a distance-vector dynamic routing protocol used by routers to exchange routing information.

RIPv2 uses hop count as its routing metric. A route with fewer hops is preferred.

## Example Network

PC1 ---- R1 -------- R2 -------- R3 ---- PC3
          |          |          |
        LAN 1      LAN 2      LAN 3

LAN 1: 192.168.10.0/24
LAN 2: 192.168.20.0/24
LAN 3: 192.168.30.0/24

R1-R2: 10.0.0.0/30
R2-R3: 10.0.0.4/30

## RIPv2 Configuration

### Router R1

router rip
version 2
no auto-summary
network 192.168.10.0
network 10.0.0.0

### Router R2

router rip
version 2
no auto-summary
network 10.0.0.0
network 10.0.0.4
network 192.168.20.0

### Router R3

router rip
version 2
no auto-summary
network 10.0.0.4
network 192.168.30.0

## Verification

show ip route
show ip protocols
show ip rip database
show ip interface brief
ping
traceroute

## Advantages

- Simple to configure
- Easy to understand
- Suitable for small networks
- Supports classless routing with RIPv2

## Limitations

- Maximum hop count is 15
- Slow convergence compared with modern routing protocols
- Periodic routing updates consume bandwidth
- Not suitable for large enterprise networks

## Common Troubleshooting Issues

### RIPv2 Not Enabled
Verify that the router is running RIPv2.

### Incorrect Network Statement
Check that the correct networks are included under the RIP configuration.

### Auto-Summary
Use no auto-summary to prevent classful route summarization when using a classless network design.

### Missing Route
Use show ip route to determine whether routes learned through RIP are present.
