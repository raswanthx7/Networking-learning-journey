#  Static Routing (4-Router Example)

##  Topics Covered
- What is static routing?
- Why static routing is needed
- 4-router scenario explanation
- Router table (before & after static routing)
- Static route configuration commands
- Advantages
- Disadvantages (Limitations)
- When Static Routing is Good
- When Static Routing is Bad

---

##  What is Static Routing?
Static routing is a process where a **network administrator manually configures routes** in the routing table.  
Routers do not learn routes automatically (like in dynamic routing protocols such as RIP/OSPF).  
Instead, each path to the destination network is **manually assigned**.

---

##  Scenario (4 Routers)

We have the following network:

`System A --- R1 --- R2 --- R3 --- R4 --- System B`


- System A is in **Network 1**
- R1 ↔ R2 is **Network 2**
- R2 ↔ R3 is **Network 3**
- R3 ↔ R4 is **Network 4**
- System B is in **Network 5**

### Network Connections
- System A → R1: **Net 1 (192.168.1.0/24)**
- R1 → R2: **Net 2 (192.168.2.0/24)**
- R2 → R3: **Net 3 (192.168.3.0/24)**
- R3 → R4: **Net 4 (192.168.4.0/24)**
- R4 → System B: **Net 5 (192.168.5.0/24)**

---

##  Routing Tables

###  Before Static Routing
Each router only knows its **directly connected networks**:

- **R1 knows:** Net1, Net2  
- **R2 knows:** Net2, Net3  
- **R3 knows:** Net3, Net4  
- **R4 knows:** Net4, Net5  

 But R1 doesn’t know how to reach Net5,  
and R4 doesn’t know how to reach Net1.  

---

###  After Static Routing
We manually add static routes:

- **On R1:** Add route → Net5 via R2  
- **On R2:** Add route → Net1 via R1, Net5 via R3  
- **On R3:** Add route → Net1 via R2, Net5 via R4  
- **On R4:** Add route → Net1 via R3  

---

##  Static Route Commands

Example (Cisco style):

```bash
# On R1
ip route 192.168.5.0 255.255.255.0 192.168.2.2   # To reach Net5 via R2

# On R2
ip route 192.168.1.0 255.255.255.0 192.168.2.1   # To reach Net1 via R1
ip route 192.168.5.0 255.255.255.0 192.168.3.2   # To reach Net5 via R3

# On R3
ip route 192.168.1.0 255.255.255.0 192.168.3.1   # To reach Net1 via R2
ip route 192.168.5.0 255.255.255.0 192.168.4.2   # To reach Net5 via R4

# On R4
ip route 192.168.1.0 255.255.255.0 192.168.4.1   # To reach Net1 via R3
```

##  Advantages
1. **Simple to configure** – easy setup for small networks.  
2. **No resource overhead** – doesn’t consume CPU/RAM for routing calculations.  
3. **Secure** – no routing updates exchanged between routers.  
4. **Predictable paths** – routes are fixed and stable.  
5. **Full control** – network engineer decides the path.  

---

##  Disadvantages (Limitations)
1. **Not scalable** – difficult to manage in large networks.  
2. **Manual changes required** – admin must update routes if topology changes.  
3. **Error-prone** – human mistakes can break communication.  
4. **No automatic failover** – if a link fails, traffic is lost until manually fixed.  
5. **Time-consuming** – configuration becomes complex as the network grows.  

---

##  When Static Routing is Good
- Small networks (labs, branch offices, or point-to-point links).  
- Default route in home/office networks.  
- Secure environments (where dynamic routing is not allowed).  

---

##  When Static Routing is Bad
- Large enterprise or ISP networks.  
- Environments that need fast **convergence** (automatic rerouting).  
- Networks with **frequent topology changes**.  

---

##  Summary
- Static routing = **manual, simple, predictable**.  
- Dynamic routing = **automatic, scalable, adaptive**.

---
