---
tags:
  - protocol
---
## 1. Email Client

Each device use an application called Mail User Agent (email client)
- At sender - send messages
- At receiver - put received messages in client's mailbox

---
## 2. Popular Protocols 

**Simple Mail Transfer Protocol (SMTP):** used to send emails
- SMTP processes must be running on both client and server

**Post Offices Protocol (POP):** used to retrieve emails
- Mail is downloaded from server to client, then deleted on the server
- **POP3** is an updated version, better for large storage

**Internet Message Access Protocol (IMAP):** also used to retrieve email
- Keeps original message on the server until manually deleted

---
## 3. Transferring Email

**Mail Transfer Agent (MTA):** transfer email between two devices
- Email is ***relayed*** to other MTAs if the recipient is not hosted locally

**Mail Delivery Agent (MDA):** accepts email from MTA
- Perform actual delivery
- Place inbound emails from MTA into mailbox
- Also do virus scanning, spam filtering,...