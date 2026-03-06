# Packet Tracer Labs

## PT-01 Basic LAN
- Build: 1 router, 1 switch, 2 PCs
- Goal: End-to-end ping, gateway validation
- Validate: ARP table, MAC table, interface status

## PT-02 VLANs and Trunks
- Build: 2 switches, 4 PCs, 2 VLANs
- Goal: Isolate broadcast domains, trunk between switches
- Validate: `show vlan brief`, `show interfaces trunk`

## PT-03 Inter-VLAN Routing
- Build: Router-on-a-stick and SVI options
- Goal: Enable communication between VLANs
- Validate: Default gateway per VLAN, routing table entries

## PT-04 Intro OSPF
- Build: 3 routers line topology
- Goal: Form neighbors and exchange routes
- Validate: `show ip ospf neighbor`, `show ip route ospf`
