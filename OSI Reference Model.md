---
tags:
  - protocol
---
# Table of Contents

- [[#1. The Need for Protocol Architecture|1. The Need for Protocol Architecture]]
	- [[#1. The Need for Protocol Architecture#1.1 What is a Protocol?|1.1 What is a Protocol?]]
	- [[#1. The Need for Protocol Architecture#1.2 Features of a Protocol|1.2 Features of a Protocol]]
	- [[#1. The Need for Protocol Architecture#1.3 Pros and Cons of Layering|1.3 Pros and Cons of Layering]]
- [[#2. The OSI Reference Model|2. The OSI Reference Model]]
	- [[#2. The OSI Reference Model#2.1 Layer 1 - Physical Layer|2.1 Layer 1 - Physical Layer]]
	- [[#2. The OSI Reference Model#2.2 Layer 2 - Data Link Layer|2.2 Layer 2 - Data Link Layer]]
	- [[#2. The OSI Reference Model#2.3 Layer 3 - Network Layer|2.3 Layer 3 - Network Layer]]
	- [[#2. The OSI Reference Model#2.4 Layer 4 - Transport Layer|2.4 Layer 4 - Transport Layer]]
	- [[#2. The OSI Reference Model#2.5 Layer 5 - Session Layer|2.5 Layer 5 - Session Layer]]
	- [[#2. The OSI Reference Model#2.6 Layer 6 - Presentation Layer|2.6 Layer 6 - Presentation Layer]]
	- [[#2. The OSI Reference Model#2.7 Layer 7 - Application Player|2.7 Layer 7 - Application Player]]
- [[#3. Data Encapsulation|3. Data Encapsulation]]
	- [[#3. Data Encapsulation#3.1 Data Segmentation|3.1 Data Segmentation]]
	- [[#3. Data Encapsulation#3.2 Protocol Data Unit (PDU)|3.2 Protocol Data Unit (PDU)]]

---
## 1. The Need for Protocol Architecture

Data communication is very complicated, with many moving parts. 

To make our lives easier, we divide communication into different ***layers***, each with its own purpose and duties. Changes to one layer should not affect other layers. 

This eases **maintenance** and **updating** of the system.

### 1.1 What is a Protocol?

A protocol is a set of ***rules*** that two (or more) participants need to follow in a conversation. 

A protocol defines the **format** and **order** of messages, as well as **actions** needed when transmitting/receiving messages.

In data communication, each layer has their own set of protocols. All the layers combined makes the ***protocol architecture***.

### 1.2 Features of a Protocol

1. **Syntax**
	- Data format, what does it look like?
2. **Semantics**
	- What does the data mean?
	- Error handling
3. **Timing**
	- Synchronization
	- Sequencing
### 1.3 Pros and Cons of Layering

**Pros**
- Simplify design and implementation for each layer
- Changes to one layer will not affect other layers
- Able to select implementations from different vendors
**Cons**
- Overhead in each layer (since we're adding extra data at each layer)
- Increased complexity

---
## 2. The OSI Reference Model

Stands for Open System Interconnection. Developed by the International Organization for Standardization (ISO) in 1984.

The most well-known framework for computer networks. 

The OSI model is not used in practical application nowadays as it was beaten out by the [[TCP IP Model]]. These days, it serves as a theoretical model. Hence the name "*reference model*".

The OSI model consists of 7 layers, from the bottom up:

### 2.1 Layer 1 - Physical Layer

Deals with **binary transmission** (bits).

Handles the physical link between end systems.

Defines how raw binary data is transmitted over the network.

Represent the **interface** between the medium and device.

See more: [[Physical Layer]]

### 2.2 Layer 2 - Data Link Layer

Deals with **frames**

Provides reliable transfer of information across physical link.

Synchronization 

Flow control

Error handling

See more: [[Data Link Layer]]

### 2.3 Layer 3 - Network Layer

Deals with **packets**

Guides packets from source to destination along the path, which may comprise multiple links.

Provides **connectionless** or **connection-oriented** services

Concerned with ***addressing*** and ***routing***.

### 2.4 Layer 4 - Transport Layer

Handles ***end-to-end*** transmission

Provide **connection-oriented** services

### 2.5 Layer 5 - Session Layer

Manages connection between nodes

Control **dialogues** between applications 

### 2.6 Layer 6 - Presentation Layer

Data formats

Data compression

Encryption

### 2.7 Layer 7 - Application Player

Enables application to access OSI environment.

Provided protocols commonly needed by users.

---
## 3. Data Encapsulation

Data travel through the protocol stack from **higher to lower** in the **sending node**, then from **lower to higher** in the **receiving node**.

Each layer it travels through, a header containing control information is added. This is referred to as ***encapsulation***.

At the receiving end, data is unwrapped from the bottom up. Each layer uses the header to carry out its duties. This is referred to as ***de-capsulation***.

![[osi-encapsulation.png]]

### 3.1 Data Segmentation

When the source data is too big, it is split into smaller chunks known as ***segments***. They are then reassembled at the destination.

Benefits:
- Different conversations can be interleaved. Long messages won't block other messages.
- Increase reliability of communication. Smaller packets can be retransmitted without resending the whole message.

### 3.2 Protocol Data Unit (PDU)

The sender inserts the header at a pre-specified position within the data frame. The result is a **Protocol Data Unit (PDU)**.

$$
Header + data = PDU
$$

![[pdu.png | center]]

---
See next:
- [[TCP IP Model]]