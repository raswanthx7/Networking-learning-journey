# Email Protocols Overview

##  Topics Covered
- SMTP (Simple Mail Transfer Protocol)
- POP3 (Post Office Protocol v3)
- IMAP (Internet Message Access Protocol)
- Quick Summary


## 1. SMTP (Simple Mail Transfer Protocol)
- **Purpose:** Used for sending emails.
- **Direction:** Outgoing (Client → Server or Server → Server).
- **Ports:**
  - 25 (default, often blocked to prevent spam)
  - 587 (secure submission)
  - 465 (legacy SSL)
- **Example:**  
  When you click **Send** in Gmail or Outlook, SMTP delivers the email to the mail server or recipient’s server.

---

## 2. POP3 (Post Office Protocol v3)
- **Purpose:** Used for downloading (fetching) emails from the server to the client.
- **Direction:** Incoming (Server → Client).
- **Ports:**
  - 110 (default)
  - 995 (secure SSL/TLS)
- **Key Behavior:**  
  - Downloads emails to your device.  
  - Usually removes them from the server (unless "Keep copy on server" is enabled).  
- **Example:**  
  Old-style Outlook or Thunderbird setup where emails are stored locally on one computer.

---

## 3. IMAP (Internet Message Access Protocol)
- **Purpose:** Used for synchronizing emails between the server and multiple devices.
- **Direction:** Two-way (Server ↔ Client).
- **Ports:**
  - 143 (default)
  - 993 (secure SSL/TLS)
- **Key Behavior:**  
  - Keeps emails on the server.  
  - Synchronizes actions across devices (read, unread, delete, move, etc.).  
- **Example:**  
  If you read a mail on your phone, it will also show as read on your laptop and webmail.

---

##  Quick Summary
- **SMTP = Send mail**
- **POP3 = Download mail**
- **IMAP = Synchronize mail**

