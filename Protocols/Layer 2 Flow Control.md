---
tags:
  - protocol
---

## 1. Definition

Flow control is a mechanism used to ensure the transmitting entity does not become **overwhelmed** 
- When a data is received, the receiver stores it in a **data buffer**. Flow control helps avoid ***buffer overflow***

Flow control is influenced by:
- Transmission time: time to emit all bits into medium
- Propagation time: time for a bit to traverse from source to destination

---
## 2. Stop-and-Wait Flow Control

Most simple type of flow control.

- Source transmits a frame
-  Source **wait** for ACK before sending next frame
- Destination receives and replies with ACK (acknowledgement). Sequence number of next frame is included in ACK
- Destination can stop flow by not sending ACK

Not very efficient when sending **multiple** frames at a time. Because it has to wait for ACK for each frame.

For high data rates and long distances, line utilization is inefficient.

![[stop-and-wait.png|center]]

---
## 3. Sliding Window Flow Control

Allows **multiple frames** to be transmitted at the same time.
- Destination has a buffer of size W (window size)
- Source can send up to W frames before getting ACK
- Each frame is numbered by the **sequence number**

Much more efficient than stop-and-wait.

**Example:**

We have a window size of 4.

1. The sender sends 4 frames without waiting for ACK.
2. Upon receiving the 1st frame, receiver ACK 1st frame
3. Sender receives the ACK, then send the next frame . Effectively **sliding** the window.
4. Repeat from step 2 for the next frames. Do this until sender runs out of frames to send. 

![[sliding-window.png]]

>[!note]
>Note that in this example, the receiver is waiting for the whole window to be sent, then ACK the whole window. In actuality, the receiver only ACK after a period of time (usually every other frame). So the window slides incrementally as more frames are acknowledged. See [this video](https://youtu.be/klDhO9N01c4?si=T-TWOw7oV5r-UzlJ) for a better explanation.

This model only works for one-directional (simplex) communication. For duplex transmission, 2 sliding windows are used at each station, one to transmit one to receive.

---
## 4. Piggybacking

Piggybacking combines data frame with ACK in duplex transmission.

Saves bandwidth, less overhead.

![[piggybacking.png|center]]

---

See next:
- [[Layer 2 Error Control]]