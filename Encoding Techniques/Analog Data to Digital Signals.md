---
tags:
  - encoding
---

# Table of Contents

- [[#1. Digitization|1. Digitization]]
- [[#2. Pulse Code Modulation (PCM)|2. Pulse Code Modulation (PCM)]]
	- [[#2. Pulse Code Modulation (PCM)#2.1 Sampling|2.1 Sampling]]
	- [[#2. Pulse Code Modulation (PCM)#2.2 Quantization|2.2 Quantization]]
	- [[#2. Pulse Code Modulation (PCM)#2.3 Encoding|2.3 Encoding]]
	- [[#2. Pulse Code Modulation (PCM)#2.4 Improving the Quality|2.4 Improving the Quality]]

---
## 1. Digitization

Before transmitting analog data, we need to convert it to digital data, then transmit over [[Digital Data to Digital Signals|digital signal]].

We do this because:
- Repeaters are better than amplifiers
- Allow use of more efficient digital switching techniques 

## 2. Pulse Code Modulation (PCM)

PCM encodes analog signal into binary through 3 steps:

### 2.1 Sampling

Take samples of amplitude of analog signal. The frequency of taking the samples is referred to as the ***sample rate***.

According to the [Sampling Theorem](https://en.wikipedia.org/wiki/Nyquist%E2%80%93Shannon_sampling_theorem), the sample rate should be ***twice*** the highest frequency of the signal.

$$
f_{sample} = 2f_{max}
$$

![[analog_sampling.png]]
### 2.2 Quantization

Map the samples to the closest $2^n$ representation

This step takes the infinite value range of the amplitude and map it to a finite set of known values. This set is referred to as the ***quantization level***s.

The higher the quantization level, the more bits we need to represent it. The number of bits needed to represent the highest quantization level is called the ***bit depth***.

More quantization levels means you can map the samples more accurately.

![[quantization.jpg | center]]
### 2.3 Encoding

Finally, convert the message into binary.

Each n-bit value from the quantization is fitted into the time slot for that message.

![[pcm.png]]

### 2.4 Improving the Quality

To improve the quality of the encoded signal, we can:

- Increase the number of quantization levels (bit depth)
- Increase the sample rate

**Downsides**
	- Lead to increased bit rate. 
	- More data to transfer and store.
	- Higher hardware requirements.
	- Can also introduce noise.
	- Computational overhead.
	- Diminishing return.

---
See next:
- [[Digital Data to Analog Signals]]