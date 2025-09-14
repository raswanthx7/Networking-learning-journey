#  Stark Company Network Scenario

## Topics Covered
- Internal Routing (RIP/OSPF)  
- Edge Router  
- ISP Connection  
- External Servers (Google, AWS, Azure)  
- How Traffic Flows  
- Redundancy with Multiple ISPs  

---

##  Internal Routing
- Inside the company, all local routers communicate with each other using **dynamic routing protocols** like **RIP** or **OSPF**.  
- Purpose: Share **internal IP addresses** and local network information.  
- Internal routers **do not connect directly** to the Internet.  

---

##  Edge Router
- The **edge router** is the single point connecting your internal network to the Internet.  
- Responsibilities:  
  1. Receive traffic from internal routers.  
  2. Forward traffic to the **ISP**.  
  3. Receive incoming traffic from the ISP and distribute it internally.  

---

##  ISP Connection
- Your edge router connects to at least **one ISP** (e.g., Airtel, Jio, Tata).  
- The ISP acts as a **gateway to the Internet**, knowing the routes to millions of external networks and servers.  
- The edge router relies on the ISP to reach servers like Google, AWS, Azure, YouTube, etc.  

---

##  External Servers (Google, AWS, Azure)
- Internal traffic does not connect to Google or AWS directly.  
- Example:  
  - Employee in Stark Company requests `aws.amazon.com`.  
  - Edge router sends the request to the connected ISP.  
  - ISP determines the best path to AWS servers using protocols like **BGP**.  
  - Data flows back through the same path to the edge router and then to the internal employee.  

---

##  How Traffic Flows (Step-by-Step)
1. **Internal Request:** Local router → Edge router.  
2. **Edge Router Forward:** Edge router → ISP.  
3. **ISP Routing:** ISP finds the destination server (Google, AWS, Azure) using **BGP / Internet routing tables**.  
4. **Server Response:** Server → ISP → Edge router → Internal router → Employee.  

---

##  Redundancy with Multiple ISPs
- For reliability, companies may connect the edge router to **multiple ISPs**.  
- Benefits:  
  - Failover if one ISP goes down.  
  - Load balancing between ISPs.  
- Principle remains the same: **edge router acts as a gateway**, and ISPs handle the external routing.  

---

##  Summary
- **Internal routers:** Only for local network, use RIP/OSPF.  
- **Edge router:** Single connection point to ISP(s), handles all traffic to/from Internet.  
- **ISP:** Gateway to external servers, knows paths to millions of networks.  
- **External servers (Google, AWS, Azure):** Reached via ISP, edge router never connects directly.  
- **Optional:** Multiple ISPs improve reliability and performance.  

---
