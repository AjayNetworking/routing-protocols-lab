# Static Routing

## Overview

Static routing is a routing method where network routes are manually configured by a network administrator.

Unlike dynamic routing protocols, static routes do not automatically learn or update routes.

## Example Network

PC1 ---- R1 -------- R2 ---- PC2
          |          |
        LAN 1      LAN 2

LAN 1: 192.168.10.0/24
LAN 2: 192.168.20.0/24
R1-R2: 10.0.0.0/30

## Static Route Configuration

### Router R1

ip route 192.168.20.0 255.255.255.0 10.0.0.2

### Router R2

ip route 192.168.10.0 255.255.255.0 10.0.0.1

## Verification

show ip route
show ip interface brief
ping
traceroute

## Advantages

- Simple for small networks
- Predictable routing behavior
- No dynamic routing protocol required
- No routing protocol update traffic

## Limitations

- Routes must be configured manually
- Difficult to maintain in large networks
- Does not automatically adapt to topology changes
- Configuration errors can cause connectivity problems

## Common Troubleshooting Issues

### Incorrect Next Hop
Verify that the next-hop IP address is reachable.

### Incorrect Network Address
Verify the destination network and subnet mask.

### Missing Return Route
The destination router must have a route back to the source network.

### Interface Down
Use show ip interface brief to verify that the required interfaces are operational.
