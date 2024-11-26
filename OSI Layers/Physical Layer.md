---
tags:
  - osi-layer
---
# Table of Contents

- [[#1. Purpose|1. Purpose]]
- [[#2. Data Communication Types|2. Data Communication Types]]
	- [[#2. Data Communication Types#2.1 Simplex|2.1 Simplex]]
	- [[#2. Data Communication Types#2.2 Half-duplex|2.2 Half-duplex]]
	- [[#2. Data Communication Types#2.3 Full-duplex|2.3 Full-duplex]]
- [[#3. Transmission Media Types|3. Transmission Media Types]]
	- [[#3. Transmission Media Types#3.1 Guided Media|3.1 Guided Media]]
		- [[#3.1 Guided Media#Twisted Pair|Twisted Pair]]
		- [[#3.1 Guided Media#Coaxial Cable|Coaxial Cable]]
		- [[#3.1 Guided Media#Optical Fiber|Optical Fiber]]
	- [[#3. Transmission Media Types#3.2 Unguided Media|3.2 Unguided Media]]
		- [[#3.2 Unguided Media#Wi-Fi|Wi-Fi]]
		- [[#3.2 Unguided Media#Bluetooth|Bluetooth]]

---
## 1. Purpose

The first layer, *closest to the metal*.

Encode/decode signals. 

Synchronization communication clock. 

Transmits/receive the **bits**.

Interface between device and transmission medium.

---
## 2. Data Communication Types

### 2.1 Simplex

Only one direction

**Ex**: FM radio, television

### 2.2 Half-duplex

Both can transmit, but ***only one at a time***

**Ex**: Walkie-talkie

### 2.3 Full-duplex

Both can transmit ***simultaneously***

**Ex**: Mobile phone

---
## 3. Transmission Media Types

### 3.1 Guided Media

Communication through a ***solid*** media (e.g. wire)

#### Twisted Pair

Two insulated coppers in a spiral pattern
- Use for both digital and analog transmission
- Relatively low bandwidth
- Cheap
- Susceptible to electromagnetic interference/hazards
- Widely used in LAN and telephone
- **Shielded Twisted Pair (STP)**: has shielding to protect against electromagnetic interference, more expensive
- **Unshielded Twisted Pair (UTP)**: More prone to electromagnetic interference, less expensive, easier to install

![[twisted-pair-cable.webp]]
#### Coaxial Cable

Has two conductors
- Wider range of frequencies. 500MHz
- Used in TV, long-distance telephone,...
 
![[coaxial_cable_jpg.jpg]]

#### Optical Fiber

Very thin cylindrical fiber that guides **optical ray**
- **Highspeed** (5Gbps), high bandwidth
- **Immune** to electromagnetic interference/hazards
- Costly, very hard to implement
- Used in wide-distance communications

![[optical-fiber.png | center]]

---
### 3.2 Unguided Media

Communication through ***wireless*** media. 

Achieved by using **antenna**.

**Transmission antenna** converts ***radio frequency*** energy into ***electromagnetic*** energy, which is radiated through the environment.

**Reception antenna** catches the ***electromagnetic*** energy from the environment, and convert it back to ***radio frequency*** energy.

***Bandwidth*** produced by the antenna is considered important.

#### Wi-Fi 

Defined in [IEEE 802.11](https://en.wikipedia.org/wiki/IEEE_802.11) . Also commonly referred to as **WLAN**.

Uses [[Carrier Sense Multiple Access (CSMA)#6. CSMA/CA|CSMA/CA]]

#### Bluetooth

Defined in [IEEE 802.15](https://en.wikipedia.org/wiki/IEEE_802.15). Referred to as **WPAN**.

Speeds up to 24 Mbps.

Targets **unlicensed ISM band**, 2.4 GHz 

Employs ***frequency hopping*** transceiver to avoid interference and fading.

---

See next:
- [[Network Topology]]
- [[Data Link Layer]]