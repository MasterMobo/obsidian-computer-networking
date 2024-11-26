---
tags:
  - network
---
# Table of Contents

- [[#1. What is a Network?|1. What is a Network?]]
- [[#2. LAN|2. LAN]]
- [[#3. MAN|3. MAN]]
- [[#4. WAN|4. WAN]]
	- [[#4. WAN#4.1 Circuit Switching|4.1 Circuit Switching]]
	- [[#4. WAN#4.2 Packet Switching|4.2 Packet Switching]]
		- [[#4.2 Packet Switching#4.2.1 Datagram|4.2.1 Datagram]]
		- [[#4.2 Packet Switching#4.2.1 Virtual Circuits|4.2.1 Virtual Circuits]]
		- [[#4.2 Packet Switching#4.2.3 Datagram vs Virtual Circuits|4.2.3 Datagram vs Virtual Circuits]]

---
## 1. What is a Network?

A network is a set of **nodes** (devices) connected by **communication links**.

There are 3 main types of networks: **LAN**, **MAN** and **WAN**

## 2. LAN

Stands for **Local Area Network**.
- Covers small scope: Building or small campus
- Much ***higher data rates***

LAN Configuration:
- **Switched Ethernet**: single or multiple switches
- **Wireless**: easier to use, slower and more prone to connection issues

Intranet: Only available to those inside the network.
Extranet: Allows users from outside the network.

## 3. MAN

Stands for **Metropolitan Area Networks**
- Larger than LAN, but smaller than WAN
- Spans a metropolitan area

---
## 4. WAN

Stands for **Wide Area Network**
- Biggest type, spans large geographical areas (cities, countries, continents,...) 
- Requires infrastructure
- Can interconnect several LANs using **switching nodes**

>[!note]
>The Internet is also considered a WAN. In fact, it is the world's biggest WAN.

Traditional WANs are implemented using:
- [[#4. WAN#4.1 Circuit Switching|Circuit Switching]]
- [[#4. WAN#4.2 Packet Switching|Packet Switching]]

Modern WANs are implemented using:
- Frame Relay, ATM
- Gigabit Internet, Internet Protocol technologies

### 4.1 Circuit Switching

Dedicated communication path is establish for the whole duration of the communication. 

Three phases:
- **Establish**
- **Transfer**
- **Disconnect**

Nodes must have switching and channel capacity to establish connection.

Used in ***telephone networks***.

---
### 4.2 Packet Switching

Data is split into small chunks known as ***packets***, which are sent in parallel.

Packets are sent from node to node between source and destination.

Packets are **labeled** with information for the receiver to reassemble the data. It also comes with information about **routing** and **addressing**.

#### 4.2.1 Datagram

**Connectionless** approach.

Each packet is treated **independently**. That is, different packets can take different routes to get to the destination.

All packets have information about destination address in the header. Intermediate nodes choose which node to send to next. 

Packets can go missing or out of order. Therefore, receiver needs to re-order the packets.

![[datagram-switching.gif]]

#### 4.2.1 Virtual Circuits

**Connection-oriented** approach.

**Pre-planned route** is established before packets are sent. Packets are sent in order.

Packets contains a **virtual circuit identifier** instead of destination address. No routing decision is required for each packet.

Virtual circuits are cleared after transfer is complete.

![[virtual-circuit-switching.gif]]

#### 4.2.3 Datagram vs Virtual Circuits

|      | Datagram                                                                                                                                                                                                                        | Virtual Circuits                                                                                       |
| ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| Pros | - Highly scalable, can handle large traffic<br>- Flexible, can support variable packet sizes and data rates<br>- Simple routing since packets can be routed dynamically<br>- Lower latency since no delay is required for setup | - Guaranteed delivery<br>- Lower error rates<br>- Efficient use of bandwidth                           |
| Cons | - Higher error rates, no guaranteed delivery<br>- Increased network congestion                                                                                                                                                  | - Limited scalability, not suitable for large networks<br>- Increased setup time<br>- Fixed data rates |

---

See next:
- [[Network Topology]]