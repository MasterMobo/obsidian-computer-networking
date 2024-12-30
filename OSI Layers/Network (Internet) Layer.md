---
tags:
  - osi-layer
---
# Table of Contents

- [[#1. Purpose|1. Purpose]]
- [[#2. IP Packet Header|2. IP Packet Header]]
- [[#3. IPv4|3. IPv4]]
- [[#4. IPv6|4. IPv6]]
- [[#5. Routers|5. Routers]]

---
## 1. Purpose

The Network Layer (Internet Layer for TCP/IP) is in charge of routing packets across different networks.

This layer handles the IP address (logical address) to provide routing.
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

**128 bit** address. Modern version of IP

Supposed to replace IPv4, but is still used in parallel.

Much larger address space, no need for subnetting.

More optimized than IPv4, simpler routing.

>[!info]
>To migrate from IPv4 to IPv6, we use ***tunneling***. This works by encapsulating the IPv6 header within the IPv4 packet.
>
>![[ip-tunneling.png]]
## 5. Routers

Routers are network devices used to route packets between different networks. They use IP addresses to achieve routing.

See more [[Routers]]

---
See next:
- [[Transport Layer]]