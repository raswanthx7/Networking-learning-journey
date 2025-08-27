#  ARP Protocol (Address Resolution Protocol)

##  Topics Covered
- What is ARP
- ARP Scenario Explanation
- Correct Step-by-Step Flow
- ARP Cache
- Summary

---

##  What is ARP?
- **Full Form:** Address Resolution Protocol  
- **Purpose:** To map an **IP address** to its corresponding **MAC address** in a local network (LAN).  
- Without ARP, devices cannot send data at the link layer.  

---

##  ARP Scenario Explanation

### Scenario:
- Person 1 wants to send a message to Person 2.  
- Both are connected to the Internet via a **router**.  
- Each device has:
  - **Unique IP address** (logical identity)
  - **Unique MAC address** (physical identity)  
- Router also has its own **public IP** and **MAC address**.

---

##  Correct Step-by-Step Flow

1. **Person 1 knows Person 2’s IP address.**  
   - First, Person 1 checks if Person 2 is in the **same subnet**.  

2. **Case 1: Same subnet (LAN)**
   - Person 1 directly sends an **ARP Request**:  
     > “Who has IP = Person 2’s IP?”  
   - Person 2 replies with his **MAC address**.  
   - Person 1 saves this mapping in the **ARP cache**.  
   - Person 1 sends the data directly to **Person 2’s MAC address**.

3. **Case 2: Different subnet (via Router)**  
   - Person 1 cannot directly ARP Person 2.  
   - Instead, Person 1 ARPs for the **Router’s MAC address**.  
   - Router replies with its MAC → Person 1 stores it in **ARP cache**.  
   - Person 1 sends the packet to **Router’s MAC**.  

4. **Router’s role:**  
   - Router checks the destination IP (Person 2).  
   - If Router doesn’t know Person 2’s MAC → it sends an **ARP Request** in its own subnet.  
   - Person 2 replies with his **MAC** → Router saves it in ARP cache.  
   - Router forwards the data to **Person 2’s MAC**.  

---

##  ARP Cache
- A temporary table where IP–MAC mappings are stored.  
- Prevents sending ARP requests repeatedly.  
- Example (Linux command):  
  ```bash
  arp -n
  # or
  ip neigh show
```
---
