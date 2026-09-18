# Routing Protocol Troubleshooting

## Overview

This section documents common routing problems and a structured troubleshooting process.

## Troubleshooting Methodology

1. Verify physical connectivity.
2. Check interface status.
3. Verify IP addressing and subnet masks.
4. Check the routing table.
5. Verify the routing protocol configuration.
6. Check neighbor relationships.
7. Test connectivity with ping.
8. Use traceroute to identify the path.

## Useful Cisco Commands

show ip interface brief
show ip route
show ip protocols
show running-config
ping
traceroute

## Common Problems

### Interface Down
Check the interface status and verify that the interface is enabled.

### Incorrect IP Address
Verify the IP address and subnet mask on both sides of the connection.

### Missing Route
Check the routing table and verify that the expected route has been learned or configured.

### Routing Neighbor Failure
Verify that routing protocol parameters match between neighboring routers.

### Connectivity Failure
Use ping and traceroute to identify where communication is failing.
