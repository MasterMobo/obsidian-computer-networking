---
tags:
  - protocol
---
## 1. Definition

Transmission is divided into fixed **time slot** (even if there's no data)

Each connection occupies a portion of time in the transmission link.

Each connection can use the **entire capacity** when it's their turn.

Used in digital and telephone communications.

---
## 2. Synchronous TDM

Uses the ***synchronizing pulse*** (framing bit) to differentiate between frames for synchronization purposes. 

In TDM, the data rate of the link is **n times faster**, and the unit duration is **n times shorter**. (n is the number of signals)

![[tdm-example.png]]

The framing bit is added to the beginning of each frame
- Allow DEMUX to synchronize with incoming stream
- Sort and direct received data to appropriate output channel

![[tdm-framing-bit.png]]

>[!info]
>In the [T-carrier System](https://en.wikipedia.org/wiki/T-carrier), 24 signals are combined to make a T-1 carrier stream.
>
>For example, to multiplex 24 8-bit signals, each frame consists of all the signal bits plus an additional framing bit.
>$$
>\text{Bits per frame} = 1 + 8.24 = 193
>$$
>If we can transmit 8000 frames per second, we get a bit rate of:
>$$
>\text{Bit rate} = 8000.193 = 1.544\text{ Mbps}
>$$
>
>![[t-1-frame.png]]
>
>T-1 frames are further to multiplexed to T-2, then T-2 is multiplexed to T-3 and so on, creating a hierarchy.
>
>![[t-carrier-hierarchy.png]]

---
## 3. Asynchronous TDM

Synchronous TDM can lead to wasted link capacity (e.g. when a station is not transmitting). Asynchronous TDM helps avoid this waste.

Allow multiple low-speed lines to be multiplex into a single higher speed line.

>[!info]
>Digital Subscriber Line (DSL) allows simultaneous **voice** and **data** service using conventional ***telephone line***. It splits signals into voice stream and data stream.
>
>Asymmetric Digital Subscriber Line (ADSL) provide high speed digital data communication over traditional telephone lines.

---
## 4. Statistical TDM

Dynamically allocate timeslots based on demand

Needs addresses to identify data

More efficient use of bandwidth, but may cause problem during peak periods (due to additional data overhead).