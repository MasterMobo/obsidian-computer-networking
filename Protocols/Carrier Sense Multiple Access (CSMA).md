---
tags:
  - protocol
---
# Table of Contents

- [[#1. Why CSMA?|1. Why CSMA?]]
- [[#2. Non-persistent CSMA|2. Non-persistent CSMA]]
- [[#3. 1-Persistent CSMA|3. 1-Persistent CSMA]]
- [[#4. p-Persistent CSMA|4. p-Persistent CSMA]]
- [[#5. CSMA/CD|5. CSMA/CD]]
- [[#6. CSMA/CA|6. CSMA/CA]]
	- [[#6. CSMA/CA#RTS/CTS|RTS/CTS]]

---
## 1. Why CSMA?

In Medium Access Control protocols like [[Data Link Layer#Pure ALOHA |ALOHA]], stations transmit whenever they have data. Which can lead to collision. To avoid this, we **listen before talk**. 

Stations listen to the medium. 
- If there *is* transmission going on, waits for a random amount of time. 
- If there is *no* transmission going on, transmit the data and wait for ACK

## 2. Non-persistent CSMA

1. If medium idle, then transmit
2. If medium busy, then wait a random amount of time (backoff), then repeat step 1

Capacity is wasted after end of transmission.

Non-persistent because it does not listen to the channel continuously.

![[non-persistent-csma.png|center]]

## 3. 1-Persistent CSMA

1. If medium idle, then transmit ***immediately***
2. If medium busy, ***continuously*** listens until medium becomes idle, repeat step 1.

Stations are **selfish**. High collision rate.

![[1-persistent-csma.png|center]]

---
## 4. p-Persistent CSMA

Time is divided into equal **slots**. Which typically equals twice the maximum propagation delay. 

1. Continuously listen to the medium
2. If medium busy, repeat step 1
3. If medium idle
	3.1 With probability $p$, transmit the data
	3.2 With probability $p - 1$, wait for next slot, then check the medium
	- If medium idle, go to 3.1
	- If medium busy, act as if collision occurred and backoff & start over

>[!note]
>With probability $p$ basically means flip a coin. If heads ($p$) to one thing, if tails ($p-1$) do another thing.

Overcomes collision of 1-persistent by not transmitting immediately.

Under heavy load, collision can still occur.

![[ppersitent.png|center]]

---
## 5. CSMA/CD

CSMA with **Collision Detection**

1. Listen to the medium (carrier sensing)
2. If medium busy, repeat step 1
3. If medium idle, transmit immediately
4. **After** transmission started, station monitor the transition
	- If collision detected, send a ***jamming signal*** to alert other stations about collision
	- Then, do random backoff and repeat step 1

Used in ***wired (guided)*** medium only. Not very relevant today.

---
## 6. CSMA/CA

CSMA with **Collision Avoidance**

Used in ***wireless (unguided)*** medium. Such as Wi-Fi.

Since in wireless medium, devices can't detect collision (they don't share a wire), they try to ***avoid collisions altogether***.

1. Listen to the medium for any transmission
2. If transmission detected, do random backoff, then repeat step 1
3. If no transmission detected, transmit the data, then wait for ACK
	- If ACK not receive, repeat step 1
### RTS/CTS

Request to Send/Clear to Send

Optional mechanism used to prevent collision in CSMA/CA

Wireless access point (WAP) acts as traffic controller for the network. 

1. Listen to the medium for any transmission
2. If transmission detected, do random backoff, then repeat step 1
3. If no transmission detected, transmit RTS signal to WAP 
	- If WAP says no, repeat step 1
	- If WAP says yes, it sends CTS signal back. WAP stop communication with all other devices, station is ready to transmit.
