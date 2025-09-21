# Routing in Cloud

## Topics Covered
- What is Routing
- Why Routing is Needed in Cloud
- How Routing Works (Step-by-Step)
- Route Table Basics
- Route Table in AWS
- Common Route Targets (IGW, NAT, Local, Peering, VPN)
- Practical Example with Subnets
- Why Routes are Configured (Local vs IGW vs NAT)
- Key Takeaways

---

## What is Routing?
Routing is the process of deciding **where network traffic should go**.  
In cloud, routing tells packets:  
👉 "If traffic is going here, send it this way."  

---

## Why Routing is Needed in Cloud
- To connect **subnets inside a VPC**  
- To connect **VPC to the internet**  
- To connect **private subnets via NAT**  
- To connect to **other VPCs (peering)** or **on-premises (VPN)**  

Without routing, packets won’t know where to go.

---

## How Routing Works (Step-by-Step)
1. A packet leaves an **instance** in a subnet.  
2. The packet first checks the **subnet’s route table**.  
3. The route table has entries like:
   - **Destination**: IP/CIDR  
   - **Target**: Where to send (IGW, NAT, Local, etc.)  
4. The packet follows the matched rule.  
5. If no rule matches → packet is dropped.  

---

## Route Table Basics
- Every **VPC** has a **main route table**.  
- Each **subnet** must be associated with a route table.  
- Route table decides **how traffic flows** out of the subnet.  

---

## Route Table in AWS
Typical entries:  
| Destination   | Target       | Meaning |
|---------------|-------------|---------|
| 10.0.0.0/16   | local       | Internal VPC traffic stays inside |
| 0.0.0.0/0     | igw-12345   | Send all external traffic to Internet Gateway |
| 0.0.0.0/0     | nat-12345   | Send external traffic from private subnets via NAT |

---

## Common Route Targets
- **Local** → Keeps traffic inside VPC  
- **IGW (Internet Gateway)** → Public internet access  
- **NAT Gateway** → Private subnet internet access  
- **VPC Peering** → Connects to another VPC  
- **VPN Gateway** → Connects to on-premises  

---

## Practical Example with Subnets
- VPC: `10.0.0.0/16`  
- Public Subnet: `10.0.1.0/24`  
- Private Subnet: `10.0.2.0/24`  

**Public Route Table**  
| Destination | Target   |
|-------------|----------|
| 10.0.0.0/16 | local    |
| 0.0.0.0/0   | IGW      |

**Private Route Table**  
| Destination | Target   |
|-------------|----------|
| 10.0.0.0/16 | local    |
| 0.0.0.0/0   | NAT      |

👉 Public subnet instances go directly to the internet.  
👉 Private subnet instances go to NAT, then internet.

---

## Why Routes are Configured Like This

### `10.0.0.0/16 → local`
- This is the **VPC’s CIDR range**.  
- AWS automatically creates this route so all **subnets in the VPC can talk** to each other.  
- Example: `10.0.1.10` (public subnet) can ping `10.0.2.10` (private subnet) because of this.

### `0.0.0.0/0 → IGW`
- `0.0.0.0/0` means **any IP outside the VPC**.  
- Adding IGW here says: *“Send all non-VPC traffic to the internet.”*  
- Used in **public subnets** for EC2s that need public internet.

### `0.0.0.0/0 → NAT`
- NAT lets **private subnets** reach the internet **without exposing themselves**.  
- Private EC2s can download updates, but outsiders **cannot connect back directly**.  
- Used in **private subnets** for security.

---

## Key Takeaways
- Routing decides packet paths.  
- Route tables are **per subnet**, not per instance.  
- `10.0.0.0/16 → local` = keep traffic inside VPC.  
- `0.0.0.0/0 → IGW` = public subnet internet access.  
- `0.0.0.0/0 → NAT` = private subnet secure internet access.  
- Public vs Private routing is the foundation of secure cloud networking.

---

