# Stark Company – DDoS Protection  

## Topics Covered
- What is DDoS  
- Why DDoS protection is needed  
- Key DDoS protection techniques  
- Typical network flow  
- Important terms explained  

---

## 1. What is DDoS?
- **DDoS (Distributed Denial of Service)** is a type of cyberattack where attackers use **multiple compromised systems (botnets)** to send huge amounts of fake traffic to a target server, application, or network.  
- Goal: **Overwhelm the system** so real users cannot access it.  

Example:  
Imagine 1000 fake customers crowding the entrance of Stark Company office. Real employees can’t enter because the fake crowd blocks the door.  

---

## 2. Why DDoS Protection is Needed
- Firewalls, IDS, and IPS can block **malicious packets** but they **struggle when traffic volume is extremely high**.  
- DDoS protection adds an extra layer that can:  
  - Differentiate between **legitimate requests** and **malicious floods**.  
  - Ensure **business continuity** (services stay online).  
  - Protect against **reputation damage** and **financial loss**.  

---

## 3. Key DDoS Protection Techniques
- **Traffic Scrubbing**: Clean incoming traffic → remove malicious packets → forward only clean traffic.  
- **Absorption**: Use large distributed infrastructure (like cloud/CDN) to absorb massive floods.  
- **Rate Limiting (Throttling)**: Limit number of requests per second from one source.  
- **Anomaly Detection**: Detect unusual traffic spikes compared to normal behavior.  
- **Failover**: If one server is attacked, traffic automatically switches to backup server.  
- **Scaling / Auto-Scaling**: Add more servers/resources automatically when load increases.  
- **Global CDN**: Deliver content through distributed servers worldwide, reducing single point of attack.  

---

## 4. Typical Flow – Stark Company Network with DDoS Protection

### 1. Outbound (Employee → Google request)
`Employee → DDoS Protection → Firewall/IDS/IPS → External Server (Google)`

**Why DDoS first?**  
When an employee sends a request out, attackers could try to flood the company’s internet connection.  
- DDoS protection comes **first** to filter fake/bot traffic.  
- Only clean traffic is passed to Firewall/IDS/IPS.  
- This prevents bandwidth exhaustion.  


### 2. Inbound (Google → Employee response)
`External Server (Google) → Firewall/IDS/IPS → DDoS Protection → Employee`

**Why Firewall first?**  
When a reply comes back from Google:  
- Firewall/IDS/IPS **check security rules, sessions, and intrusion attempts** first.  
- After that, DDoS protection verifies if there are abnormal floods before delivering to the employee.  

### 3. Simple Logic
- **Outbound (sending requests):** Protect bandwidth first → **DDoS first**.  
- **Inbound (receiving replies):** Enforce security rules first → **Firewall first**.  

---

## 5. Important Terms
- **Malicious**: Something harmful, intended to damage (e.g., hacker traffic).  
- **Flood Traffic**: Large amount of fake requests sent to overload the system.  
- **Traffic Scrubbing**: Cleaning incoming traffic to remove bad packets.  
- **Absorption**: Handling excess traffic by spreading across large infra.  
- **Throttling**: Limiting request rate per user/IP.  
- **Anomaly Detection**: Identifying traffic patterns that don’t look normal.  
- **Failover**: Switching to backup system automatically if main system fails.  
- **Scaling**: Increasing resources manually when demand grows.  
- **Auto Scaling**: Automatically adding/removing resources based on demand.  
- **Global CDN**: Worldwide distributed servers delivering content close to users.  

---

## Final Understanding
- DDoS is about **traffic volume**, not just malicious packets.  
- Protection must **filter, absorb, and reroute** traffic before it even reaches firewall/IDS/IPS.  
- For Stark Company → DDoS protection is the **first guard**, then firewall/IDS/IPS, then internal servers.  

---

