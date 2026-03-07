# Walkthrough 01: Campus VLAN + Inter-VLAN Routing

## Goal

Build a small campus network with user, server, and guest VLANs and secure inter-VLAN communication.

## Topology

- SW1, SW2 (access)
- DSW1 (distribution)
- R1 (edge)
- PC-USER, PC-GUEST, SERVER

## VLAN Plan

- VLAN 10 USERS 10.10.10.0/24
- VLAN 20 SERVERS 10.10.20.0/24
- VLAN 30 GUEST 10.10.30.0/24

## Config (distribution switch)

```bash
vlan 10
 name USERS
vlan 20
 name SERVERS
vlan 30
 name GUEST

interface vlan 10
 ip address 10.10.10.1 255.255.255.0
 no shutdown
interface vlan 20
 ip address 10.10.20.1 255.255.255.0
 no shutdown
interface vlan 30
 ip address 10.10.30.1 255.255.255.0
 no shutdown

ip routing
```

## Verification

```bash
show vlan brief
show interfaces trunk
show ip interface brief
show ip route
ping 10.10.20.10
```

## Failure Drill

Remove VLAN 20 from one trunk allowed list and observe server outage from USER VLAN.
