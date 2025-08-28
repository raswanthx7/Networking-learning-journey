#  SSL & TLS Protocols

##  Topics Covered
- What is SSL
- What is TLS
- Why TLS Replaced SSL
- Security Features
- Scenario Example

---

##  What is SSL?
- **Full Form:** Secure Sockets Layer  
- **Purpose:** An older protocol used to secure communication between a **client (browser)** and a **server (web server)**.  
- **How it works:** Encrypts data so attackers cannot read it while in transit.  
- **Status:**  Deprecated (not secure anymore). SSL v2 and v3 have known vulnerabilities (e.g., POODLE attack).  

---

##  What is TLS?
- **Full Form:** Transport Layer Security  
- **Purpose:** The successor of SSL, used to secure communication between browser and server.  
- **How it works:** Provides encryption, authentication, and data integrity.  
- **Status:**  Actively used. All modern websites use TLS (even though people still say “SSL certificates”).  

---

##  Why TLS Replaced SSL
- SSL was **weak and breakable**.  
- TLS introduced:  
  - Stronger encryption algorithms  
  - More secure handshake  
  - Better authentication  
  - Forward secrecy (old data stays safe even if a key is stolen later)  
- TLS is standardized by **IETF (Internet Engineering Task Force)**.  

---

##  Security Features of SSL/TLS
1. **Encryption** – Scrambles data into secret code so nobody can read it.  
2. **Authentication** – Confirms the server is genuine (not fake or phishing).  
3. **Integrity** – Ensures data is not modified during transmission.  

---

##  Difference Between SSL and TLS

| Feature          | SSL                         | TLS                         |
|------------------|----------------------------|----------------------------|
| Security         | Weaker, vulnerable         | Stronger, modern ciphers   |
| Versions         | SSLv2, SSLv3               | TLS 1.0, 1.1, 1.2, 1.3    |
| Performance      | Slower handshake           | Faster handshake (TLS 1.3) |
| Recommendation   |  Not used anymore        |  Use TLS 1.2+            |

---

##  Scenario Example
 - You open Google Chrome and visit `https://www.youtube.com`.  
- Steps:  
  1. Browser requests IP via **DNS**.  
  2. TCP connection is established with YouTube server (3-way handshake).  
  3. Browser initiates **TLS handshake** with YouTube:  
     - Server sends TLS certificate  
     - Browser verifies authenticity  
     - Both agree on encryption and exchange session keys  
  4. Browser sends **HTTPS request** for homepage.  
  5. Server responds → Browser **renders** the page securely.  

 Result: You can watch YouTube securely, without fear of hackers stealing your data.  

---

