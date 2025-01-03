---
tags:
  - protocol
---

## 1. Definition

An error is when a (or multiple) bit is altered during the transmission.

Errors could be caused by noise, interference, loss of synchronization,...

Types of errors:
- Single bit error: only 1 bit is altered (e.g. white noise)
- Burst error: contiguous sequence of bits that is altered (e.g. impulse noise, fading in wireless)

Error control is the **detection** and **correction** of errors in the transmission of frames.
- Frames can be **lost** (fails to arrive)
- Frames can be **damaged** (arrives but bits have been altered)

**Automatic Repeat Request (ARQ)** is a type of error control protocol that turns potentially unreliable data into reliable.

---
## 2. Stop-and-Wait ARQ

Lost data frame:
- When a frame is lost or damaged, no ACK is sent from receiver
- Sender waits for timeout, then retransmit the frame

![[stop-and-wait-arq-lost-frame.png|center]]

Lost ACK:
- Frames are labeled 0 or 1 alternatively
- If timeout and no ACK received, sender retransmits the frame
- If receiver sees 2 frames in a row with the same label. It has detected an error
	- Receiver discards the second frame, but sends ACK0 to each

![[stop-and-wait-arq-lost-ack.png|center]]

Simple but inefficient

---
## 3. Go-Back-N ARQ

Based on [[Layer 2 Flow Control#3. Sliding Window Flow Control|sliding window]]

Uses the **sequence number** to detect lost frames.

If error happens, receiver transmit a **rejection**:
- It discards that frame and all future frame until error is resolves
- Sender must **go back** and retransmit **all frames** from the error onwards

More efficient than Stop-and-Wait ARQ, but has to retransmit a lot of frames when error occurs. Therefore still quite inefficient.

---
## 4. Selective Reject ARQ

Also based on [[Layer 2 Flow Control#3. Sliding Window Flow Control|sliding window]]

Also called **selective retransmission**.

Only retransmit frames that are rejected.

Valid frames are still buffered inside the receiver.

=> **Minimizes retransmission**

However, larger buffer is needed in the receiver, and transmission logic is more complex.