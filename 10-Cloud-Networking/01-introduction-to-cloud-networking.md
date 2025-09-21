# Introduction to Cloud Networking

##  Topics Covered
- What is Cloud Networking  
- Difference between On-Premises vs Cloud Networking  
- AWS Networking Components Overview (VPC, Subnets, SG, NACL, ELB, Route53)  

---

##  What is Cloud Networking?
Cloud Networking means using **virtual networking services** provided by cloud platforms (like AWS) instead of building and maintaining physical networking devices (routers, switches, firewalls, etc.) in your own data center.  
- All physical infrastructure (servers, routers, cables, data centers) is managed by the cloud provider.  
- You, as a cloud/network engineer, only **design and configure virtual networks** using cloud tools.  
- Example: In AWS, you create a **VPC (Virtual Private Cloud)** and design subnets, routing, gateways, and security rules inside it.

---

##  Difference: On-Premises vs Cloud Networking

| Feature                 | On-Premises Networking                         | Cloud Networking (AWS)                         |
|--------------------------|-----------------------------------------------|-----------------------------------------------|
| **Hardware**             | You buy/manage routers, switches, firewalls   | AWS manages all hardware behind the scenes    |
| **Setup Cost**           | High upfront (servers, racks, cooling, power) | Pay-as-you-go, no upfront infrastructure cost |
| **Scalability**          | Difficult, need to buy new hardware           | Easy, scale with a few clicks (auto-scaling)  |
| **Maintenance**          | You maintain cables, power, OS, patches       | AWS maintains infra, you only configure       |
| **Control**              | Full physical control                         | Virtual control through AWS console/CLI       |
| **Networking**           | Configure subnets, VLANs, routing physically  | Configure VPC, subnets, routing virtually     |

👉 **Main Idea:**  
On-Prem = You manage both **hardware + configuration**.  
Cloud = AWS manages **hardware**, you only manage **configuration**.  

---

##  AWS Networking Components Overview

When you design networking in AWS, these are the **main building blocks**:

1. **VPC (Virtual Private Cloud)**  
   - Your isolated virtual data center in AWS.  
   - You choose IP ranges (CIDR block).  

2. **Subnets**  
   - Divide your VPC into **public** (internet-facing) and **private** (internal) areas.  

3. **Security Groups (SG)**  
   - Virtual firewalls for EC2 instances.  
   - Control inbound/outbound traffic at **instance level**.  

4. **Network ACLs (NACLs)**  
   - Firewall at **subnet level**.  
   - Control traffic in/out of entire subnet.  

5. **ELB (Elastic Load Balancer)**  
   - Distributes traffic across multiple servers.  
   - Types: Application LB, Network LB, Classic LB.  

6. **Route 53 (DNS Service)**  
   - AWS DNS service for domain names.  
   - Maps domain → IP / load balancer / cloud service.  

---



