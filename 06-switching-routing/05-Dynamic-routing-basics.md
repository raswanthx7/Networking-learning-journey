#  Dynamic Routing

##  Topics Covered – Dynamic Routing

- What is Dynamic Routing?  
- Key Features of Dynamic Routing  
- Types of Dynamic Routing Protocols    
- Example: RIP working  
- Advantages of Dynamic Routing  
- Disadvantages of Dynamic Routing  
- Static vs Dynamic Routing (Comparison)  
- Summary & Real-world usage  

---

##  What is Dynamic Routing?
Dynamic routing is when routers **automatically learn and update routes** using routing protocols.  
- Routers exchange information with each other.  
- The routing table updates itself.  
- If a link fails, routers **recalculate the best path** automatically.  

 Unlike static routing (manual), dynamic routing is **automatic and adaptive**.  

---

##  Key Features
- **Automatic route learning** (no manual entries needed).  
- **Adaptability** to network changes.  
- **Best path selection** using metrics (hop count, bandwidth, cost, delay).  
- **Scalable** for medium to large networks.  

---

##  Types of Dynamic Routing Protocols

1. **Distance Vector Protocols**  
   - Share routes as “distance + direction.”  
   - Metric: hop count.  
   - Example: **RIP (Routing Information Protocol)**  

2. **Link State Protocols**  
   - Each router knows the full network map.  
   - Metric: cost, bandwidth, delay.  
   - Example: **OSPF (Open Shortest Path First)**, IS-IS  

3. **Path Vector Protocols**  
   - Used for Internet-scale routing.  
   - Example: **BGP (Border Gateway Protocol)**  

---

##  Example: RIP
- RIP shares routing tables with neighbors every 30 seconds.  
- Uses **hop count** (max = 15 hops).  
- Updates happen automatically → no need for manual changes.  

---

##  Advantages
1. **Scalable** – good for big networks.  
2. **Automatic updates** – less admin work.  
3. **Fault-tolerant** – reroutes traffic if a link fails.  
4. **Efficient** – always tries to use the best path.  

---

##  Disadvantages
1. **Consumes resources** – uses CPU, memory, and bandwidth.  
2. **More complex** than static routing.  
3. **Slower** in very small networks (overhead not worth it).  
4. **Security risks** – routing updates can be manipulated if not secured.  

---

##  Static vs Dynamic Routing

| Feature                | Static Routing  | Dynamic Routing  |
|-------------------------|------------------|-------------------|
| Configuration           | Manual by admin  | Automatic (protocols) |
| Scalability             | Small networks   | Medium & large networks |
| Adaptability            | No (fixed path)  | Yes (auto recalculates) |
| Resource Usage          | None             | Uses CPU, memory, bandwidth |
| Failover                | Manual fix needed| Automatic failover |
| Complexity              | Simple           | More complex |

---

##  Summary
- Static routing = **manual, simple, predictable**.  
- Dynamic routing = **automatic, scalable, adaptive**.  
- In real networks, both can be used together (static for defaults, dynamic for large routing).

---

