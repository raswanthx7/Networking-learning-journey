#  Stark Company – Firewall, IDS, IPS, and Internal Server Scenario

## Topics Covered
- Why companies use internal servers  
- Placement of Firewall, IDS, IPS  
- Scenario: Employee accessing Google (external server)  
- Scenario: Employee accessing company internal server  
- Key differences explained  

---

## 1. Why Do Companies Need Internal Servers?
- Internal servers are used to **store and run company applications and data** that should not be exposed directly to the internet.  
- Examples:  
  - HR system (payroll, leave management)  
  - File servers (documents, reports)  
  - Databases (customer records, finance data)  
  - Intranet portals (internal websites for employees)  

 **Reason:** Improves **security** and **performance** by keeping sensitive data **inside company network**, not outside.  

---

## 2. Where Are Firewall, IDS, IPS Placed?
- Firewalls, IDS, and IPS are **security layers placed at the company’s network edge**.  
- They act as a **security gate** between:  
  - The company’s internal network (employees + internal servers).  
  - The external internet (Google, AWS, other websites).  

---

## 3. Scenario A: Employee Accessing Google (External Website)
### Steps:
1. Employee at **Stark Company** opens browser → types `google.com`.  
2. Request goes directly to **Firewall/IDS/IPS** (not to internal server).  
3. Security layers check the request (IP, port, state, threats).  
4. If safe → request forwarded to Google server.  
5. Google server replies → response comes back through Firewall/IDS/IPS.  
6. If safe → response is delivered directly to **employee’s system**.  

 Internal server is **not involved** in this case.  

---

## 4. Scenario B: Employee Accessing Internal Company Application
### Steps:
1. Employee opens **Stark Company HR portal** (hosted on internal server).  
2. Request goes through Firewall/IDS/IPS → but since destination is **internal server**, it is routed inside company network.  
3. Internal server processes the request and sends back data (like payslip info).  
4. Response passes through Firewall/IDS/IPS (internal checks) → reaches the employee’s system.  

 Internal server is **involved only for company-specific applications/data**.  

---

## 5. Key Differences to Remember
- **External Request (Google, YouTube, etc.)**  
  Employee → Firewall/IDS/IPS → Internet (Google) → Firewall/IDS/IPS → Employee  

- **Internal Request (Company HR, Payroll, DB, File Server)**  
  Employee → Firewall/IDS/IPS → Internal Server → Firewall/IDS/IPS → Employee  

---

##  Final Understanding
- Firewalls, IDS, and IPS sit **in front of everything** as the **first line of defense**.  
- **Internal servers** are used only for **company apps and data**.  
- Not every request goes through the internal server → only requests for internal company services.  
- Internet browsing (Google, AWS) bypasses internal server but still goes through Firewall/IDS/IPS.  

---
