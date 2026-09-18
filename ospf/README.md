# OSPF - Open Shortest Path First

## Overview

OSPF is a link-state interior gateway routing protocol used to exchange routing information within an autonomous system.

OSPF uses the Shortest Path First algorithm and calculates routes based on cost.

## Example Network

PC1 ---- R1 -------- R2 -------- R3 ---- PC3
          |          |          |
        LAN 1      LAN 2      LAN 3

LAN 1: 192.168.10.0/24
LAN 2: 192.168.20.0/24
LAN 3: 192.168.30.0/24

R1-R2: 10.0.0.0/30
R2-R3: 10.0.0.4/30

## OSPF Configuration

### Router R1

router ospf 1
router-id 1.1.1.1
network 192.168.10.0 0.0.0.255 area 0
network 10.0.0.0 0.0.0.3 area 0

### Router R2

router ospf 1
router-id 2.2.2.2
network 10.0.0.0 0.0.0.3 area 0
network 10.0.0.4 0.0.0.3 area 0
network 192.168.20.0 0.0.0.255 area 0

### Router R3

router ospf 1
router-id 3.3.3.3
network 10.0.0.4 0.0.0.3 area 0
network 192.168.30.0 0.0.0.255 area 0

## Important OSPF Concepts

### OSPF Area
OSPF divides a routing domain into areas. Area 0 is the backbone area.

### Router ID
The router ID uniquely identifies an OSPF router.

### OSPF Cost
OSPF uses cost as its metric. Lower-cost paths are preferred.

### Neighbor Relationship
OSPF routers establish neighbor relationships to exchange link-state information.

## Verification

show ip route
show ip ospf
show ip ospf neighbor
show ip protocols
show ip interface brief
ping
traceroute

## Advantages

- Fast convergence
- Supports hierarchical network design
- Supports classless routing
- Uses cost to select paths
- Suitable for medium and large networks

## Limitations

- More complex than static routing or RIP
- Requires more planning and configuration
- Uses CPU and memory to maintain link-state information

## Common Troubleshooting Issues

### OSPF Neighbor Not Forming
Check that interfaces are up, IP addresses are correct, and OSPF parameters match.

### Incorrect Network Statement
Verify the network address and wildcard mask.

### Area Mismatch
OSPF interfaces forming a neighbor relationship must be configured in compatible areas.

### Missing Route
Use show ip route to determine whether OSPF routes are installed in the routing table.
