# Networking – Ports

## Topics Covered
1. What is a Port?  
2. Port Ranges  
3. Port Examples  
4. Advantages of Ports  
5. Real-World Analogy  
6. Commonly Used Ports (Cloud & AWS Focus)  

---

## 1. What is a Port?
A **port** is a virtual communication endpoint that allows network traffic to be directed to the correct service or application.  
- **IP address** = House address  
- **Port** = Room number inside the house  
- Without ports, all incoming traffic would arrive at the same place, and the computer wouldn’t know which program should handle it.  

---

## 2. Port Ranges
Port numbers are **0 – 65535**, divided into three categories:

- **Well-Known Ports (0 – 1023):** Reserved for core services like HTTP (80), HTTPS (443), DNS (53), SSH (22).  
- **Registered Ports (1024 – 49151):** Used by applications and companies (e.g., MySQL = 3306, RDP = 3389).  
- **Dynamic/Ephemeral Ports (49152 – 65535):** Temporary ports chosen by the OS for client connections.  
  - Example: When you connect to `https://amazon.com`, your computer may use a random port like **51734** to talk to the server’s port **443**.
  
**Quick Summary:**  
- **Well-known ports** = Core services (e.g., 80 for web, 22 for SSH).  
- **Registered ports** = Applications and software (e.g., 3306 for MySQL).  
- **Dynamic ports** = Temporary/random ports used by your computer (e.g., 51734).  
---

## 3. Port Examples
- **Port 80** → HTTP (web traffic)  
- **Port 443** → HTTPS (secure web traffic)  
- **Port 22** → SSH (remote login)  
- **Port 25** → SMTP (send email)  
- **Port 3306** → MySQL database  
- **Port 3389** → RDP (remote desktop)  

---

## 4. Advantages of Ports
- **Organized Communication:** Each service has its own port → no confusion.  
- **Multi-tasking:** One computer can run multiple services at once.  
- **Security Control:** Firewalls filter traffic using ports.  
- **Efficiency:** Quickly directs traffic to the right service.  

---

## 5. Real-World Analogy
Imagine a **college campus**:  
- **Main gate** = IP address (all traffic enters here).  
- **Different rooms** = Ports (each room for a specific purpose).  
  - Library (Port 80 → HTTP)  
  - Exam office (Port 25 → SMTP)  
  - Computer lab (Port 22 → SSH)  

Without room numbers (ports), students would get lost even if they reach the campus (IP).  

---

## 6.Commonly Used Ports in Cloud (AWS & Other Cloud Platforms)
These ports are **very important** for cloud engineers and admins:

| **Port** | **Service** | **Cloud Use Case** |
|----------|-------------|---------------------|
| 22       | SSH         | Secure remote login to Linux EC2 instances |
| 80       | HTTP        | Hosting web applications |
| 443      | HTTPS       | Secure web apps, APIs, load balancers |
| 25       | SMTP        | Email sending (sometimes restricted in AWS for spam control) |
| 53       | DNS         | Domain resolution in Route 53 and VPC |
| 3389     | RDP         | Remote Desktop for Windows EC2 instances |
| 3306     | MySQL       | Databases (Amazon RDS, Aurora MySQL) |
| 1433     | MS SQL      | Databases (Amazon RDS SQL Server) |
| 27017    | MongoDB     | NoSQL databases on EC2 |
| 6379     | Redis       | In-memory caching (Amazon ElastiCache) |
| 8080     | HTTP-Alt    | Application servers, API endpoints |
| 5000–6000| Ephemeral   | Temporary client connections |

---

 **Quick Summary:**  
A **port** is like a door to a service. Ports help cloud engineers manage traffic, secure services, and run multiple applications on the same server. Common cloud ports you must know: **22 (SSH), 80 (HTTP), 443 (HTTPS), 3389 (RDP), 3306 (MySQL), 1433 (MSSQL), 6379 (Redis), 27017 (MongoDB).**  

---

