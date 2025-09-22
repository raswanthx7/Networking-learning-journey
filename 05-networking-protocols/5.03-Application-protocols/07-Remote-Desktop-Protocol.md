#  Remote Desktop Protocol (RDP)

##  Topics Covered
1. Definition  
2. Purpose  
3. How it Works  
4. OSI Model Placement  
5. Default Port  
6. Real-World Usage  
7. Security Considerations  
8. Summary  

---

##  Definition
RDP (Remote Desktop Protocol) is a **Microsoft-developed networking protocol** that allows one computer to **remotely access and control** another computer’s desktop over a network.

---

##  Purpose
- To **see and control** a remote Windows system as if you were physically in front of it.  
- Commonly used for **system administration, troubleshooting, remote work, and server management**.

---

##  How it Works
- Your **laptop or local computer** acts as the **client**.  
- The **remote Windows machine** acts as the **server**.  
- The server must have **Remote Desktop Services running**, otherwise you cannot connect.  
- The connection is established using **TCP**, which ensures a **reliable connection**, and the **default port is 3389**.  
- Once the connection is successful, the **server sends its desktop screen updates** to your local computer in real time.  
- This allows you to **view and work on the remote Windows machine** as if you were physically sitting in front of it.  

---

##  OSI Model Placement
- **Application Layer (Layer 7)** → RDP protocol itself.  
- **Transport Layer** → Uses TCP for reliable communication.  
- **Network Layer** → Uses IP addressing to reach the remote host.  

---

##  Default Port
- **TCP 3389**

---

##  Real-World Usage
- **AWS / Cloud**: Accessing a Windows EC2 instance remotely.  
- **Corporate IT**: IT support staff fixing employee PCs from a central office.  
- **Work from Home**: Employees connecting to their office desktops securely over the internet.  

---

##  Security Considerations
- RDP allows **full remote access to the remote Windows machine (server)**.  
- Never open RDP to **0.0.0.0/0**, because this exposes your **remote server** to the **entire internet**, making it vulnerable to attacks.  
- Your **local PC (client)** is safe; the risk is only to the remote server.  
- Always restrict RDP access to **specific trusted IPs** (example: `203.45.67.89/32`).  
- Use **strong passwords + Multi-Factor Authentication (MFA)**.  
- Consider connecting through a **VPN or Bastion Host** for extra security.  
- Keep the remote Windows servers updated to prevent exploits.  

---

##  Summary
- **RDP is a networking protocol** (Port 3389, Layer 7).  
- It is used to **remotely access and control Windows desktops/servers**.  
- In AWS:  
  - **Linux EC2 → SSH (port 22)**  
  - **Windows EC2 → RDP (port 3389)**

---
