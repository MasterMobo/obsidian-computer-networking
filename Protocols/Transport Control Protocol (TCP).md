---
tags:
  - protocol
---
# Table of Contents

- [[#1. Purpose|1. Purpose]]
- [[#2. TCP Segment Format|2. TCP Segment Format]]
- [[#3. Establishing Connection|3. Establishing Connection]]
- [[#4. Terminating Connection|4. Terminating Connection]]

---
## 1. Purpose

TCP is a protocol in Layer 3-[[Transport Layer]] that provides ***reliable, in-order*** data transmission.

It combines the benefits of **packet-switching** (smaller packets, less congestion) with **circuit-switching** (reliable and stable connection).

TCP also contains **flow control** and **congestion control** for better delivery and performance:

- **Checksum** is used to detect corrupted data
- **Sequence numbers** are used detect missing data and put them back in order
- **Acknowledgments and retransmission** to ensure delivery
	- **TCP segments** are delivered in order. When a segment goes missing (acknowledgement is not received), it is retransmitted.
- **Window sizes** to avoid congestion
- **Timeout** based on round-trip time (e.g. when a segment takes to long to acknowledge)

>[!info]
>TCP works with **Socket address**, which is a combination of the IP address and the port number. The IP address identifies the host device, while the port number identifies the process (program) that is using the connection.

TCP should be used when reliable and guarantee delivery is important.
**Example use cases**: Email, document editing, file sharing,...

---
## 2. TCP Segment Format

The TCP segment header contains these notable fields:
- **Source port address**
- **Destination port address**
- **Sequence number**: number of the message
- **Acknowledgment number**: number to acknowledge the previous message (usually message number + 1)
- **Window size**: avoid congestion by limiting data size of the sender
- **Checksum**: error detection

---
## 3. Establishing Connection

To begin transmitting data, TCP first establish the connection from source to destination via the ***three-way handshake***.

1. Sender sends a SYN message
2. Receiver sends a SYNC + ACK message
3. Sender sends a ACK message

![[tcp-connect.png]]

>[!note]
>Notice how the ack number is the previous seq number + 1

If no ACK is received by the SYN message after a certain amount of time (usually 3-6 seconds), it re-transmit the message.

---
## 4. Terminating Connection

To end a connection, TCP does 2 round-way trips:
1. Sender send a FIN message
2. Receiver send an ACK message
3. Receiver send a FIN message
4. Sender send an ACK message

![[Pasted image 20241231174253.png|center]]

---
See next:
- [[User Datagram Protocol (UDP)]]