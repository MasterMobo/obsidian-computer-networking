---
tags:
  - protocol
---
## 1. Definition

Allows multiple devices to transmit on the same frequency at the same time, but with ***different codes***.

Used in mobile communication (3G).

Advantages:
- Bandwidth efficient
- No synchronization needed
- Good interference protection
Disadvantages
- Lower data rates
- Complex signal regeneration

---
## 2. How it Works

Each device is assigned a unique **chipping code** (usually 64-bit)
- To transmit a 1, device transmit the chipping code
- To transmit a 0, device transmit the ***inverse*** of the chipping code

The receiver uses the chipping code to decode the data
- If decode to +64, it is a 1
- If decode to -64, it is a 0
- If decode to something else, this data is not intended for the receiver

>[!info] Formal Look
>We have a 64-bit chipping code:
>$$
>code = <c1,c2,c3,...,c64>
>$$
>We receive a data stream
>$$
>data = <d1,d2,d3,...d64>
>$$
>We decode the data by multiplying each team of the code with the data, then add them all up
>$$
>decoded = d1.c1 + d2.c2 + ... + d64.c64
>$$
>
>If decoded = +64, we know this data is a binary 1. 
>If decoded = - 64, we know this data is a binary 0.
>If decoded is something else, this data is not for us.

The reason this works is because the chipping codes are **orthogonal**. That is, interference is detectable via the code.

