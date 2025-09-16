# Proxy Server

##  Topics Covered
1. What is a Proxy Server  
2. Why Use a Proxy Server  
3. Types of Proxy Servers  
   - Forward Proxy (with example)  
   - Reverse Proxy (with example)  
   - Transparent Proxy (with example)  
4. Proxy vs Router (Quick Comparison)  
5. Proxy vs VPN (Quick Comparison)  
6. Real-World Examples  

---

## 1. What is a Proxy Server
A Proxy Server is a **middle system** between your laptop (or system) and the internet server.  
When you open a website, your request first goes to the proxy, then the proxy contacts the website server, and finally gives the result back to you.  

---

## 2. Why Use a Proxy Server
- To **hide your system’s IP address**  
- To **block some websites** (like social media in companies)  
- To **filter traffic** for security  
- To **cache (store data)** for faster access  
- To **protect servers** from direct attack  

---

## 3. Types of Proxy Servers

###  Forward Proxy
- Works on the **user side (laptops/systems)**.  
- It sends requests to the internet server on behalf of the user.  
- The server only sees the proxy’s IP, not the actual laptop’s IP.  
- Mostly used by companies to control employee internet usage.  

**Example:**  
In a company, if employees try to open Facebook or YouTube, the forward proxy blocks it.  
If allowed, it will connect to the website using its own IP address, hiding the employee’s laptop IP.  

---

###  Reverse Proxy
- Works on the **server side (websites/cloud servers)**.  
- Users connect to the reverse proxy, not directly to the main server.  
- It hides the real server’s identity and also distributes user traffic to multiple servers.  

**Example:**  
Big websites like Amazon, Netflix, or Cloud services use **Nginx** or **Apache** as reverse proxies.  
They manage millions of user requests without exposing the real server directly.  

---

###  Transparent Proxy
- Users don’t even know it’s there.  
- It does not hide your IP.  
- Mostly used in schools, colleges, and companies to monitor or block sites.  

**Example:**  
In a college computer lab, some websites are blocked even though students never set a proxy.  
This happens because the network has a transparent proxy running.  

---

## 4. Proxy vs Router (Quick Comparison)

| Feature              | Proxy Server                            | Router                          |
|----------------------|-----------------------------------------|---------------------------------|
| Main Function        | Acts as middleman for web requests      | Connects devices to the internet|
| IP Handling          | Hides/replaces your system’s IP address | Converts private IP to public IP (NAT) |
| Filtering Websites   | Yes                                     | No (needs firewall/proxy rules) |
| Works On             | Application level (browser/system apps) | Network level (entire network)  |

---

## 5. Proxy vs VPN (Quick Comparison)

| Feature              | Proxy Server                         | VPN                               |
|----------------------|--------------------------------------|-----------------------------------|
| IP Hiding            | Yes, hides system IP (but limited)   | Yes, hides system IP completely   |
| Data Encryption      |  No encryption                     |  Full encryption (secure tunnel)|
| Speed                | Faster (no encryption overhead)      | Slightly slower (because of encryption) |
| Use Case             | Block/unblock websites, caching      | Full privacy, security, bypass geo-restrictions |
| Company/Personal Use | More in companies, schools, offices  | More by normal users for privacy  |

---

## 6. Real-World Examples

- **Company** → Uses forward proxy to block social media and monitor employee activity.  
- **College** → Uses transparent proxy to stop students from opening entertainment websites.  
- **Big Websites (Amazon, Netflix)** → Use reverse proxy (Nginx, Apache) to protect servers and manage heavy traffic.  
- **Normal User** → Installs proxy extension or VPN app in browser to unblock websites or hide location.  

---

