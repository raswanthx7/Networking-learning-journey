#  Transmission Control Protocol (TCP)

##  Topics Covered
- What is TCP?
- Why TCP is used
- 3-Way Handshake (3-shake)
- Synchronization and Sequence Numbers
- Features of TCP
- Real-Life Examples
- TCP in Cloud/Companies
- Protocols that use TCP

---

##  What is TCP?
**TCP (Transmission Control Protocol)** is a **connection-oriented protocol**.  
This means before sending data, TCP establishes a secure connection between the sender and the receiver.  

It is mainly used when **reliability and accuracy** are more important than speed.  

---

##  Why TCP is Used?
- To ensure data is **delivered safely**.  
- To maintain **correct order** of data packets.  
- To provide **error detection and correction**.  

---

##  3-Way Handshake (3-shake)
TCP uses a **3-Way Handshake** to establish a connection. This is also called the **“3-shake”** process in interviews.

1. **SYN** → Client sends a synchronization request.  
   - *Synchronization means: Before starting a conversation, both people need to be on the same page.*  
2. **SYN-ACK** → Server acknowledges and responds.  
3. **ACK** → Client confirms and connection is established.  

 After this handshake, data transfer begins.

---

##  Synchronization and Sequence Numbers

###  What is a Sequence Number?
TCP splits large data into **packets**, and each packet is assigned a **sequence number**.  
This allows the receiver to **rearrange packets in the correct order** and request retransmission if a packet is lost.  

###  Example:
If a PDF file is split into 5 packets:  
- Packet 1 → Seq 100  
- Packet 2 → Seq 200  
- Packet 3 → Seq 300  
- Packet 4 → Seq 400  
- Packet 5 → Seq 500  

Even if Packet 3 arrives before Packet 2, the receiver uses the sequence numbers to correctly reassemble the data.  

---

##  Features of TCP

###  Connection-Oriented
Before data is sent, the protocol establishes a connection and checks whether both the sender and the receiver are active and ready to communicate.  

###  Reliability
It ensures that the data successfully reaches the receiver. If any packets are lost, TCP automatically retransmits them.  

###  Accuracy
It guarantees that the correct message, without errors or corruption, is delivered to the receiver.  

###  Ordered Delivery
Packets arrive in the exact same sequence they were sent.  

###  Flow Control
TCP prevents the sender from overwhelming the receiver by adjusting the speed of data transmission.  

---

##  Real-Life Examples
- **Web Browsing (HTTP/HTTPS)** → Reliable loading of web pages.  
- **Email (SMTP, IMAP, POP3)** → Emails must be delivered completely.  
- **File Transfer (FTP, SFTP)** → Files need to be transferred without corruption.  

---

##  TCP in Cloud/Companies
- Cloud servers (like AWS EC2, Azure VMs, GCP Compute) use TCP for **secure communication**.  
- Load balancers use TCP to manage reliable client-server sessions.  
- APIs over HTTPS rely on TCP for **data integrity**.  

---

##  Protocols that use TCP
TCP is a **transport layer protocol**, but many **application layer protocols run on top of TCP** because they require reliability and accuracy.  

Examples include:  
- **HTTP / HTTPS** → For web browsing.  
- **SMTP, IMAP, POP3** → For sending and receiving emails.  
- **FTP / SFTP** → For file transfers.  
- **Telnet, SSH** → For remote login.  

 TCP itself is a protocol at the Transport Layer. Other higher-level protocols like HTTP, HTTPS, SMTP, and FTP use TCP as their transport mechanism. These protocols define the rules for communication (like requesting a webpage or sending an email), but they rely on TCP to ensure that the data is transmitted reliably, accurately, and in the correct order.  

---

 **Summary**:  
TCP is a **reliable, connection-oriented protocol** that uses the **3-Way Handshake (3-shake)** to establish communication. Synchronization ensures both sides are on the same page, and sequence numbers keep packets in order. Many higher-level protocols (HTTP, HTTPS, SMTP, FTP, SSH) rely on TCP to provide safe and reliable data transfer.

