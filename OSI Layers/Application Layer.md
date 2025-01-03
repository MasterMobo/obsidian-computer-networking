---
tags:
  - osi-layer
---
# Table of Contents

- [[#1. Purpose|1. Purpose]]
- [[#2. Peer-to-Peer (P2P) Network|2. Peer-to-Peer (P2P) Network]]
- [[#3. Client-Server Network|3. Client-Server Network]]
- [[#4. Hypertext Transfer Protocol (HTTP)|4. Hypertext Transfer Protocol (HTTP)]]
- [[#5. Email Protocols|5. Email Protocols]]
- [[#6. Domain Name System (DNS)|6. Domain Name System (DNS)]]
- [[#7. Dynamic Host Configuration Protocol (DHCP)|7. Dynamic Host Configuration Protocol (DHCP)]]
- [[#8. File Transfer Protocol (FTP)|8. File Transfer Protocol (FTP)]]
- [[#9. Sever Message Block (SMB)|9. Sever Message Block (SMB)]]

---
## 1. Purpose

The application layer directly interacts with the user. It provides services for end-user applications.

---
## 2. Peer-to-Peer (P2P) Network

Two or more devices (called peers) connected via a network that share resources with each other.

There is no central dedicated server. All peers are considered equal. Both can initiate communication.

P2P decentralizes the resources on the network.

---
## 3. Client-Server Network

Dedicated server stores data (files). Replies to client requests.

Users are clients that can make requests to the server.

---
## 4. Hypertext Transfer Protocol (HTTP)

Extremely popular protocol used to transfer data over the Internet. particularly HTML web pages that make up the World Wide Web.

Request/response protocol.

Several message types: GET, POST, PUT, DELETE,...

HTTPS (Hypertext Transfer Protocol Secure) is a modern version that includes encryption for better security.

---
## 5. Email Protocols

For sending: SMTP

For receiving: POP3, IMAP

For transferring: MTA, MDA

See more: [[Email Protocols]]

---
## 6. Domain Name System (DNS)

Resolve human readable Internet names (domain name) to IP addresses.

Client sends an domain name to a DNS server, which then replies back with the IP address.

DNS records are also often cached, making it faster to resolve IP addresses.

Record types:
- A - end device address
- NS - authoritative name server
- CNAME - canonical name
- MX - mail exchange record

DNS is hierarchical, going from second level, top level, to root servers.

![[dns-hierarchy.png]]

---

## 7. Dynamic Host Configuration Protocol (DHCP)

Allows dynamic IP address assignment

Client/server model. Server provide IP addresses to client.

When a host requests an IP address, server chooses from the ***address pool***  and temporarily *leases* it to the host.

Used for general purpose hosts, such as end devices (PC, smartphones,...). Static addressing is still used for network devices (routers, switches,...)

---

## 8. File Transfer Protocol (FTP)

Used for interactive file transfer between devices

FTP client running on the computer push and pull data from a server

Requires two connections: 
- One for commands and replies
- One for actual file transfer

TFTP (Trivial FTP) simple FTP implementation for connectionless active file transfer

FTPS (FTP Secure) is a modern version with encryption

---

## 9. Sever Message Block (SMB)

Network file sharing protocol.

Allow client to read/write files and request services from server.

Allow client to access resources on the server as it was available locally