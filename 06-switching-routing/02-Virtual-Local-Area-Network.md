# VLAN (Virtual Local Area Network)

##  Topics Covered
- What is VLAN?
- Why VLAN is used?
- Access Port vs Trunk Port
- VLAN Tagging
- Native VLAN & Default VLAN
- Real-world Example (HR & Developer Teams)
- VLAN Port Mapping Table (Example)
- ASCII Diagram of VLAN Example (with diagram explanation)
- Quick summary

---

##  What is VLAN?
- VLAN = Virtual Local Area Network.  
- It allows you to **logically separate a network into groups**, even if devices are connected to the same physical switch.  
- Example: In a company, HR team and Developer team can be separated using VLANs.

---

##  Why VLAN is used?
1. **Segmentation** – Separate different departments (HR, Dev, Finance).  
2. **Security** – Traffic of one team is isolated from another.  
3. **Reduce Broadcasts** – Broadcasts stay inside their VLAN, not disturbing others.  
4. **Better Network Management** – Logical grouping instead of depending only on physical switch.  

---

##  Access Port vs Trunk Port
- **Access Port**
  - Connected to **end devices** (PCs, printers, servers).  
  - Carries traffic of **only one VLAN**.  
  - Example: HR PC → Access Port (VLAN 20).  

- **Trunk Port**
  - Connects **switch-to-switch**.  
  - Carries traffic of **multiple VLANs** using **tags**.  
  - Example: Switch 1 to Switch 2 → Trunk Port.  

---

##  VLAN Tagging
- When data moves between switches, a **VLAN ID (tag)** is added inside the Ethernet frame.  
- This tells the receiving switch → “This packet belongs to VLAN 10 (Dev) or VLAN 20 (HR).”  
- If **no tag** is present → the traffic is placed into **Native VLAN**.

---

##  Default VLAN vs Native VLAN

### **Default VLAN**
- By default, **all switch ports belong to VLAN 1**.  
- If you don’t configure anything → all devices are in VLAN 1.  
- Example: HR PC and Dev PC connected without VLAN setup → both fall into VLAN 1.  

### **Native VLAN**
- Related only to **trunk ports**.  
- If a frame is received **without a VLAN tag** → it is assumed to belong to the **Native VLAN**.  
- Default Native VLAN = VLAN 1.  

 **Difference in one line**:  
- **Default VLAN** = all switch ports are in VLAN 1 initially.  
- **Native VLAN** = untagged frames on a trunk port are placed into VLAN 1 (by default).


---

##  Real-world Example (HR & Dev Teams)
- Company has 4 people:  
  - Switch 1 → HR + Dev  
  - Switch 2 → HR + Dev  

- VLAN Assignment:  
  - Developer Team → VLAN 10  
  - HR Team → VLAN 20  

- Case:
  - Developer in Switch 1 wants to send a broadcast.  
  - Instead of reaching all 4 users, VLAN tagging ensures → only Developers in VLAN 10 get the message.  
  - If Switch 1 doesn’t find another Dev in VLAN 10 → it forwards the frame via **Trunk Port** to Switch 2.  
  - Switch 2 delivers it to the correct Developer (VLAN 10).  

- If a device is not assigned to any VLAN → it falls into **Default VLAN (1)**.  
- If an untagged frame passes through a trunk → it is placed into **Native VLAN (1)**.  

### Example to connect to story:
- If you don’t assign VLAN IDs to HR and Dev → all their ports stay in default VLAN 1.

- If a trunk port is used between switches, and a frame arrives without VLAN tag, it is placed in native VLAN (also VLAN 1 by default).

---

##  VLAN Port Mapping Table (Example)

| Switch | Port   | User         | VLAN ID | Port Mode |
|--------|--------|--------------|---------|-----------|
| SW1    | Gi0/1  | HR (User A)  | VLAN 20 | Access    |
| SW1    | Gi0/2  | Dev (User B) | VLAN 10 | Access    |
| SW1    | Gi0/24 | To SW2       | Trunk   | Trunk     |
| SW2    | Gi0/1  | HR (User C)  | VLAN 20 | Access    |
| SW2    | Gi0/2  | Dev (User D) | VLAN 10 | Access    |
| SW2    | Gi0/24 | To SW1       | Trunk   | Trunk     |


