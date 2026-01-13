# Hub vs Switch – Broadcast & Collision Domain Lab

<img width="1607" height="752" alt="image" src="https://github.com/user-attachments/assets/1900d739-8696-4f36-83e1-6fb942e7d2e3" />


## What this lab is about
In this lab, I compared how a **hub** and a **switch** behave when devices communicate on the network.  
The main goal was to understand **broadcast traffic, collision domains, and MAC address learning** by observing real packet flow in Packet Tracer.

The lab is divided into two parts:
- **Network 1** uses a **hub**
- **Network 2** uses a **switch**

All devices are assumed to be freshly rebooted.

---

## Network 1 – Hub-Based Network
Network 1 consists of four PCs (PC1 to PC4) connected using a **hub**.

### What happens when PC1 pings PC4
When PC1 sends traffic to PC4:
- PC1 first sends an **ARP broadcast** to find PC4’s MAC address.
- Because a hub works at **Layer 1**, it does not understand MAC addresses.
- The hub **forwards the packet to all connected PCs**.

### Who receives the packet?
- PC2, PC3, and PC4 all receive the packet.
- Only PC4 processes it; others simply discard it.

### Return traffic (PC4 to PC1)
- The reply from PC4 is again sent to the hub.
- The hub floods the traffic to **all devices**, including PC1, PC2, and PC3.

### Key observation
- Every device sees every packet.
- There is **one collision domain**.
- There is **one broadcast domain**.

---

## Network 2 – Switch-Based Network
Network 2 consists of four PCs (PC5 to PC8) connected using a **switch**.

### Initial ping (PC5 to PC8)
Since the switch has just rebooted:
- The switch’s MAC address table is empty.
- PC5 sends an **ARP broadcast**.
- The switch floods this broadcast to all ports.

### MAC address learning
- The switch learns the MAC address of PC5 from the incoming frame.
- When PC8 replies, the switch learns PC8’s MAC address.

### After MAC learning
- Any further communication between PC5 and PC8 is sent **only to the correct port**.
- Other PCs do not receive the traffic.

### Key observation
- Traffic is **not flooded after MAC learning**.
- Each port is a **separate collision domain**.
- There is still **one broadcast domain**.

---

## Broadcast Domain Comparison
- **Network 1 (Hub):** 1 broadcast domain
- **Network 2 (Switch):** 1 broadcast domain

Broadcast domains are the same because no router or VLAN is used.

---

## Collision Domain Comparison
- **Network 1 (Hub):** 1 collision domain (shared by all PCs)
- **Network 2 (Switch):** 4 collision domains (one per port)

---
