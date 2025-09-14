# Border Gateway Protocol (BGP)

## Topics Covered
- What is BGP?
- Why BGP is Needed
- Autonomous Systems (AS)
- Types of BGP (eBGP vs iBGP)
- BGP Path Attributes
- BGP Decision Process (Best Path Selection)
- BGP Tables (RIB, Adj-RIB-In, Adj-RIB-Out)
- BGP over TCP (Port 179)
- Advantages of BGP
- Limitations of BGP

---

## What is BGP?
- BGP stands for **Border Gateway Protocol**.  
- It is the protocol that makes the **Internet work**.  
- BGP is used to exchange routing information between **Autonomous Systems (AS)**.  
- Example: Airtel (AS1), Jio (AS2), Google (AS3), Tata (AS4).  

---

## Why BGP is Needed
- Inside a company or campus → use protocols like RIP or OSPF for **internal routing**.  
- But the **Internet has millions of networks**.  
- RIP/OSPF cannot handle such a huge scale.  
- That’s why BGP is needed for **external routing** between ISPs and large organizations.  

---

## Autonomous Systems (AS)
- An **AS** is a collection of routers under a single organization/ISP.  
- Each AS has a unique number called **ASN (Autonomous System Number)**.  
- Example: Airtel → AS9498, Jio → AS55836, Google → AS15169.  

---

## Types of BGP
- **eBGP (External BGP):** Runs between different AS (e.g., Airtel ↔ Google).  
- **iBGP (Internal BGP):** Runs within the same AS (e.g., inside Airtel’s routers).  

---

## BGP Path Attributes
BGP decides the **best path** using attributes:  

1. **Weight (Cisco only)** → Highest wins. Local router setting.  
2. **Local Preference** → Highest wins. Used inside an AS.  
3. **AS-Path** → Shortest wins. Shows number of AS hops.  
4. **Origin Type** → IGP > EGP > Incomplete. Determines trust level.  
5. **MED (Multi Exit Discriminator)** → Lowest wins. Suggests preferred entry point.  
6. **eBGP vs iBGP** → eBGP preferred. External over internal routes.  
7. **IGP Metric to Next-Hop** → Shortest internal path wins.  

---

## BGP Decision Process (Best Path Selection)
Routers apply attributes in this order to select the **best path**:  
1. Weight  
2. Local Preference  
3. AS-Path  
4. Origin Type  
5. MED  
6. eBGP over iBGP  
7. Shortest IGP path to next hop  

---

## BGP Tables
BGP maintains **three main tables** to manage routing information:  

1. **RIB (Routing Information Base)**  
   - Contains the routes that are **installed in the router**.  
   - These routes are used for actual packet forwarding.  

2. **Adj-RIB-In**  
   - Stores **routes received from BGP neighbors** before policy decisions.  
   - Incoming updates from other routers go here first.  

3. **Adj-RIB-Out**  
   - Stores **routes that will be advertised to neighbors**.  
   - Outgoing updates after applying policies and filtering.  

---

## BGP over TCP (Port 179)
- BGP uses **TCP (Transmission Control Protocol)** for communication.  
- Specifically, it runs on **TCP port 179**.  
- Why TCP?  
  - Provides **reliable delivery** of routing updates.  
  - Ensures ordering, retransmission, and acknowledgment of packets.  
- In the OSI model → BGP is considered an **Application Layer protocol** since it runs *on top of TCP*.  
- Common BGP message types sent over TCP: **Open, Update, Keepalive, Notification**.  

---

## Advantages of BGP
- Scales to the **entire Internet**.  
- Supports **policy-based routing** (control which path traffic takes).  
- Stable and reliable for inter-AS communication.  

---

## Limitations of BGP
- Slower convergence than IGPs (RIP, OSPF).  
- Very complex to configure and maintain.  
- Requires more **memory and CPU** in routers.

---