---

##  ASCII Diagram of VLAN Example

```swift
      [ HR-PC ]                 [ HR-PC ]
         |                          |
    Gi0/1 (VLAN 20)            Gi0/1 (VLAN 20)
         |                          |
    +----------+   Trunk Link   +----------+
    |          |================|          |
    |   SW1    | Gi0/24   Gi0/24|   SW2    |
    |          |================|          |
    +----------+                +----------+
         |                          |
    Gi0/2 (VLAN 10)            Gi0/2 (VLAN 10)
         |                          |
    [ Dev-PC ]                 [ Dev-PC ]
```   

### Understanding the Port Names (Gi0/1, Gi0/2, Gi0/24)

- **Gi** → Stands for **Gigabit Ethernet**.  
  - Modern switches usually have **Gigabit (1 Gbps)** or **10-Gigabit** ports.  
  - Old switches had **Fast Ethernet (Fa)** for 100 Mbps speed.

- **0/1, 0/2, 0/24** → These are **port numbers** on the switch.  
  - `Gi0/1` → First Gigabit port on the switch.  
  - `Gi0/2` → Second Gigabit port on the switch.  
  - `Gi0/24` → 24th Gigabit port on the switch.

**In most switches:**
- **Ports 1–23** → Used to connect **end devices** (PCs, laptops, servers).  
- **Last port (like Gi0/24)** → Often used as an **uplink or trunk** to connect to **another switch** or **router**.  

 That’s why in the diagram we use **Gi0/1 & Gi0/2 for HR/Dev PCs** and **Gi0/24 for trunk connection**.

### Diagram Explanation

**Step 1 – Teams on Two Switches**
- **Switch 1 (SW1):**
  - HR-PC is on **Gi0/1 → VLAN 20**.  
  - Dev-PC is on **Gi0/2 → VLAN 10**.  
- **Switch 2 (SW2):**
  - HR-PC is on **Gi0/1 → VLAN 20**.  
  - Dev-PC is on **Gi0/2 → VLAN 10**.  

 HR = VLAN 20, Developer = VLAN 10.

**Step 2 – The Trunk Link**
- Both switches are connected with **Gi0/24 ↔ Gi0/24**.  
- This is a **Trunk Port**.  
- **Trunk Port** can carry **multiple VLANs** by attaching a **VLAN tag** inside the Ethernet frame.  

 So both **VLAN 10 (Dev)** and **VLAN 20 (HR)** traffic can travel between switches.

**Step 3 – Communication Inside VLANs**
- **Dev-PC on SW1** sends a message (broadcast).  
  - SW1 checks VLAN = 10.  
  - No other VLAN 10 members on SW1 → forward through **Trunk (Gi0/24)**.  
  - SW2 receives VLAN 10 tagged frame → delivers only to **Dev-PC on SW2**.  

 Devs talk only to Devs.  

- Same for HR (VLAN 20). HR traffic only goes to HR-PCs.  

**Step 4 – Isolation and Security**
- HR and Dev teams are **separated** into different VLANs.  
- Even though all devices are connected to the **same physical switches**, logically they are **different networks**.  
- This prevents unnecessary broadcasts and increases security.  

 That’s the **power of VLANs**: clear separation and control.

 Now, when you see the diagram and port numbers (Gi0/1, Gi0/2, Gi0/24), you’ll immediately connect them with:  
**Access ports = PCs, Trunk port = Switch-to-Switch communication carrying VLAN tags.**

---

## Quick Summary
- VLAN = Logical separation of network.  
- Access Port = Carries single VLAN.  
- Trunk Port = Carries multiple VLANs with tags.  
- Default VLAN = VLAN 1 (all ports belong by default).  
- Native VLAN = For untagged frames on trunk ports (default = VLAN 1).  

---

## Interview Note:
"A VLAN is used to logically separate networks at Layer 2. It reduces broadcast traffic, improves security, and simplifies network management. In cloud environments like AWS, VLAN concepts are similar to Subnets in a VPC, where isolation and segmentation are key for designing secure architectures."

---
