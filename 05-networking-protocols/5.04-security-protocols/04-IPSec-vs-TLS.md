# IPSec vs SSL/TLS

## Topics Covered
- What is IPSec
- What is SSL/TLS
- Layer of operation
- Scope of encryption
- Use cases
- Key differences
- Scenario examples

---

## What is IPSec
- IPSec (Internet Protocol Security) is a **network layer protocol**.
- It **encrypts all IP packets** between two endpoints.
- Commonly used for **site-to-site VPNs** and **device-wide VPN connections**.
- Ensures **confidentiality, integrity, and authentication** of network traffic.

---

## What is SSL/TLS
- SSL (Secure Sockets Layer) and TLS (Transport Layer Security) are **transport layer protocols**.
- They **encrypt only specific TCP connections**, usually used for **browser traffic or specific apps**.
- Commonly used for **remote-access VPNs, HTTPS websites, and secure application traffic**.
- Ensures **confidentiality, integrity, and authentication** for the TCP connection.

---

## Key Differences

| Feature            | IPSec                          | SSL/TLS                     |
|-------------------|--------------------------------|-----------------------------|
| Layer              | Network Layer (Layer 3)       | Transport Layer (Layer 4)   |
| Scope              | Entire network traffic        | Specific TCP connections    |
| Typical Use        | Site-to-site VPN, device-wide | Remote-access VPN, HTTPS    |
| Encryption         | Full IP packet (headers + data)| Only TCP payload            |
| Apps Covered       | All apps automatically        | Only apps using TCP         |
| Tunnel Type        | Permanent, always-on           | Connection-based, session-specific |
| Protocol Examples  | IKEv2/IPSec, L2TP/IPSec       | OpenVPN (SSL), HTTPS        |

---

## Scenario Example

### IPSec VPN
1. Office A in Chennai wants to connect to Office B in Singapore.
2. A **site-to-site VPN tunnel** using IPSec is created.
3. All devices in Office A can securely communicate with devices in Office B.
4. File sharing, apps, emails – everything goes encrypted through the tunnel.

### SSL/TLS VPN
1. A developer in Chennai wants to access a **remote corporate application**.
2. Browser connects via **SSL/TLS VPN** (e.g., OpenVPN).
3. Only the browser traffic to that application is encrypted.
4. Other apps on the device (like WhatsApp or system updates) are not affected.

---

## Summary
- **IPSec = network-wide encryption**, ideal for connecting **entire offices or networks**.
- **SSL/TLS = connection-specific encryption**, ideal for **remote-access or browser traffic**.
- Modern VPN apps use **either IPSec or SSL/TLS** based on provider and scenario.

---
