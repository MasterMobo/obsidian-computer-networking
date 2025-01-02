---
tags:
  - osi-layer
---
---
## 1. Purpose

The second layer, above the [[Physical Layer]].

Split into two sublayers with two distinct responsibilities:

### Logic Link Control

Responsible for [[Layer 2 Flow Control|flow control]] and [[Layer 2 Error Control|error control]]

### Medium Access Control

Responsible for framing, MAC addresses, Multiple (Medium) Access Control.

The Data Link Layer does not look closely into the packets, but it switches based on the physical network address.

In LAN, the transmission medium is shared. That is, multiple devices use the same medium to transmit data. This can lead to ***collision*** when two devices transmit at the same time.

---
## 2. MAC Address

MAC address are associated with the hardware of the network adapters.

Usually is a string of ***6 sets of two-digit characters***

**Ex**: 00-00-0c-12-34-56 or 0000.0c12.3456

The ***first three pairs*** signifies the ***manufacturer*** of the device, known as **Organizationally Unique Identifier (OUI)**

**Ex**:
- Dell: 00-14-22
- Cisco: 00-40-96

### MAC Frame Format

- **Start Frame**: informs devices that a frame is coming down the wire
- **Address Field**: source and destination MAC addresses
- **Type/Length Field** (optional): what type/length of data is coming
- **Data Field**: actual data sent by upper layers
- **Stop Frame Field (Frame Trailer)** (optional): used when length length of frame is not specified in Type/Length Field

>[!info]
>To resolve an IP address to a MAC address, [[Address Resolution Protocol (ARP) |ARP]] is used.

---
## 3. Medium (Multiple) Access Control

In a shared medium, we need to minimize collisions to maximize bandwidth utilization. There are many protocols that can help achieve this.

### 3.1 Random Access Protocols

Random access tries to minimize **reaction time** to improve performance
- Proceed with the transmission without waiting for acknowledgement (ACK)
- Deal with collision
- No station is superior to another

#### Pure ALOHA

- Station transmit **whenever they have data**; and listen to the medium
- If collision occurs, wait a **random time** and retransmit

Even when two frames slight overlap (collision), they are totally destroyed. Not efficient use of bandwidth.

![[Pure-ALOHA.jpg|center]]

More details
- All transmitted frames must be of **equal length** (L bits)
- After transmitting a frame, sender **waits for ACK** until timeout
$$
timeout = 2 t_{propagation}
$$
- If no ACK is received, sender assumes frame (or ACK) was destroyed
	- Sender **resends** the frame after waiting a **random amount of time**

#### Slotted ALOHA

Time on channel is divided into **uniform slots**. A central clock (or some other mechanism) synchronize all stations.

Stations are only allowed to transmit at the ***start*** of time slot.

Frames either ***miss or overlap totally***

Better utilization than Pure ALOHA, but still quite poor.

![[Slotted-ALOHA.jpg|center]]

#### Carrier Sense Multiple Access (CSMA)

CSMA is a type of protocol used to detect/avoid/resolve collisions in a shared medium. It aims to address certain weakness of simple protocols like ALOHA.

See more : [[Carrier Sense Multiple Access (CSMA)]]

---
See next:
- [[Network (Internet) Layer]]
