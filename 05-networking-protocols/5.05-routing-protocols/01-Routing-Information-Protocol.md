# RIP (Routing Information Protocol)

## Topics Covered  
- What is RIP  
- Hop Count (OpCount) & Basics  
- How RIP Chooses Path  
- RIP Operation  
- RIP Timers  
- Advantages of RIP  
- Limitations / Disadvantages of RIP  

---

##  What is RIP?
- RIP (Routing Information Protocol) is one of the **oldest dynamic routing protocols**.  
- It belongs to the Distance Vector category..  
- **Metric used:** Hop count.  
- Maximum hop count = **15** → any destination beyond 15 hops is considered **unreachable**.  
- RIP automatically updates routing tables without manual configuration.  
- RIP only chooses paths based on **shortest hop count**, ignoring bandwidth, delay, or reliability.  

---

##  Hop Count (OpCount) & Basics
- **Hop:** One router a packet passes through.  
- **Hop count / OpCount:** Number of routers between source and destination.  
- Example:  
`PC A → Router 1 → Router 2 → Router 3 → PC B`

Hop count = 3  
- RIP uses **hop count to choose the best path**: fewer hops = better path.  
- Maximum hop count in RIP = 15. More than 15 = unreachable.  

---

##  How RIP Chooses Path
- RIP compares **hop counts** of all available paths.  
- Path with **lowest hop count** is selected.  
- Example:  
- Path 1: 4 hops → Router1 → Router2 → Router3 → Router4 → Destination  
- Path 2: 2 hops → Router1 → Router5 → Destination  
- RIP will choose **Path 2** (2 hops) even if Path 1 has faster links.  

---

##  RIP Operation
- Each router knows **directly connected networks** only.  
- Every **30 seconds**, routers broadcast (v1) or multicast (v2) their **routing table** to neighbors.  
- Neighbors update their tables and forward updates further.  
- Example with 3 routers:  
- Router 1 knows Network 1 & 2  
- Router 2 knows Network 2 & 3  
- Router 3 knows Network 3 & 4  
- After exchanging updates, all routers eventually know all networks.  

---

##  RIP Timers
- **Update Timer:** 30 sec → interval between routing updates  
- **Invalid Timer:** 180 sec → route marked invalid if no updates received  
- **Hold-down Timer:** 180 sec → prevents flapping routes from being reinstated quickly  
- **Flush Timer:** 240 sec → route is removed if no update received  

---

##  Advantages of RIP
1. Simple to configure  
2. Automatic route updates  
3. Good for **small networks**  
4. No manual static routes needed  

---

##  Limitations / Disadvantages of RIP
1. Maximum hop count = 15 → not suitable for large networks  
2. Slow convergence → takes time to detect failures  
3. Only uses hop count → ignores speed, bandwidth, delay  
4. Periodic updates every 30 sec → extra traffic  
5. Not suitable for modern, large, or complex networks  

---
