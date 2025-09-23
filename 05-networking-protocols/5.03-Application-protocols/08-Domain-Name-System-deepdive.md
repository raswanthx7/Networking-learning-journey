# DNS Deep Dive – Topics Covered

1. What is DNS?  
2. Why Do We Need DNS?  
3. DNS Hierarchy  
4. Core DNS Components  
5. DNS Records  
6. Zone File  
7. How DNS Works (Step-by-Step)  
8. TTL (Time to Live)  
9. Types of DNS Queries  
10. Hands-On Commands  
11. Summary  

---

## 1. What is DNS?
DNS (Domain Name System) is like the **phonebook of the internet**.  
It translates human-friendly **domain names** (e.g., `google.com`) into machine-friendly **IP addresses** (e.g., `142.250.183.142`).

- Without DNS → We would need to remember IP addresses for every website.  
- With DNS → We simply type domain names, and DNS resolves them to IP addresses.

---

## 2. Why Do We Need DNS?
- Easy to use domain names instead of numbers.  
- Flexible: one domain can map to multiple IPs (load balancing).  
- Supports different services: websites, emails, APIs, etc.  
- Centralized management of records.

---

## 3. DNS Hierarchy
Domain names are structured in a **tree-like hierarchy**:

- **Root (.)** → the starting point of DNS.  
- **Top-Level Domain (TLD):** `.com`, `.org`, `.net`  
- **Second-Level Domain:** `google` in `google.com`  
- **Subdomain:** `www`, `mail`, `blog` in `www.google.com`, `mail.google.com`

Example:  
www.google.com

│
├── www → Subdomain
├── google → Second-Level Domain
└── com → Top-Level Domain

---

## 4. Core DNS Components

1. **Recursive Resolver**  
   - A server (usually by ISP or Google DNS `8.8.8.8`) that performs DNS lookups on behalf of the client.  
   - Does all the work and returns the final IP address to your browser.  

2. **Root Server**  
   - Knows where the TLD servers are (`.com`, `.org`, `.net` etc).  
   - Does not store IPs of domains.

3. **TLD Server**  
   - Knows where the authoritative servers for second-level domains exist (`google.com`).  

4. **Authoritative Name Server**  
   - Stores the **zone file** for a domain.  
   - Provides the final answer (IP address or record details).

---

## 5. DNS Records
DNS stores different types of information in the form of **records**.

| Record | Purpose | Example |
|--------|---------|---------|
| **A** | Maps a domain to an **IPv4** address | `google.com → 142.250.183.142` |
| **AAAA** | Maps a domain to an **IPv6** address | `google.com → 2404:6800:4007:811::200e` |
| **CNAME** | Maps one name (alias) to another domain | `www.mywebsite.com → mywebsite.com` |
| **MX** | Mail Exchange – tells which server handles email | `gmail.com → aspmx.l.google.com` |
| **NS** | Name Server – points to authoritative DNS servers for the zone | `google.com → ns1.google.com` |
| **SOA** | Start of Authority – stores admin info, refresh times | Zone metadata |

 All these records are stored in the **zone file** on authoritative servers.

---

## 6. Zone File
A **zone file** is a simple text file that contains all the DNS records for a domain.  

Example (`mywebsite.com` zone file):

@ IN A 192.0.2.1
@ IN MX 10 mail.mywebsite.com.
www IN CNAME mywebsite.com.
ns1 IN A 192.0.2.2
@ IN NS ns1.mywebsite.com.

---

## 7. How DNS Works (Step-by-Step)
1. User types `www.google.com` in browser.  
2. Browser checks local cache (TTL).  
3. If not found → Query goes to recursive resolver.  
4. Resolver asks Root Server: “Where is `.com` TLD?”  
5. Root replies: “Ask `.com` TLD server.”  
6. Resolver asks `.com` TLD: “Where is google.com’s name server?”  
7. TLD replies with Authoritative Name Server for `google.com`.  
8. Resolver asks authoritative server: “What is IP for www.google.com?”  
9. Authoritative server replies with final IP.  
10. Resolver caches answer for TTL and gives it to the browser.  
11. Browser connects to the IP and loads the website.  

All of this happens in **milliseconds**.

---

## 8. TTL (Time to Live)
- Every DNS record has a **TTL value** (e.g., 300 seconds = 5 minutes).  
- TTL controls how long the answer is cached.  
- If TTL not expired → answer comes from cache (faster).  
- If expired → full resolution process happens again.

---

## 9. Types of DNS Queries
- **Recursive Query** → Client asks resolver for final answer, resolver does all the work.  
- **Iterative Query** → Resolver goes step by step: Root → TLD → Authoritative.  
- **Non-Recursive Query** → Resolver already has the answer in cache, responds immediately.  

---

## 10. Hands-On Commands
- `nslookup google.com` → Shows IP and server used.  
- `dig google.com` → Detailed DNS query output.  
- `host google.com` → Quick lookup.

---

#  Summary
- DNS = Internet’s phonebook.  
- Converts domain names to IP addresses.  
- Works in hierarchy: Root → TLD → Authoritative.  
- Stores info in records (A, AAAA, CNAME, MX, NS, SOA).  
- Zone file = database of records.  
- TTL controls caching.  
- Queries: Recursive, Iterative, Non-Recursive.  
- Tools: nslookup, dig, host.

---

