# DHCP Configuration Using Router

<img width="852" height="564" alt="Screenshot 2026-01-13 125735" src="https://github.com/user-attachments/assets/04d80567-8bb4-45a0-b31d-807cd8941a47" />


## What this lab is about
In this lab, I configured **Router1 as a DHCP server** so that a PC can get its IP address automatically.  
The setup uses a router, a multilayer switch, and a PC, and the main focus is to understand how DHCP works in a basic network.

---

## Topology Overview
- Router: **ISR4321 (Router1)**
- Switch: **3650-24PS Multilayer Switch**
- End device: **PC**
- Network used: `10.1.1.0/24`

The router is connected to the switch, and the switch connects to the PC.

---

## DHCP Setup on Router1
DHCP is configured directly on Router1 with these settings:

- IP addresses from `10.1.1.1` to `10.1.1.100` are excluded so they can be used for network devices.
- A DHCP pool named **pc** is created.
- Network is set to `10.1.1.0/24`.
- Router1 is configured as both the **default gateway** and **DNS server**.

This allows the PC to receive all required network information automatically.

---

## How IP Assignment Works
When the PC is turned on:
1. It sends a DHCP request.
2. Router1 responds with an available IP address.
3. The PC receives its IP address, subnet mask, gateway, and DNS details.

No manual IP configuration is required on the PC.

---

## Testing & Verification
To verify the configuration:
- The PC successfully receives an IP address via DHCP.
- The PC is able to **ping the loopback interface of Router1**.
- Successful ping confirms that DHCP and connectivity are working properly.

---
