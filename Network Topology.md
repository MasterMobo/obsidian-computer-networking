---
tags:
  - network
---
# Table of Contents

- [[#1. Network Topology|1. Network Topology]]
	- [[#1. Network Topology#1.1 LAN Topologies|1.1 LAN Topologies]]
		- [[#1.1 LAN Topologies#Star Topology|Star Topology]]
		- [[#1.1 LAN Topologies#Bus Topology|Bus Topology]]
		- [[#1.1 LAN Topologies#Extended Star Topology (Tree Topology)|Extended Star Topology (Tree Topology)]]
		- [[#1.1 LAN Topologies#Ring Topology|Ring Topology]]
	- [[#1. Network Topology#1.2 WAN Topologies|1.2 WAN Topologies]]
		- [[#1.2 WAN Topologies#Point-to-Point Topology|Point-to-Point Topology]]
		- [[#1.2 WAN Topologies#Hub and Spoke Topology|Hub and Spoke Topology]]
		- [[#1.2 WAN Topologies#Full Mesh Topology|Full Mesh Topology]]


---
## 1. Network Topology

Topology is how nodes in a network are interconnected.

**Physical Topology** is how devices are arranged and cabled in the real world.

**Logical Topology** only cares about the *logical* connections, not real-world factors like cabling, distances,...

### 1.1 LAN Topologies

#### Star Topology

All devices connected to a central node (usually a switch or a hub).

Central node relays information to other devices.

#### Bus Topology

Devices connected to a single cable, called a ***bus***. Devices interface with the bus through a ***tap***.

Every transmission propagates through the entire bus. Terminators at the end of the bus can remove the transmission once it has reach the end.

Devices transmits frames with address info through the bus. Other devices looks at the frames to see if they are the intended destination. If not, they ignore the transmission. 

#### Extended Star Topology (Tree Topology)

Combination of Star Topology and Bus Topology.

Has one or more central nodes connected by a bus.

Provides better scalability.

#### Ring Topology

Devices connected in a circle (or *ring*).

Devices transmit frames onto the ring, which goes in either clockwise or anti-clockwise direction.

When the frame reaches a device, it checks if the destination is correct. If not, it forward it to the next device on the ring.

Poor scalability.

![[LAN_topology.gif | center]]

---
### 1.2 WAN Topologies

#### Point-to-Point Topology

One node connects to another node

#### Hub and Spoke Topology

Similar to [[#Star Topology]], but for WAN. So it is much larger in scale/distance.

The central node is a LAN network, not a single device like Star Topology.

#### Full Mesh Topology

All nodes in connected to each other.

Provides redundancy for better failure handling. But has poor scalability and therefore more expensive.

![[wan-topology.png|center]]