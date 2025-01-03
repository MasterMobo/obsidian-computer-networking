---
tags:
  - protocol
---

## 1. Definition

When the bandwidth of the medium is larger than bandwidth of signals to be transmitted, we can divide the bandwidth to accommodate many users at the same time.

Used in telephone systems

**Guard bands** are inserted in between user signals to avoid overlapping.

FDM uses analog signaling, which is susceptible to **noise**.
## 2. How it Works

At the sender, each signal is ***modulated*** (combined) with a unique **carrier signal** (usually high-frequency).  The modulated signals are combined into a **composite signal**, which is transmitted.

![[fdm-modulation.png|center]]

At the receiver, the DEMUX uses filters to separate signals. Individual signals are passed through a demodulator and finally reach the destination. 

![[fdm-demodulation.png]]

See more on modulation:
- [[Analog Data to Analog Signals]]
- [[Digital Data to Analog Signals]]