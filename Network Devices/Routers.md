---
tags:
  - network-devices
---
---
## 1. Definition

Routers are network devices used to connect between *different networks* (LANs). 

Routers operate at Layer 3-[[Network (Internet) Layer]]. They deal with IP (logical) addresses.

When a switch forwards a broadcast frame (e.g. ARP request), it goes to all the devices in the network, which is called the **broadcast domain**. Broadcast traffic ***never*** goes outside the network (i.e. never go outside the router).

---
## 2. Routing Table

Routers maintain a routing table, which maps between an **IP address** (of a network) and a **network interface** (physical port).

Routers use this table to determine where to forward packets to reach a target network.

Example routing table:

| Network     | Interface          |
| ----------- | ------------------ |
| 10.0.0.0    | FastEthernet0/1    |
| 192.168.0.0 | GigabitEthernet1/1 |

---
## 3. Hardware

Physically speaking, we have three main components:
- Control Module: central control, like a CPU
- Switch Module: support communication between modules
- Line Cards: the ports where traffic comes in/out

Logically speaking, routers consist of 2 ***planes***:
- Control Plane - Central Processor Module (CPM)
- Data Plane - Line cards

![[router-hardware.png]]
---
## 4. How Routing Works

The **Routing Information Base** (RIB) is a database in the control plane that stores routing information about the network.

Routing protocols exchange routing updates on the ***control plane***. The router uses this information to update the RIB.

![[routing-1.png]]

>[!info] 
>Routing updates are propagated throughout all connected routers, which help them stay up-to-date (e.g. when a router goes down). This is called **convergence**.
>
>Convergence time is the time it takes for all status updates to finish. Shorter convergence time is better for network performance.

Based on certain protocol metrics, the CPM chooses the best routes from the RIB and writes them to the route table

![[routing-2.png]]

The routing information is transferred to the ***data plane*** (to every line card), and is stored in the **Forwarding Information Base (FIB**). 

The FIB helps improve performance by skipping the need for CPM to repeatedly give the line cards the routing information.

![[routing-3.png]]