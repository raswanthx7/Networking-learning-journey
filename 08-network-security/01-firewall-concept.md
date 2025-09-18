# Firewall Concepts

##  Topics Covered
- What is a Firewall?
- Purpose of a Firewall
- How Does a Firewall Work?
- Types of Firewalls:
  - Packet Filtering Firewall
  - Stateful Firewall (with correction note)
  - Proxy Firewall
  - Next-Generation Firewall (NGFW)
  - Web Application Firewall (WAF)
- Quick Comparison Table
- Final Summary

---

## 1. What is a Firewall?
- A **firewall** is a security system that monitors and controls **network traffic** based on predefined rules.  
- It acts as a **barrier** between a trusted internal network and an untrusted external network (like the internet).  

**Simple Example:**  
Imagine your **house gate**. The gatekeeper checks who is allowed inside and who is not.  
- Friends/family → allowed.  
- Strangers/thieves → blocked.  
The firewall does the same for **data traffic**.

---

## 2. Purpose of a Firewall
- To **protect internal systems** from unauthorized access.  
- To **filter traffic** based on IP, port, or application data.  
- To **prevent cyber attacks** (viruses, hackers, malware).  
- To **log and monitor** network activity.  

**Real-world Example:**  
- In a company, only employees can access the internal servers, outsiders are blocked.  
- In cloud (AWS, Azure, GCP), firewalls protect services from public internet threats.

---

## 3. How Does a Firewall Work?
1. **Traffic enters the firewall** (request from client).  
2. Firewall checks against **rules**:  
   - Is the **IP address** allowed?  
   - Is the **port number** open?  
   - Is the **protocol** safe?  
3. If the request matches → **allow**.  
   If it does not → **block**.  

**Analogy:** Like an airport security check:  
- Passport + ticket valid → allow.  
- Suspicious passenger → block.

---

## 4. Types of Firewalls

### 4.1 Packet Filtering Firewall
- **Definition:** Oldest and simplest firewall. Checks only **IP address, port, and protocol** of packets.  
- **How it Works:**  
  - If packet matches rule → allow.  
  - Else → drop.  
- **Weakness:** Cannot see the actual content inside the packet.  
- **Analogy:** A guard at a gate only checking **vehicle number plates** (not the people inside).  

**Example:**  
- Early Cisco routers using ACLs (Access Control Lists).  
- Linux `iptables` basic rules.  

---

### 4.2 Stateful Firewall
- **Definition:** Remembers (tracks) ongoing connections in a **state table**.  
- Stateful Firewall → Like a watchman (milkman example). If a client requests Google, the firewall records it. When Google replies, the firewall allows it without extra checks because it knows the session is already valid.
- **How it Works:**  
  - Client sends request → firewall makes entry in state table.  
  - Server sends response → firewall checks if it matches entry.  
  - If yes → allow. Else → block.  
- **Advantage:** Safer than packet filtering since it understands connections.  
- **Analogy:** A watchman **keeping a list of guests**. If you entered before, you can return without re-checking.  

**⚠️ (Important):**  
 
- ❌ “Stateful firewall allows all traffic from Google once allowed once.”  
- ✅ Correct: **Stateful Firewall only allows responses that match an existing session in the state table**.  
- Stateful firewall does not allow all traffic from Google, only replies that match the session you started.
  - If other random traffic comes from Google (not matching the session), it will be blocked.  
  
**Example:**  
- AWS **Security Groups** (stateful).  
- Cisco ASA firewalls.  

---

### 4.3 Proxy Firewall (Application-Level Firewall)
- **Definition:** Works as an **intermediary (proxy)** between client and server.  
- **How it Works:**  
  - Client sends request → firewall inspects deeply → forwards to server only if safe.  
  - Server response → firewall checks → forwards to client.  
- **Advantage:** Can filter based on content, not just IP/port.  
- **Disadvantage:** Slower, since it processes each request.  
- **Analogy:** Like a **middleman** between you and a seller, checking everything before handing it over.  

**Example:**  
- Web proxy servers like Squid.  
- Zscaler cloud proxy.  

---

### 4.4 Next-Generation Firewall (NGFW)
- **Definition:** Modern firewall that combines **stateful inspection + deep packet inspection + intrusion prevention (IPS)**.  
- **Features:**  
  - Identifies and blocks advanced attacks.  
  - Detects malware, ransomware, zero-day threats.  
  - Integrates with cloud & security policies.  
- **Analogy:** Like a **smart security system** with CCTV + facial recognition + alarm.  

**Example:**  
- Palo Alto Networks Firewall.  
- Fortinet FortiGate.  
- Check Point NGFW.  

---

### 4.5 Web Application Firewall (WAF)
- **Definition:** Protects **web applications (Layer 7)** from attacks like SQL Injection, XSS, CSRF.  
- WAF → Protects web applications. A normal firewall only blocks by IP/port, but WAF looks inside the request. If a hacker uses tricks like SQL injection, WAF detects and blocks it.
- **How it Works:**  
  - Inspects **HTTP/HTTPS traffic**.  
  - Blocks malicious requests targeting web apps.  
- **Advantage:** Protects against attacks that normal firewalls cannot detect.  
- **Analogy:** Like a **bodyguard inside the building** checking if visitors behave properly, not just at the gate.  

**Example:**  
- AWS WAF, Azure WAF, Google Cloud Armor.  
- Cloudflare WAF.  

---

## 5. Quick Comparison Table

| Firewall Type        | Layer       | Tracks State? | Main Use                | Example                  |
|----------------------|------------|---------------|-------------------------|--------------------------|
| Packet Filtering     | L3/L4      | No            | Basic IP/Port filtering | Linux iptables           |
| Stateful Firewall    | L3/L4      | Yes           | Tracks sessions         | AWS Security Groups      |
| Proxy Firewall       | L7         | N/A           | Application filtering   | Squid Proxy              |
| NGFW                 | L3-L7      | Yes           | Advanced threats        | Palo Alto, FortiGate     |
| Web App Firewall     | L7 (HTTP)  | No            | Protect web apps        | AWS WAF, Cloudflare WAF  |

---

## ✅ Final Summary
- Firewalls act as **gatekeepers** of the network.  
- Different firewalls protect at **different layers** (network vs application).  
- In real-world companies and cloud setups:  
  - **Packet Filtering/Stateful** → Used for basic traffic filtering.  
  - **Proxy Firewalls** → Used for internal security checks.  
  - **NGFW** → Used in enterprises for strong protection.  
  - **WAF** → Must for any company running **web apps**.  

---
