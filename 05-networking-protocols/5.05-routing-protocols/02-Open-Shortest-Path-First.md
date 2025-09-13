#  OSPF (Open Shortest Path First)

---

##  Topics Covered
- What is OSPF   
- OSPF metric (cost) & reference vs link bandwidth  
- Three main OSPF steps (Neighbor, Database Exchange, SPF)  
- Router ID (what is sent in Hello)  
- OSPF packet types / DB exchange flow (Hello, DBD, LSR, LSU, LSAck)  
- SPF (Dijkstra’s Algorithm) explanation & proof   
- Advantages & Disadvantages

---

##  What is OSPF?
OSPF is a **link-state routing protocol** designed for medium-to-large IP networks.  
Each OSPF router builds a full map of the network (link-state database) and runs the SPF (Dijkstra) algorithm to find the best paths.

---

##  OSPF Metric (Cost)
- **Cost = Reference Bandwidth / Link Bandwidth**  
- Default **Reference Bandwidth** = 100 Mbps (can be changed)  
- **Link Bandwidth** = actual interface speed (e.g., 1.544 Mbps, 10 Mbps, 100 Mbps, 1000 Mbps)  
- Example:
  - FastEthernet (100 Mbps): `cost = 100 / 100 = 1`  
  - Ethernet (10 Mbps): `cost = 100 / 10 = 10`  
  - Serial (1.544 Mbps): `cost ≈ 100 / 1.544 ≈ 64`  
- OSPF chooses the path with **lowest total cost** (not hop count).

---

##  The 3 Main OSPF Steps
1. **Become Neighbors**  
   - Routers discover each other using **Hello** packets.  
   - Hello contains the **Router ID (RID)**, Hello interval, area ID, authentication info, etc.  
   - If parameters match and authentication succeeds → routers form an adjacency.

2. **Exchange Database Information**  
   - Routers exchange **Database Description (DBD)** packets to describe their LSDB.  
   - If one router needs missing info → it sends **Link-State Request (LSR)**.  
   - The other router replies with **Link-State Update (LSU)** (contains LSAs).  
   - Receiver sends **Link-State Acknowledgment (LSAck)**.  
   - After this exchange, both routers have synchronized LSDBs for that area.

3. **Choose Best Routes (SPF)**  
   - Each router uses the **link cost formula** to assign weights to all links.  
    
     `Link Cost = Reference Bandwidth / Link Bandwidth`
    
   - Default Reference Bandwidth = **100 Mbps**.  
   - Example link bandwidths:  
     - Serial: 1.544 Mbps  
     - Ethernet: 10 Mbps  
     - Fast Ethernet: 100 Mbps 

   - Then it runs **Dijkstra’s SPF algorithm** on the LSDB.  
   - SPF calculates the **Shortest Path Tree (SPT)** from the router to all networks.  
   - Best routes are installed in the routing table for packet forwarding.

---

##  Router ID (RID)
- 32-bit value (like an IPv4 address) that uniquely identifies a router in OSPF.  
- Selection order:
  1. Manually configured RID (highest priority)  
  2. Highest loopback IP (if present)  
  3. Highest active interface IP (if no loopbacks)  
- The RID is sent inside the **Hello** packet during neighbor formation.

---

##  SPF (Dijkstra’s Algorithm in OSPF)
- **SPF = Shortest Path First** algorithm.  
- Each OSPF router runs SPF **inside itself** (not in a computer).  
- SPF uses the LSDB to calculate the **Shortest Path Tree (SPT)** with the router as the root.  
- The result = best, loop-free routes installed into the **Routing Table**.  

**Example**
-Imagine 4 routers: A, B, C, D
- Costs:
   - A → B = 2
   - A → C = 5
   - B → C = 1
   - B → D = 3
   - C → D = 2
SPF Calculation (Root = A):
- Start: A = 0, B = ∞, C = ∞, D = ∞
- Step 1: Pick A (0). Update neighbors:

   - B = 2, C = 5
- Step 2: Pick B (2). Update neighbors:
   - C = min(5, 2+1=3) → C = 3
   - D = 2+3=5
- Step 3: Pick C (3). Update neighbors:
   - D = min(5, 3+2=5) → stays 5 
- Step 4: Pick D (5). Done.
Result:
- **Shortest paths from A:**
   - A → B = 2
   - A → B → C = 3
   - A → B → D = 5

**How it works in OSPF:**  
1. Router collects LSAs from neighbors.  
2. Builds a full **map of the network (LSDB)**.  
3. Runs **Dijkstra’s SPF** to find lowest-cost paths.  
4. Installs those best paths into its routing table.

---

##  Proof: How SPF Fits into OSPF
1. **Hello Exchange** → Routers discover neighbors.  
2. **Database Sync (LSAs)** → Routers share link information.  
3. **LSDB Built** → All routers now have the same network map.  
4. **SPF Algorithm Runs** → Each router calculates the shortest paths locally.  
5. **Routing Table Updated** → Best routes installed and used for packet forwarding.

---

##  OSPF Packet / DB Exchange Flow (Summary)
- **Hello** → Discover & form neighbor  
- **DBD (Database Description)** → Describe LSDB contents  
- **LSR (Link-State Request)** → Request missing LSAs  
- **LSU (Link-State Update)** → Send LSAs (actual link info)  
- **LSAck** → Acknowledge receipt  


---

##  Advantages
- Fast convergence  
- Bandwidth-aware (chooses high-capacity links)  
- Scalable with areas (reduces LSDB size & processing)  
- Supports VLSM/CIDR and complex topologies

##  Disadvantages
- More complex to configure than distance-vector protocols  
- Uses more CPU and memory (keeps LSDB, runs SPF)  
- Needs careful area and design planning in very large networks

---



