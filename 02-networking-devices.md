
# Networking Devices

##  Topics Covered

- Hosts, Servers, Clients
- Switch vs Router vs Hub
- Modem, Access Point, Bridge
- Diagram: How devices connect in LAN/WAN
- OSI Layers
- Real-world Examples and Use Cases

---

##  Basic Networking Devices

###  Hosts, Servers, Clients

- **Host**: Any device connected to a network (PC, smartphone, printer).
- **Client**: A host that **requests services** (e.g., browser requesting a web page).
- **Server**: A host that **provides services** (e.g., web server, mail server).

###  Modem

- Converts ISP's analog signal to digital for home/company networks.
- Connects your network to the **Internet (WAN)**.

###  Router

- Connects different networks (like LAN to WAN).
- Directs traffic between networks.
- Can provide wireless (Wi-Fi) and wired connections.

###  Switch

- Connects **multiple devices within the same network (LAN)**.
- Sends data **only to the intended device** using MAC addresses.
- Used in companies for **internal communication and secure data transfer**.

###  Access Point (AP)

- Extends wireless coverage.
- Connects wireless devices to the wired LAN.
- Used in large buildings where router’s Wi-Fi range isn’t enough.

**Note**: Routers can act as access points too. But for larger spaces, a dedicated AP is better.

###  Hub (Obsolete)

- Broadcasts data to **all devices** (less secure, more traffic).
- Replaced by **switches** in modern networks.

###  Bridge

- Connects two different LAN segments.
- Operates at Data Link Layer (Layer 2).

---

##  Diagram – Devices in LAN/WAN

```
[Internet (WAN)]
       |
     Modem
       |
     Router
     /    \
 Switch   Access Point
   |           |
Devices     Wireless Devices
(PCs, etc.) (Phones, Laptops)
```

---

##  OSI Layers – Why It’s Important

| Layer | Name               | Purpose                                |
|-------|--------------------|----------------------------------------|
| 7     | Application         | Interfaces with apps (e.g., browser)   |
| 6     | Presentation        | Data translation (e.g., encryption)    |
| 5     | Session             | Start/end communication sessions       |
| 4     | Transport           | Reliable delivery (TCP/UDP)            |
| 3     | Network             | Routing (IP addresses)                 |
| 2     | Data Link           | MAC addressing                         |
| 1     | Physical            | Cables, switches, electrical signals   |

 Helps understand **how data travels** from one device to another.

---

##  Real-World Company Use

- **Switch**: Shares internal files securely within a company.
- **Router**: Connects company to the Internet.
- **Access Point**: Gives Wi-Fi to staff.
- **Modem**: Translates ISP signal for router.
- **Bridge**: Connects 2 buildings’ LANs.
- **Client-Server**: Employees (clients) accessing internal apps or cloud servers.

---

 **Key Understanding Recap**

- Switch = Internal sharing in company (secure, efficient).
- Router = Connects LAN to WAN (Internet).
- Access Point = Wireless extension.
- Modem = ISP translator.
- OSI = Big picture of how networking works.

---



