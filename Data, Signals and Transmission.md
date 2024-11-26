---
tags:
  - encoding
---
# Table of Contents

- [[#1. Analog vs Digital Signals|1. Analog vs Digital Signals]]
	- [[#1. Analog vs Digital Signals#1.1. Terminologies|1.1. Terminologies]]
		- [[#1.1. Terminologies#Bit Rate|Bit Rate]]
		- [[#1.1. Terminologies#Throughput|Throughput]]
		- [[#1.1. Terminologies#Bandwidth|Bandwidth]]
- [[#2. Analog vs Digital Transmission|2. Analog vs Digital Transmission]]
	- [[#2. Analog vs Digital Transmission#2.1 Pros and Cons of Digital Signals|2.1 Pros and Cons of Digital Signals]]
- [[#3. From Data to Signals|3. From Data to Signals]]

---
## 1. Analog vs Digital Signals

Analog signals varies smoothly over time.

Digital signals maintains a **constant** level over a period of time, and then change to a different level.

![[analog_vs_digital_signals.jpg | center]]

### 1.1. Terminologies

#### Bit Rate
For digital signals, the duration of each bit (the ***bit interval***) is the inverse of the ***bit rate***. Measured in **bps** (bits per seconds)

#### Throughput
Rate of actual data (information) being transmitted, after taking into account overheads and errors. Therefore, it is always less than bit rate.

Some factors that affect through put include: frame overhead, delays, congestion, retransmission,...
#### Bandwidth
The range between the **lowest** and **highest** frequency for a signal.

---
## 2. Analog vs Digital Transmission

Analog transmission is done through ***amplifiers***, which strengthens the **amplitude** of the signal. Therefore, noise can be accidently amplified during transmission, reducing accuracy.

Digital transmission is done through ***repeaters***, which regenerates the signal entirely. This makes it less susceptible to noise. 

### 2.1 Pros and Cons of Digital Signals

**Pros**
- Cheaper
- Less susceptible to noise
Cons
- Greater ***attenuation***. Pulse can become rounded and smaller, leading to loss of data

![[digital-attenuation.jpg | center]]

=> Digital transmission if ***preferred*** nowadays

## 3. From Data to Signals

There are many ways we can convert data into signals. The process of mapping data bits into signal elements is called ***encoding***. We will dive deeper into some of them here:

- [[Digital Data to Digital Signals]]
- [[Analog Data to Digital Signals]]
- [[Digital Data to Analog Signals]]
- [[Analog Data to Analog Signals]]