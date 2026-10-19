# Five-Router Static Routing Configuration & Troubleshooting

## Project Overview

This lab demonstrates the configuration and troubleshooting of a five-router network using Cisco Packet Tracer. The objective was to establish connectivity across multiple IPv4 networks using static routing and identify routing issues that prevented successful communication.

## Technologies & Networking Concepts

- Cisco Packet Tracer — Network simulation and topology design
- Cisco IOS CLI — Router configuration and troubleshooting
- IPv4 Addressing & Subnetting — /24 network configuration
- Static Routing — Next-hop configuration and route verification
- ICMP — Connectivity testing using ping
- Traceroute — Network path diagnostics
- Routing Tables — Forward and return path analysis
## Network Topology

The network consists of five Cisco routers connected in a linear topology.

**Router0 → Router1 → Router2 → Router3 → Router4**

| Network | Subnet Mask | Purpose |
|---|---|---|
| 192.168.10.0/24 | 255.255.255.0 | Router0–Router1 |
| 192.168.20.0/24 | 255.255.255.0 | Router1–Router2 |
| 192.168.30.0/24 | 255.255.255.0 | Router2–Router3 |
| 192.168.40.0/24 | 255.255.255.0 | Router3–Router4 |

## Configuration

Configured IPv4 addresses on router interfaces and established static routes to remote networks using Cisco IOS commands.

Example:

```cisco
configure terminal
ip route 192.168.40.0 255.255.255.0 192.168.10.2
end
```

## Troubleshooting Process

During testing, Router0 was unable to communicate with remote networks despite having static routes installed.

The following commands were used to investigate:

```cisco
show ip interface brief
show ip route
show running-config | include ip route
ping 192.168.20.2
traceroute 192.168.40.2
```

### Root Cause

A missing return route toward the 192.168.10.0/24 network prevented successful bidirectional communication.

### Resolution

Identified the missing route, configured the appropriate next-hop address, and retested connectivity.

## Verification

Connectivity was retested after correcting the routing configuration. Final end-to-end results and screenshots will be added after verification.

## Key Takeaways

- Static routes require correct destination networks, subnet masks, and next-hop addresses.
- Successful communication requires valid forwarding and return paths.
- Routing tables are essential for identifying missing or incorrect routes.
- A systematic troubleshooting process helps isolate network connectivity failures.

## Supporting Files

- Cisco Packet Tracer topology (`.pkt`) — to be uploaded
- Network topology screenshot — to be uploaded
- Routing configurations — to be uploaded
- Connectivity verification screenshots — to be uploaded
