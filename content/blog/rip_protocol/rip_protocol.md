---
title: RIP Protocol Project
description: Implementation of RIP Protocol created in collaboration with Adam Venroy
date: 2023-08-23
tags: 
---
# Implementing the RIP Routing Protocol in Python

During my study abroad in New Zealand, one of my computer networking courses involved implementing the Routing Information Protocol (RIP) in Python. RIP is a distance-vector routing protocol used to exchange routing information between routers.

For this project, I worked in collaboration with Adam Venroy to build out an incomplete implementation of RIP v2 as specified in RFC 2453. Our implementation handles the core functionality namely:
- Sending and receiving RIP response messages
- Processing routing table updates
- Managing router timeouts and triggered updates
- Poison reverse to prevent routing loops

Some limitations of our implementation:
- No authentication
- No support for route tags, subnet masks, or next hops
- Uses port numbers from the config file instead of ip addresses
- Does not handle RIP queries

## Implementation Details

Each router in our RIP implementation is simulated by a separate Routing Demon process configured from a file specifying the router ID, ports, neighbors, and timers. The Routing Demon opens UDP sockets on its input ports to receive RIP packet updates. Internally, it uses a distance vector table stored in a nested dictionary to track the costs to each known destination router. This table gets populated and updated as RIP responses are received. The demon also maintains its own routing table containing the next hop, interface, metric, and timers for each route. It leverages Python's struct library to encode and decode the raw RIP packet byte arrays. And it implements internal timers to manage timeout of stale routes and triggering rapid updates when the topology changes. The core routing logic and control plane mechanisms were built from scratch in Python without any external libraries. Each Routing Demon serves as an autonomous router emulation able to receive and propagate routing updates through the exchange of RIP packets.

## Key Components

Some of the key components we implemented:

RIP Message Processing - Parses incoming RIP response packets and processes the routing table entries to update the local routing table. This includes validating metrics and router IDs.

Triggered Updates - Monitors routing changes and can trigger an immediate update to neighbors rather than waiting for the next periodic update. This speeds up convergence.

Timers - Manages time-based behaviors like timing out stale routes and garbage collecting old deletions.

Routing Table - Stores routes, metrics, next hops, and timers in a dictionary structure.

Packet Encoding - Uses Python struct library to encode and decode RIP packet byte arrays.
Lessons Learned

# Experience Gained

Working on this project gave me hands-on experience with:

    Implementing a real networking protocol from its RFC specification
    Packet encoding and parsing
    Managing router state and time-based behaviors
    Optimizing convergence and stability in a distributed routing algorithm
    Python

Let me know if you have any other questions! I'm happy to discuss the project in more depth.
