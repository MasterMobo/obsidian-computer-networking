---
tags:
  - protocol
---
---
# 1. Purpose

UDP is a protocol in the Layer 3-[[Transport Layer]] that provides **fast** but **unreliable** data transmission.

UDP is a **best effort** service, it makes no recovery when data is lost. There is no guarantee that data will be delivered.

UDP deliver data **out-of-order**.

More simple with less overhead than TCP, therefore much faster.

UDP should be used when fast delivery is important, and sacrifices to accuracy can be made.
**Example use cases**: live streaming, video streaming, other real-time applications,...

---
## 2. UDP Datagram Format

The UDP header is much more simple than TCP, consisting of 4 main fields:
- Source port address
- Destination port address
- Total length
- Checksum