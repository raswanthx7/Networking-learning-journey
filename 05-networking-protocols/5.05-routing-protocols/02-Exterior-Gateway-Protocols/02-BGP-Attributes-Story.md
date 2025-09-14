# BGP Attributes – Real Internet Story (Stark Company & Cloud Providers)

## Topics Covered
- Introduction to BGP Attributes
- How Attributes Work in the Real Internet
- Story Scenario: Stark Company Edge Router & Cloud Providers
- Each Attribute Explained in Action
- Summary

---

## Introduction to BGP Attributes
- BGP attributes are **rules or properties** that help routers **decide the best path** to reach a destination on the Internet.  
- Each attribute has its own priority and purpose.  
- Without these attributes, BGP wouldn’t know which route to choose when multiple paths exist.

---

## How Attributes Work in the Real Internet
- The Internet is made of **millions of networks**.  
- Each network is managed by an **Autonomous System (AS)** (e.g., Airtel, Jio, Tata, AWS, Azure, Google Cloud).  
- Routers use BGP to **share network reachability** with each other.  
- Attributes help determine the **best path between ASes**.  

---

## Story Scenario: Stark Company
1. **Stark Company** has many internal routers (RIP/OSPF inside).  
2. The **Edge Router** of Stark Company connects to multiple ISPs (Airtel, Jio, Tata).  
3. Edge Router uses **BGP** to learn about external networks like **AWS, Azure, Google Cloud**.  
4. When Stark’s Edge Router gets multiple paths to the same cloud provider, it uses **BGP attributes** to select the best one.  
5. It can also **advertise its own reachable networks** to ISPs so other companies can route traffic to Stark.

---

## Each Attribute in Action

1. **Weight (Cisco Only)**
   - Used locally on Stark’s Edge Router.  
   - Example: Stark wants traffic to **AWS** to go through Airtel instead of Jio.  
   - Higher weight → route is preferred.  

2. **Local Preference**
   - Decides which exit path **inside Stark Company** is preferred.  
   - Example: Stark receives AWS routes from Airtel and Tata.  
   - Local Preference higher → router chooses that ISP for outgoing traffic.  

3. **AS-Path**
   - Shows the sequence of AS numbers to reach a destination.  
   - Shortest AS-Path is preferred.  
   - Example: AWS → path via Airtel (2 AS hops) vs path via Jio+Tata (3 AS hops).  
   - Stark chooses Airtel path because fewer AS hops.  

4. **Origin Type**
   - Determines trust of route source.  
   - Preference: IGP > EGP > Incomplete.  
   - Example: Route learned from internal ISP network (IGP) is preferred over a less reliable route.  

5. **MED (Multi Exit Discriminator)**
   - Suggests preferred entry point to neighbors.  
   - Example: Stark advertises AWS route to Jio and says “use this link (lowest MED) to reach AWS via me”.  

6. **eBGP vs iBGP**
   - eBGP routes (external) are preferred over iBGP (internal).  
   - Example: Stark Edge Router receives route from Airtel (eBGP) and from its internal iBGP neighbor.  
   - Airtel’s route is chosen.  

7. **IGP Metric to Next-Hop**
   - Tie-breaker: shortest internal path to next hop router.  
   - Example: Multiple ISPs provide the same external path. Stark chooses the one with lower internal cost to reach that ISP.

---

## Summary – How the Internet Works Using Attributes
1. Stark Edge Router connects to multiple ISPs.  
2. Each ISP advertises networks (e.g., AWS, Azure, Google Cloud) via BGP.  
3. Stark Edge Router receives **multiple paths** to same cloud provider.  
4. Attributes decide:  
   - Weight → local preference  
   - Local Preference → best exit  
   - AS-Path → shortest AS sequence  
   - Origin → trust of route  
   - MED → suggest entry point  
   - eBGP vs iBGP → external preferred  
   - IGP Metric → internal tie-breaker  
5. Best path installed in routing table.  
6. Stark Edge Router also **advertises reachable networks** to ISPs for others to use.  

---

This story makes it clear how **BGP attributes work in a cloud-focused scenario**. Stark Company = your network, Edge Router = main connection point, ISPs = Internet providers, Cloud Providers = AWS/Azure/Google Cloud.

