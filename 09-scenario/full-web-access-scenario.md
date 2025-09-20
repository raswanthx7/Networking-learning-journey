# Stark Company – Full Website Access Scenario

## Topics Covered
- Employee system and NIC
- DHCP for IP assignment
- Switch & VLAN forwarding
- Router & NAT
- Security layers: DDoS, Firewall, IDS, IPS
- DNS resolution
- TCP/UDP protocols
- HTTP/HTTPS requests
- TLS/SSL encryption
- Server response and rendering
- End-to-end network flow

---

## Step 0: Employee System Ready
- John at **Stark Company** wants to access `www.example.com`.  
- His **NIC** has a unique **MAC address**.  
- NIC requests **IP from DHCP server** → receives `192.168.1.101`.  
- Employee system is now ready to communicate on the network.

---

## Step 1: Typing the Domain Name
- John types `www.example.com` in his browser.  
- Browser needs the **server IP**, so it sends a **DNS query**.  

---

## Step 2: DNS Resolution (Name → IP)
- DNS request is forwarded from John's system → **Switch → Router → Firewall/IDS/IPS → Internet**.  
- Query travels through:
  1. **Root DNS server**  
  2. **TLD server**  
  3. **Authoritative DNS server**  
- Result: IP address returned, e.g., `192.0.2.1`.  

**Protocols involved:** UDP (DNS query), ICMP (optional network diagnostics)  

---

## Step 3: Security Check (Outbound)
Employee System → Switch → Router → DDoS → Firewall → IDS → IPS → Internet

- **DDoS Protection:** Filters malicious traffic.  
- **Firewall:** Checks rules (IP, port, protocol).  
- **IDS:** Logs suspicious activity.  
- **IPS:** Blocks detected threats.  

---

## Step 4: TCP Connection (Reliable Transport)
- Browser starts **TCP 3-way handshake** with web server:
  1. **SYN:** Browser asks server to connect.  
  2. **SYN-ACK:** Server agrees.  
  3. **ACK:** Browser confirms.  

**Protocols:** TCP (reliable delivery), IP (addressing), ARP (IP → MAC for local network)  

---

## Step 5: TLS/SSL Handshake (HTTPS only)
- If HTTPS: secure connection is established.
  - Server sends **TLS certificate**.  
  - Browser verifies certificate via **Certificate Authority (CA)**.  
  - Key exchange → encrypted channel established.  

**Protocols:** TLS/SSL on top of TCP  

---

## Step 6: HTTP/HTTPS Request Sent
- Browser sends **HTTP GET request** to server for page content.  
- Data passes through same **security layers** outbound.  
- Router forwards request via Internet to external server.  

**Protocols:** HTTP/HTTPS (application layer), TCP (transport layer), IP (network layer)  

---

## Step 7: Server Processes Request
- External server (`192.0.2.1`) receives request.  
- Server generates response: HTML, CSS, JS, images.  
- Response is broken into **TCP packets** → sent back to client.  

---

## Step 8: Security Check (Inbound)
Google Server → Internet → IPS → Firewall → DDoS → Router → Switch → Employee System

- **IPS:** Detects malicious payloads.  
- **Firewall:** Ensures session validity.  
- **DDoS:** Protects against flood attacks.  

---

## Step 9: Packet Delivery to Browser
- Router/NAT → maps external IP → internal IP.  
- Switch → forwards frame to John’s NIC.  
- NIC receives Ethernet frame → sends payload to browser.  
- Browser reassembles TCP packets → decrypts TLS → displays page.  

---

## Step 10: Rendering the Web Page
- Browser parses HTML → creates DOM tree.  
- CSS applied → page styled.  
- JavaScript executed → dynamic content loaded.  
- Web page fully displayed and interactive.  

---

## Protocols Summary
| Protocol | Role |
|----------|------|
| DHCP     | Assigns IP to client NIC |
| ARP      | Maps IP → MAC for LAN |
| IP       | Addresses packets |
| TCP      | Reliable transport, packet ordering |
| UDP      | DNS queries |
| ICMP     | Ping/traceroute diagnostics |
| DNS      | Domain → IP resolution |
| HTTP/HTTPS | Web requests |
| TLS/SSL  | Encryption & secure channel |
| SSH/IPSec/VPN | Optional secure remote access |

---

## Devices & Their Role
| Device | Role |
|--------|------|
| Employee Laptop/NIC | Sends/receives packets, MAC assigned |
| Switch / VLAN | Forwards frames based on MAC, isolates VLAN |
| Router / NAT | Routes packets to external network, NAT translation |
| Firewall | Blocks unauthorized traffic, enforces rules |
| IDS | Alerts suspicious activity |
| IPS | Blocks detected attacks |
| DDoS Protection | Filters flood/malicious traffic |
| External Server | Processes requests & sends response |

---

## Simple Flow Arrows
Employee Laptop → Switch → Router → DDoS → Firewall → IDS → IPS → Internet → External Server
External Server → Internet → IPS → Firewall → DDoS → Router → Switch → Employee Laptop


---

### Final Takeaways
1. Every step ensures **addressing, security, and reliability**.  
2. Security layers protect against **malicious traffic** both ways.  
3. Protocols work **together**: DHCP → DNS → TCP/UDP → HTTP/HTTPS → TLS/SSL.  
4. Devices ensure **packet delivery**, proper routing, and network segmentation. 

---
