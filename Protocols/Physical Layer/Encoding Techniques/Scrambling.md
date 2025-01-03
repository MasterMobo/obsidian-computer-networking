---
tags:
  - encoding
---

# Table of Contents

- [[#1. Filling the Gaps|1. Filling the Gaps]]
- [[#2. Bipolar with 8-zeros substitution (B8ZS)|2. Bipolar with 8-zeros substitution (B8ZS)]]
- [[#3. High-density Bipolar-3 Zeros (HDB3)|3. High-density Bipolar-3 Zeros (HDB3)]]

---
## 1. Filling the Gaps

In encoding techniques like [[Digital Data to Digital Signals#2.2 Bipolar|Bipolar AMI and Pseudoternary]], Long sequences of constant voltage level might occur (e.g. for long strings of 0's). This makes it hard for end devices to sync up.

To avoid this, we replace these *constant* sequences with **special sequences** that:
- Produces enough **transitions** to ***synchronize clock***
- Has no DC component
- No long sequences of constant level
- No reduction in data rate
- Has error detection capabilities

## 2. Bipolar with 8-zeros substitution (B8ZS)

Based on Bipolar AMI

If you see a string of 8 zeros, replace it with:

| Previous Pulse | Bits to Encode |
|:--------------:|:--------------:|
|       +        |    000+-0-+    |
|       -        |    000-+0+-    |

This scheme ***intentionally violates*** AMI **twice**
1. Based on the sign of the previous pulse, the next pulse should be flipped
2. The sign after the 0 in the middle should be flipped

The idea is this pattern with these violations is unlikely to occur by noise.

The receiver can therefore detect this pattern and replace it back with 8 zeros.

## 3. High-density Bipolar-3 Zeros (HDB3) 

Based on Bipolar AMI

If you see a string of 4 zeros, replace it with:

|                | Number of 1's since last substitution |  <   |
|:--------------:|:-------------------------------------:|:----:|
| Previous Pulse |                  Odd                  | Even |
|       +        |                 000+                  | -00- |
|       -        |                 000-                  | +00+ |

Fourth zero is replaced with one ***violation***.

Has higher density than B8ZS, and therefore better synchronization. But is more complicated, and only has 1 violation, which makes it harder to differentiate from error.

![[scrambling.png]]