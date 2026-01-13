
# Router on a Stick (Inter-VLAN Routing)
   
   <img width="1539" height="570" alt="image" src="https://github.com/user-attachments/assets/411375f3-a854-46fc-bbc2-00731c042c3e" />



## About this lab
In this lab, I practiced **Router on a Stick** to allow communication between two different VLANs.  
The idea is simple: PCs are placed in separate VLANs, and a single router interface is used to route traffic between them using subinterfaces.

---

## Network Setup
The topology includes:
- One router
- One switch
- Two PCs

Both PCs are connected to the switch, and the switch is connected to the router.  
The link between the router and switch is configured as a **trunk** so that multiple VLANs can pass through it.

---

## VLAN and IP Planning
I created the following VLANs and networks:

- **VLAN 1** → `10.1.1.0/24` (management)
- **VLAN 10** → `10.1.10.0/24`
- **VLAN 20** → `10.1.20.0/24`

The router uses the **last usable IP address** in each subnet and works as the default gateway for the PCs.

- Switch management IP: `10.1.1.253/24`
- PC1 (VLAN 10): `10.1.10.1`
- PC2 (VLAN 20): `10.1.20.2`

---

## What I Configured

### On the Switch
- Created VLAN 10 and VLAN 20
- Assigned PC1 to VLAN 10
- Assigned PC2 to VLAN 20
- Configured the port connected to the router as a trunk

### On the Router
- Created subinterfaces for VLAN 1, VLAN 10, and VLAN 20
- Assigned IP addresses to each subinterface
- Enabled routing between VLANs

---

## Testing the Network
After completing the configuration:
- PC1 and PC2 received correct IP addresses
- PC1 was able to **ping PC2 successfully**
- This confirmed that inter-VLAN routing was working properly

---

## What I Learned from This Lab
- How Router on a Stick works in real networks
- Why trunk links are required between router and switch
- How VLANs are routed using router subinterfaces
- How to verify inter-VLAN connectivity using ping

---
