##  Topics Covered:

- Bus, Star, Mesh, Ring (basic understanding)
- IP Addressing Basics (IPv4 and IPv6)
- MAC Address vs IP Address
- Difference Between Public and Private IPs
- OSI Model (with Layer Functions)
- Packet Flow Through OSI Model (Sender to Receiver)

---

##  Concepts Learned:

###  Network Topologies

 1. **Bus Topology**
- Single central cable (backbone).
- All devices are connected to this line.
- Low cost, but one break affects entire network.

 2. **Star Topology**
- All nodes connect to a central hub or switch.
- Easy to manage and isolate faults.
- Hub failure affects entire network.

 3. **Ring Topology**
- Devices form a closed loop.
- Data flows in one direction (or two in dual ring).
- A break in the ring can disrupt communication.

 4. **Mesh Topology**
- Every device connected to every other.
- Highly redundant and reliable.
- Very expensive and complex.

 5. **Hybrid Topology**
- Mix of two or more topologies (e.g., Star + Ring).
- Flexible and scalable.

---

###  IP Addressing:
- **IPv4**: 32-bit address (e.g., 192.168.0.1)
- **IPv6**: 128-bit address for more unique devices.
- **MAC Address**: Unique hardware address of a device.
- **IP Address**: Logical address used to communicate on a network.

###  Public vs Private IP:
- **Private IP**: Used inside a local network.
- **Public IP**: Used to connect to the internet.
- Devices in LAN use private IPs and share a single public IP via NAT.

---


##  OSI Model – 7 Layers

| Layer | Layer Name        | Function Example |
|-------|-------------------|------------------|
| 7     | Application       | Apps like browsers, WhatsApp |
| 6     | Presentation      | Data encryption, translation |
| 5     | Session           | Open/close/manage sessions |
| 4     | Transport         | TCP/UDP, delivery & error check |
| 3     | Network           | IP addressing and routing |
| 2     | Data Link         | MAC, framing, error detection |
| 1     | Physical          | Cables, Wi-Fi, transmission |

---

##  Flow of OSI Model (Sender to Receiver)

1. **Application Layer**: You type a message in WhatsApp.
2. **Presentation Layer**: Converts message to bits, encrypts.
3. **Session Layer**: Establishes connection to friend’s phone.
4. **Transport Layer**: Splits message into **segments**, uses TCP/UDP.
5. **Network Layer**: Adds **IP Address** to route message.
6. **Data Link Layer**: Adds MAC address, prepares **frames**.
7. **Physical Layer**: Sends data via **Wi-Fi**, **Ethernet**, etc.

Reverse happens on the receiver side.

---

##  Real-World Examples

- **LAN**: Office computers sharing files.
- **WAN**: Streaming a YouTube video.
- **Transport Layer**:
  - TCP: Email or text message (reliable)
  - UDP: Zoom or Video Call (faster, no retransmit)


---

##  Commands to Practice

```bash
ip a            # Show IP address
hostname -I     # Show IP address
ping 8.8.8.8    # Test network connection
```

---
