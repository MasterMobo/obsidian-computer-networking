---
tags:
  - encoding
---

# Table of Contents

- [[#1. Modulation|1. Modulation]]
- [[#2. Amplitude Shift Keying (ASK)|2. Amplitude Shift Keying (ASK)]]
- [[#3. Frequency Shift Keying (FSK)|3. Frequency Shift Keying (FSK)]]
- [[#4. Phase Shift Keying (PSK)|4. Phase Shift Keying (PSK)]]
- [[#5. Baud Rate vs Bit Rate|5. Baud Rate vs Bit Rate]]

---
## 1. Modulation

Modulations converts digital data to analog.

We modulate the source data onto a carrier signal.

## 2. Amplitude Shift Keying (ASK)

Two different ***amplitudes*** of the carrier signal represents two binary values.

Usually, one amplitude is zero.

- 1 - sine wave with frequency $f$
- 0 - constant 0 voltage

![[ask_modulated_waveform.jpg | center]]

## 3. Frequency Shift Keying (FSK)

Two different ***frequencies*** of the carrier signal represents two binary values.

- 1 - sine wave with frequency $f_1$
- 0 - sine wave with frequency $f_2$

Less susceptible to error than ASK

![[fsk_modulated_output_wave.jpg | center]]

## 4. Phase Shift Keying (PSK)

***Phase*** of carrier signal is shifted to represent data

- 1 - $A\sin(2\pi f t)$
- 0 - $A\sin(2\pi f t + \phi)$
 
![[psk-wave.jpg | center]]

## 5. Baud Rate vs Bit Rate

[Baud](http://en.wikipedia.org/wiki/Baud) is _symbols_ per second. If these symbols — the indivisible elements of your data encoding — are not bits, the baud rate will be lower than the bit rate by the factor of bits per symbol. That is, if there are 4 bits per symbol, the baud rate will be ¼ that of the bit rate.

Check out the full excellent explanation [here](https://stackoverflow.com/a/20534498)

---

See next:
- [[Analog Data to Analog Signals]]