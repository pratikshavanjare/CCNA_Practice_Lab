<img width="1233" height="746" alt="image" src="https://github.com/user-attachments/assets/d6dff921-968d-4da3-a662-77478ec851e2" />
 
This lab was created to practice **IPv4 subnetting, VLSM, and basic routing concepts** using Cisco Packet Tracer.  
The original network `192.168.1.0/24` is subnetted to support multiple LANs and WAN links while making efficient use of IP addresses.

---

## Network Overview
The topology consists of multiple branch routers connected to a central Internet router.  
Each site has its own LAN with PCs and a switch, while the routers communicate using point-to-point serial links.

- Base network: `192.168.1.0/24`
- Subnetting method: VLSM
- LAN subnets: `/26` and `/28`
- WAN links: `/30`
- Devices used: Cisco R4321 routers and 3650 switches

---


## LAN Subnet Design

### Site 1
- Network: `192.168.1.0/26`
- Used for a larger LAN
- Router configured with the **last usable IP**
- Switch configured with the **second last usable IP**
- Hosts assigned starting from the **first usable IP**

### Site 2
- Network: `192.168.1.128/26`
- Same IP allocation approach as Site 1
- Supports multiple PCs and servers

### Site 3
- Network: `192.168.1.64/28`
- Smaller LAN with fewer hosts
- Router and switch IPs assigned following the same rule

---

## WAN Subnetting
Point-to-point serial links were subnetted using `/30` to avoid wasting IP addresses.

| Connection | Subnet |
|----------|--------|
| R1 to Internet Router | `192.168.1.112/30` |
| R2 to Internet Router | `192.168.1.192/30` |
| R4 to Internet Router | `192.168.1.116/30` |

Each WAN link uses one IP address per router interface.

---

## Internet Access
A central Internet router connects all branch routers.  
Public servers such as **8.8.8.8**, **cisco.com**, and **facebook.com** are simulated in the lab.

- DHCP is configured on the Internet router
- PCs are able to browse external websites successfully

---

