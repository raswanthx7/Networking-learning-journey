# MAC Addressing

## Topics Covered
- What is a MAC Address
- MAC Address Format
- Types of MAC Addresses
- Purpose of MAC Addresses
- How MAC Addresses Work
- Real-World Use Cases
- Commands to Check MAC Address
- summary

---

## 1. What is a MAC Address
- **MAC** stands for **Media Access Control**.
- It is a **unique hardware identifier** assigned to every network interface card (NIC).
- MAC addresses operate at the **Data Link Layer (Layer 2)** of the OSI model.

---

## 2. MAC Address Format
- MAC addresses are **48-bit numbers**.
- Typically written in **hexadecimal** as six groups of two digits:
`00:1A:2B:3C:4D:5E`

- The first **3 bytes** (OUI – Organizationally Unique Identifier) identify the manufacturer.
- The last **3 bytes** are unique for each device.

---

## 3. Types of MAC Addresses
1. **Unicast** – Identifies a single network interface.
2. **Multicast** – Identifies a group of devices.
3. **Broadcast** – FF:FF:FF:FF:FF:FF, used to communicate with all devices on a network.

---

## 4. Purpose of MAC Addresses
- Uniquely identifies devices on a **local network**.
- Helps in **switch forwarding decisions**.
- Used for **network security and filtering**.

---

## 5. How MAC Addresses Work
- When a device sends a frame, it uses the **destination MAC address** to deliver the data to the correct device.
- Switches use MAC addresses to **build a MAC(CAM) table** (switching table) to forward frames efficiently.

### Example: How a Switch Uses the MAC (CAM) Table

- **Laptop A MAC:** `00:1A:2B:3C:4D:5E`  
- **Laptop B MAC:** `11:22:33:44:55:66`  

When **Laptop A** sends a frame to **Laptop B**:  
1. The switch receives the frame on the port connected to Laptop A.  
2. It checks its **MAC (CAM) table**.  
3. Finds that `11:22:33:44:55:66` belongs to **Laptop B** on a specific port.  
4. Forwards the frame **only to Laptop B’s port** (instead of broadcasting to all ports).  

### MAC (CAM) Table on Switch

| MAC Address        | Port  |
|--------------------|-------|
| 00:1A:2B:3C:4D:5E  | Fa0/1 |
| 11:22:33:44:55:66  | Fa0/2 |

---

## 6. Real-World Use Cases
- **Switches:** Forward frames using MAC addresses.
- **ARP Protocol:** Maps IP addresses to MAC addresses.
- **Network Security:** MAC filtering in Wi-Fi routers.
- **Troubleshooting:** Identify devices in a network.

---

## 7. Commands to Check MAC Address
- **Linux / macOS:**
```bash
ifconfig
 or 
ip link show
```
## Summary

- MAC addresses are unique hardware identifiers for network devices.
- Operate at Layer 2, essential for switching and local network communication.
- Knowledge of MAC addresses is crucial for networking, cloud, and troubleshooting.

---
