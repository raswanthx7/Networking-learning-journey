#  Full Scenario: Accessing a Website

##  Topics Covered
- DNS Resolution
- TCP Connection
- HTTP/HTTPS Requests
- TLS/SSL Security
- Rendering Web Page

---

##  Step 1: Typing the Domain Name
- You open your browser and type `www.example.com`.  
- This initiates the process to access the website.

---

##  Step 2: DNS Resolution
- **DNS (Domain Name System)** translates the domain name into an IP address.  
- Example: `www.example.com → 192.0.2.1`  
- The query goes through:  
  1. **Root DNS server**  
  2. **TLD (Top-Level Domain) server**  
  3. **Authoritative DNS server**  
- Result: Your browser knows the **server IP address**.  

---

##  Step 3: TCP Connection
- **Why TCP is needed:**  
  1. Ensures a **reliable connection** between browser and server.  
  2. Guarantees **all data packets arrive in order**.  
  3. Detects **lost packets** and requests retransmission.  

- **How it works (3-way handshake):**  
  1. **SYN** → Browser asks server to connect.  
  2. **SYN-ACK** → Server agrees.  
  3. **ACK** → Browser confirms.  

- Once the handshake is complete, the **TCP connection is established**, ready for HTTP/HTTPS requests.  

---

##  Step 4: HTTPS / HTTP Request
- Browser sends a **request to the web server** using HTTP or HTTPS.  
- **HTTPS** adds a security layer using **TLS/SSL**.  
- Steps:  
  1. Server sends its **TLS certificate**.  
  2. Browser verifies the certificate with a **Certificate Authority (CA)**.  
  3. Browser and server perform **TLS handshake**:  
     - Agree on encryption method  
     - Exchange keys  
  4. Encrypted communication begins.  

---

##  Step 5: Server Response
- Server sends the requested **webpage data** (HTML, CSS, JS, images).  
- Browser receives all packets in order through TCP.  

---

##  Step 6: Rendering the Page
- Browser **renders** the webpage:  
  - Converts HTML to visible content.  
  - Applies CSS styling.  
  - Executes JavaScript for dynamic content.  

---

##  Summary
1. Browser types domain → DNS resolves IP.  
2. TCP establishes a **reliable connection**.  
3. HTTP/HTTPS requests are sent to the server.  
4. TLS/SSL ensures **encryption, authentication, integrity**.  
5. Server responds → Browser renders the webpage.  

Now the website is fully loaded and secure for interaction.  

