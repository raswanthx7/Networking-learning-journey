#  DHCP Protocol (Dynamic Host Configuration Protocol)

##  Topics Covered
- What is DHCP
- DORA Process
- Lease Time (with scenario)
- DNS Server Address (why needed)
- Default Gateway (why needed)

---

##  What is DHCP?
- **Full Form:** Dynamic Host Configuration Protocol  
- **Purpose:** Automatically assigns **IP addresses** and other network settings to devices.  
- Eliminates the need for manual IP configuration.  

---

##  DORA Process (Concept)
DHCP uses a 4-step process to assign IPs:  
1. **DHCP Discover** → Client broadcasts: “Is there any DHCP server?”  
2. **DHCP Offer** → Server replies with available IP.  
3. **DHCP Request** → Client requests the offered IP.  
4. **DHCP Acknowledgement** → Server confirms assignment.  

*(Note: DORA scenario is assumed; exact steps covered in theory.)*  

---

##  Lease Time
- **Definition:** The **time period** for which the DHCP server assigns an IP to a device.  
- After lease expires, the device must **renew** the IP or request a new one.  

### Scenario Example
- DHCP server lease time = 24 hours  
- Laptop gets IP `192.168.1.20` at 10:00 AM  
- At 10:00 AM next day:  
  - If laptop is still connected → automatically renews the lease  
  - If laptop disconnected → IP becomes free for another device  

**Purpose:** Ensures efficient use of IP addresses and avoids conflicts.  

---

##  DNS Server Address
- DHCP also provides the **DNS server address** to the device.  
- **Purpose:** Tells the device which DNS server to contact to resolve domain names to IPs.  
- Ensures automatic, consistent, and correct domain resolution across the network.  

---

##  Default Gateway
- DHCP provides the **default gateway address** (usually your router).  
- **Purpose:** Allows devices to communicate with networks outside the local network (like the Internet).  
- Acts as the **“exit door”** for traffic going to other networks.  

### Scenario Example
- Device IP = `192.168.1.15`  
- Subnet = `255.255.255.0` → local network = `192.168.1.0/24`  
- Default Gateway = `192.168.1.1` (router)  
- When visiting `www.google.com`:  
  1. Device sees Google is outside local network.  
  2. Sends packet to **default gateway `192.168.1.1`**.  
  3. Router forwards it to Internet and brings back the reply.  

---

## Summary
- DHCP = Automatically assigns **IP addresses** and network settings.  
- **DORA** = 4-step process (Discover, Offer, Request, Acknowledge).  
- **Lease Time** = Duration of IP assignment; ensures recycling of IPs.  
- **DNS Server Address** = Tells device where to resolve domain names.  
- **Default Gateway** = Router IP to reach outside networks.  

---

