# Subnets in Cloud Computing

## Topics Covered
- What is a Subnet
- Why Use Subnets
- Types of Subnets
- Subnets in Cloud Example (AWS)
- Route Tables
- How It Works in Practice
- Real-World Scenario
- Role of Cloud Engineer
- Key Takeaways

---

## 1. What is a Subnet?
A **subnet** (short for **subnetwork**) is a smaller network within a larger network.  
It helps organize and control traffic inside your **VPC (Virtual Private Cloud)**.

**Analogy:**  
- VPC → Apartment building  
- Subnet → Floor in the building  
- Servers/resources → People living on that floor  

---

## 2. Why Use Subnets?
1. **Divide network for management**  
   - Keep web servers and databases separate.  
2. **Control traffic with security**  
   - Public and private subnets with different access rules.  
3. **Efficient IP management**  
   - Avoid wasting IP addresses.  
4. **Isolation and security**  
   - Network segmentation for secure architecture.  

---

## 3. Types of Subnets
### a) Public Subnet
- Connected to **Internet Gateway (IGW)**  
- Accessible from the internet  
- Example: Web servers  

### b) Private Subnet
- Not directly accessible from internet  
- Access internet via **NAT Gateway** for updates  
- Example: Databases, backend services  

### c) Isolated/Hybrid Subnet
- No internet access at all  
- Example: Internal sensitive tools  

---

## 4. Subnets in Cloud Example (AWS)
VPC CIDR: `10.0.0.0/16` → 65,536 IPs  

| Subnet Type   | CIDR Block    | IPs  | Purpose                    |
|---------------|---------------|------|----------------------------|
| Public Subnet | 10.0.1.0/24  | 256  | Web servers, Load balancers|
| Private Subnet| 10.0.2.0/24  | 256  | Databases, backend services|

**Steps:**
1. Create a VPC → assign a CIDR block  
2. Create subnets → assign smaller CIDR ranges  
3. Associate **route tables** → control traffic flow  
4. Attach **security rules** → control access  

---

## 5. Route Tables
A **route table** directs traffic from a subnet to the correct destination.

### a) Public Subnet Route Table
| Destination | Target          |
|-------------|----------------|
| 0.0.0.0/0   | Internet Gateway|

### b) Private Subnet Route Table
| Destination | Target         |
|-------------|---------------|
| 0.0.0.0/0   | NAT Gateway    |

**Explanation of 0.0.0.0/0:**  
- `0.0.0.0/0` means **all IP addresses** in IPv4  
- It is a **default route** → catch-all for any traffic not matched by other routes  
- The **target** (IGW or NAT) decides the path traffic will take  

---

## 6. How It Works in Practice
- **Public Subnet (Web Server)**  
  - Traffic goes to **Internet Gateway (IGW)** → directly accessible from the internet  
- **Private Subnet (Database / App Server)**  
  - Traffic goes to **NAT Gateway** → NAT translates private IP to public IP → then goes to IGW → internet  
- Even though both use `0.0.0.0/0`, they **don’t conflict** because each subnet has its **own route table**  
- **Analogy:**  
  - Public street → goes straight to the highway  
  - Private street → first goes to toll booth (NAT), then highway  

---

## 7. Real-World Scenario
- **Web Server** → Public Subnet → IGW → Accessible by users  
- **Database** → Private Subnet → NAT Gateway → No direct internet access  
- **App Server** → Private Subnet → NAT Gateway → Communicates internally  

---

## 8. Role of Cloud Engineer
- Decide which subnets need internet access  
- Associate proper route tables with subnets  
- Configure IGW, NAT Gateway, or peering connections  
- Ensure **security groups** and **NACLs** are correct  
- Control traffic flow and network segmentation  

---

## 9. Key Takeaways
- Subnets **organize** your cloud network  
- **Public vs Private** subnets control internet access  
- **Route tables** direct traffic  
- Cloud engineers design network flow, security, and access  
- `0.0.0.0/0` is the **default route** → target determines path (IGW or NAT)  

---
