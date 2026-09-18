# EIGRP - Enhanced Interior Gateway Routing Protocol

## Overview

EIGRP is a Cisco-developed interior gateway routing protocol that uses the Diffusing Update Algorithm (DUAL) to calculate loop-free paths.

EIGRP can use bandwidth and delay as its primary routing metrics.

## Example Network

PC1 ---- R1 -------- R2 -------- R3 ---- PC3
          |          |          |
        LAN 1      LAN 2      LAN 3

LAN 1: 192.168.10.0/24
LAN 2: 192.168.20.0/24
LAN 3: 192.168.30.0/24

R1-R2: 10.0.0.0/30
R2-R3: 10.0.0.4/30

## EIGRP Configuration

### Router R1

router eigrp 100
network 192.168.10.0 0.0.0.255
network 10.0.0.0 0.0.0.3
no auto-summary

### Router R2

router eigrp 100
network 10.0.0.0 0.0.0.3
network 10.0.0.4 0.0.0.3
network 192.168.20.0 0.0.0.255
no auto-summary

### Router R3

router eigrp 100
network 10.0.0.4 0.0.0.3
network 192.168.30.0 0.0.0.255
no auto-summary

## Important EIGRP Concepts

### DUAL
DUAL calculates loop-free paths and selects successor and feasible successor routes.

### Successor
The successor is the best route to a destination network.

### Feasible Successor
A feasible successor is a backup route that satisfies EIGRP feasibility conditions.

### Autonomous System Number
Routers participating in the same EIGRP routing process use the same autonomous system number.

## Verification

show ip route
show ip protocols
show ip eigrp neighbors
show ip eigrp topology
show ip interface brief
ping
traceroute

## Advantages

- Fast convergence
- Supports unequal-cost load balancing
- Uses DUAL for loop-free path calculation
- Supports classless routing

## Limitations

- Historically associated with Cisco environments
- More complex than static routing and RIP
- Requires careful configuration in larger networks

## Common Troubleshooting Issues

### Neighbor Not Forming
Verify that routers use the same EIGRP autonomous system number and that the interfaces can reach each other.

### Incorrect Network Statement
Verify the network statements and wildcard masks.

### Missing Route
Use show ip route and show ip eigrp topology to verify learned routes.

### Interface Problem
Use show ip interface brief to verify that interfaces are up and have the expected IP addresses.
