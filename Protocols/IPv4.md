---
tags:
  - protocol
---
# Table of Contents

- [[#1. IPv4|1. IPv4]]
- [[#2. Subnetting|2. Subnetting]]
- [[#3. CIDR Notation|3. CIDR Notation]]
- [[#4. Classful Networks|4. Classful Networks]]
- [[#5. Classless Networks|5. Classless Networks]]
- [[#6. Private vs Public Addresses|6. Private vs Public Addresses]]

---
## 1. IPv4

**32 bit** address. Divided into four 8-bit segments (called ***octets***) separated by dots.

Since each segment is 8 bits, the value can range from 0.0.0.0 to 255.255.255.255 

>[!info] Example
>
>**IP Address**: 128.11.3.31
>In binary: 10000000 00001011 00000011 00011111

---
## 2. Subnetting

In IPv4, we can only assign $2^{32} \approx$  4 billion addresses, which is not enough. Therefore, we rely on **subnetting** to divide the address space into smaller spaces, providing more addresses, albeit with a lot of added complexity

The **subnet mask** is used to split the IP address into two parts: the network (subnet) part, and the host part.

The network part is the address of smaller subnets, and the host part is the address of individual devices.

>[!info] Example
>
>**IP Address**: 192.168.10.9
>In binary: 11000000 10101000 00001010 00001001
>
>**Subnet mask**: 255.255.255.0
>In binary: 11111111 11111111 11111110 00000000
>
>To figure out the network part of the address, we do a **bitwise AND** between the address and the subnet mask.
>
>**Network Part**: 192.168.10.0
>**Host Part**: 9


>[!tip] TL;DR
>Whatever is 1 in the subnet mask belongs to the network, the remaining part (the 0s) belongs to the host

---
## 3. CIDR Notation

**CIDR notation** is a more concise way of writing the subnet mask. The number after the slash is the number of bits for the **network part** (i.e. number of 1s of the subnet mask). 

>[!info] Example
>**CIDR Notation**: /24
>**Subnet mask**: 255.255.255.0
>
>**CIDR Notation**: /22
>**Subnet mask**: 255.255.252.0
>
>**CIDR Notation**: /27
>**Subnet mask**: 255.255.255.224

---
## 4. Classful Networks

In classful networks (mostly obsolete nowadays), IPv4 address space is divided into 5 classes based on the first octet (byte). More specifically, it is based on the **leading 4 bits**.

Classes are given alphabetical names, from biggest to smallest: A, B, C, D, and E. Only classes A, B, C are used commercially.

Class C is most commonly used in homes and ***small networks*** (with lower amount of devices). Class A is commonly used in ***big networks***, where there are many devices (e.g. Internet Provider networks)

Each class is associated with a **default subnet mask**

| Class | Leading Bits | Start Address | CIDR Notation | Subnet Mask   |
| ----- | ------------ | ------------- | ------------- | ------------- |
| A     | 0            | 0.0.0.0       | /8            | 255.0.0.0     |
| B     | 10           | 128.0.0.0     | /16           | 255.255.0.0   |
| C     | 110          | 192.0.0.0     | /24           | 255.255.255.0 |

---
## 5. Classless Networks

Instead of relying on the leading 4 bits of the address, classless networks uses **subnet masks** to divide networks. This type of network is more popular in modern times.

In **CIDR** (Classless Inter-Domain Routing), we allocate the IP address in variable-sized blocks, making it easier to grow/shrink the network as we need.

---
## 6. Private vs Public Addresses

Public IP address are discoverable for anyone on the Internet. This is also often called the front-facing IP address.

Private IP addresses are only discoverable for devices within a private network. Public routers discard packets with these addresses.

> [!info]
> [RFC1918](https://datatracker.ietf.org/doc/html/rfc1918) defines these address spaces for private network:
> - 10.0.0.0
> - 172.16.0.0
> - 192.168.0.0
>
>Which is why you might see them in a lot of examples, or even your own IP address!

**Network Address Translation (NAT)** is used to convert between private and public IP address. The IP addresses are translated when a packet goes into/out of the private network. 

NAT also provides security by hiding private addresses from the outside world.