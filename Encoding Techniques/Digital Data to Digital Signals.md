---
tags:
  - encoding
---

# Table of Contents

- [[#1. Terminologies|1. Terminologies]]
- [[#2. Digital Encoding Schemes|2. Digital Encoding Schemes]]
	- [[#2. Digital Encoding Schemes#2.1 Unipolar|2.1 Unipolar]]
		- [[#2.1 Unipolar#NRZ-L|NRZ-L]]
		- [[#2.1 Unipolar#NRZ-I|NRZ-I]]
	- [[#2. Digital Encoding Schemes#2.2 Bipolar|2.2 Bipolar]]
		- [[#2.2 Bipolar#Bipolar AMI|Bipolar AMI]]
		- [[#2.2 Bipolar#Pseudoternary|Pseudoternary]]
	- [[#2. Digital Encoding Schemes#2.3 Manchester Encoding|2.3 Manchester Encoding]]
	- [[#2. Digital Encoding Schemes#2.4 Differential Manchester|2.4 Differential Manchester]]


---
## 1. Terminologies 

**Signal Element (Pulse)**: The result of encoding a single data bit.   

**Unipolar**: All signal elements have the same sign. All positive, or all negative.

**Polar**: One bit state is represented by a positive voltage, the other by negative voltage.

**Modulation**: Combining ***basehand*** (original) signal with ***carrier*** signal (usually high frequency) to create analog signals

---
## 2. Digital Encoding Schemes

### 2.1 Unipolar

#### NRZ-L

Non-Return-to-Zero-Level
- 0 - ***high*** level
- 1 - ***low*** level
####  NRZ-I

Non-Return-to-Zero-Inverted
- 0 - ***No transition*** at beginning of interval
- 1 - ***Transition*** at beginning of interval


![[nzr.jpg | center]]

**Pros**
- Both are extremely easy to implement
**Cons**
- No self synchronization
- No error detection

---
### 2.2 Bipolar
#### Bipolar AMI

Bipolar alternate mark inversion
- Uses 3 voltage level
- 0 - no line signal
- 1 - either positive or negative pulse
	- ***Alternate*** the sign whenever you see a 1

#### Pseudoternary

Same thing with Bipolar AMI but replace 0's with 1's
- Uses 3 voltage level
- 1 - no line signal
- 0 - either positive or negative pulse
	- ***Alternate*** the sign whenever you see a 0

![[ami-pseudoternary.jpg | center]]

**Pros**
- No loss of synchronization for long strings of 1's (for Bipolar AMI, the issue is still the same with Pseudoternary, albeit with 0's)
- No net DC component (+ and - cancels out) -> Lower bandwidth than NZR
- Better error detection
**Cons**
- Long strings of 0's are still not synchronized
- Not as efficient as NRZ
	- Each signal element represent only 1 bit
	- Receiver needs to distinguish 3 levels

To fix the issue with long strings of 0's, we use [[Scrambling]].

---
### 2.3 Manchester Encoding

Always a transition in **middle** of each bit period
- 1 - transition from ***low to high***
- 0 - transition from ***high to low***

The transitions act as both ***data*** and ***clock***

>[!info]
>This scheme is used by **[IEEE 802.3](https://en.wikipedia.org/wiki/IEEE_802.3)** for **Ethernet**

### 2.4 Differential Manchester

Always a transition in **middle** of each bit period. Look at ***start*** of bit period to figure out 1 and 0.
- 1 - ***No transition*** at start of bit period
- 0 - ***Transition*** at start of bit period

>[!info]
>This scheme is used by **IEEE 802.5** for the **[Token Ring](https://en.wikipedia.org/wiki/Token_Ring)**

![[manchester-encoding.jpg | center]]

**Pros**
- Self synchronization (at mid-bit transitions)
- No net DC component
- Error detection (by absence of expected transitions)
**Cons**
- Lots of transitions. At least one per pit time, possibly two.
- Requires more bandwidth

---
See next:
- [[Analog Data to Digital Signals]]