# Telnet Protocol Overview

##  Topics Covered
- What is Telnet
- Key Points
- Real-World Example
- Telnet vs SSH (Quick Comparison)
- Summary


## 1. What is Telnet?
- **Definition:** Telnet is a network protocol used to connect a client machine to a remote server over a network.  
- **Purpose:** Allows access to the command line of a remote system.  
- **Default Port:** 23  
- **Security:** Not secure; sends data in plain text, including passwords.  

---

## 2. Key Points
- Used for **remote command-line access**.  
- Mostly **obsolete**, replaced by SSH for secure remote access.  
- Sometimes used for **testing connectivity or legacy devices**.  

---

## 3. Real-World Example
- To check if a mail server is reachable on port 25 (SMTP):
```bash
telnet smtp.gmail.com 25
```
- If you get a connection, the server is reachable.

---

## 4. Telnet vs SSH (Quick Comparison)

| Feature       | Telnet              | SSH                 |
|---------------|-------------------|-------------------|
| Port          | 23                 | 22                 |
| Security      | Unencrypted        | Encrypted          |
| Usage Today   | Rare / Legacy      | Modern Standard    |
| Purpose       | Remote CLI access  | Secure Remote CLI  |

---

## 5. Summary

- **Telnet** = Remote command-line access (insecure)  
- **SSH** = Secure alternative to Telnet  
- Telnet is mostly used today **for learning, testing, or old systems**

---
