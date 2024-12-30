---
tags:
  - protocol
---
# Table of Contents

- [[#1. The TCP/IP Model|1. The TCP/IP Model]]
	- [[#1. The TCP/IP Model#1.1 Layer 1 - Physical Layer|1.1 Layer 1 - Physical Layer]]
	- [[#1. The TCP/IP Model#1.2 Layer 2 - Network Access Layer|1.2 Layer 2 - Network Access Layer]]
	- [[#1. The TCP/IP Model#1.3 Layer 3 - Internet Layer|1.3 Layer 3 - Internet Layer]]
	- [[#1. The TCP/IP Model#1.4 Layer 4 - Transport layer|1.4 Layer 4 - Transport layer]]
	- [[#1. The TCP/IP Model#1.5 Layer 5 - Application Layer|1.5 Layer 5 - Application Layer]]
- [[#2. Addressing in TCP/IP|2. Addressing in TCP/IP]]

---
## 1. The TCP/IP Model

The de facto framework for developing computer communications standards. Widely used by the **Internet**.

Developed by the US Defense Advance Research Project Agency (DARPA) for its packet-switch network - ARPANET.

Uses two key protocols: **TCP** and **IP**

Similar to [[OSI Reference Model]], but with some changes.

Consists of 5 layers (although some standards only consider 4):

### 1.1 Layer 1 - Physical Layer

Interface between device and medium

Specifies transmission medium, nature of signals, data rate,...

Some standards group this with layer 2

See more: [[Physical Layer]]

### 1.2 Layer 2 - Network Access Layer

Handles routing for end systems in the ***same network***.

Also referred to as **Data Link layer**

See more: [[Data Link Layer]]

### 1.3 Layer 3 - Internet Layer

Handles routing for end systems in the ***different network***.

Internet Protocol (IP) is used to provide routing across multiple networks.

IP is implemented in end systems, as well as **routers**. Which, connects two networks by relaying data.

Also referred to as **Network Layer**

See more: [[Network (Internet) Layer]]

### 1.4 Layer 4 - Transport layer

Provides ***end-to-end*** services

TCP protocol is used for reliability.

### 1.5 Layer 5 - Application Layer

Supports user application.

This layer combines layers 5, 6 and 7 of the [[OSI Reference Model]] into one layer.

---
## 2. Addressing in TCP/IP

Each layer in the TCP/IP model uses different types of addresses. They are, from top down:

- **Specific address**
- **Port address**
- **Logical address** (IP address): could change
- **Physical address** (MAC address): stays permanent


![[tcpip-addressing.jpg]]