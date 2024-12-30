---
tags:
  - osi-layer
---
---
## 1. Purpose

## 2. IP Packet Header

The packet header contains summary information about the packet. Notable fields include:

- **Source Address**: IP address of the source device
- **Destination Address**: IP address of the destination device
- **Type of Service** (ToS): defines the Quality of Service (QoS). For example, how fast your download/upload speed is, the size of your bandwidth,...
- **Total Length**: total length of the packet in bytes
- **Protocol**: the protocol being encapsulated for this packet (e.g. ARP)
- **Time to Live** (TTL): 
	- How many *hops* this packet can survive. 
	- When it hops through a router, it decrease the TTL by 1. If TTL is 0, the packet is dropped.
	- This is to avoid **infinite loops** when packets are sent across the network.

## 3. IPv4 

IPv4 is an older version of the Internet Protocol. It uses **32-bit addresses** (which is limited) with **subnetting** to provide more address flexibility. Still used today in almost every network.

See more: [[IPv4]]

## 4. IPv6

## 5. Routers

Routers are network devices used to route packets between different networks. They use IP addresses to achieve routing.

See more [[Routers]]