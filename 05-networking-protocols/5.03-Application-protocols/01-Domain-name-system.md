#  DNS Protocol (Domain Name System)

##  Topics Covered
- What is DNS
- Why DNS is needed
- What is TLD
- What is Root Server
- What is Authoritative DNS Server
- DNS Scenario (Step-by-Step Example)
- DNS Resolution Process
- Summary

---

##  What is DNS?
- **Full Form:** Domain Name System  
- **Purpose:** Converts **domain names** (like `google.com`) into **IP addresses** (like `142.250.190.78`).  
- Computers communicate using IP addresses, but humans find names easier to remember.  

 DNS is often called the **Phonebook of the Internet**.

---

##  Why DNS is needed?
- Without DNS, users would need to remember numeric IP addresses.  
- Example: Instead of typing `google.com`, you would have to type `142.250.190.78`.  
- DNS makes the Internet **user-friendly** by handling this conversion automatically.  

---

##  What is TLD?
- **Full Form:** Top-Level Domain  
- It is the **last part** of a domain name (after the dot).  
- Example:  
  - `google.com` → `.com` is the TLD  
  - `wikipedia.org` → `.org` is the TLD  
  - `gov.in` → `.in` is the TLD  

---

##  What is a Root Server?
- A **Root DNS Server** is the **starting point** in the DNS hierarchy.  
- Root servers **do not store every website’s IP**.  
- Instead, they **know where the TLD servers are** (like `.com`, `.org`, `.in`).  
- There are **13 root server systems (A to M)** with many global copies.  

---

##  What is an Authoritative DNS Server?
- The **final authority** in DNS resolution.  
- Stores the **actual DNS records** of a domain (A, AAAA, MX, CNAME, NS).  
- Example: For `google.com`, Google’s Authoritative DNS server replies with the real IP of `www.google.com`.  

---

##  DNS Scenario Example (Step-by-Step)
1. User types `www.amazon.com` in the browser.  
2. Resolver asks a **Root Server** → Root replies: “Go to the `.com` TLD server.”  
3. Resolver asks the **.com TLD Server** → TLD replies: “Go to Amazon’s Authoritative server.”  
4. Resolver asks the **Authoritative DNS Server** → It replies with Amazon’s actual IP address.  
5. Resolver gives the IP to the user’s computer → Browser connects to Amazon.  

---

##  DNS Resolution Process (Detailed)
1. User enters domain name (e.g., `www.example.com`).  
2. Local DNS Resolver checks its cache.  
3. If not found → Resolver queries the **Root Server**.  
4. Root Server directs to **TLD server** (e.g., `.com`).  
5. TLD server directs to **Authoritative DNS server** (e.g., Example’s DNS).  
6. Authoritative server responds with the correct IP address.  
7. Resolver caches the result and returns the IP to the user’s computer.  
8. The computer connects to the destination server using the IP.  

---

##  Summary
- DNS = Converts **domain names** to **IP addresses**.  
- **TLD = Last part of a domain (like `.com`, `.org`, `.in`).**  
- **Root Server = First guide, knows where TLD servers are.**  
- **Authoritative DNS Server = Final authority that gives the actual IP.**  
- DNS works like the **Internet’s phonebook**, making websites easy to access by name instead of numbers.  

---

