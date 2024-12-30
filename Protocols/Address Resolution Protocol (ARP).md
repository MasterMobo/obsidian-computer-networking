---
tags:
  - protocol
---
---
## 1. Definition

ARP maps IP addresses to MAC addresses within a *local network*. 

Operating at the [[Data Link Layer]] (Layer 2), it supports Layer 3 by enabling communication between devices on the same subnet. 

When a device needs to send data, it *broadcasts* an ARP request for the target IP's MAC address. The matching device responds with its MAC address, allowing direct communication.

>[!info]
>A broadcast is a special type of frame that is received by everyone on the network (broadcast domain). It is usually sent on the ***broadcast address***, which is usually the last address of the subnet (e.g. 192.168.10.255/24)

## 2. ARP Table

The ARP table (aka ARP cache) stores mappings between the IP address and the MAC address after a new ARP request is successful.

ARP tables reduce the need for repeated broadcasts and improving network efficiency.