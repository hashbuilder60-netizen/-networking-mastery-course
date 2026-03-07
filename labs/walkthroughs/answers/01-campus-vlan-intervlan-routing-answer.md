# Walkthrough 01 Solved: Campus VLAN and Inter-VLAN Routing

## Expected End State

- VLAN 10, 20, 30 exist on all required switches.
- Trunks carry only required VLANs.
- SVIs provide default gateway for each VLAN.
- User to server flow allowed; guest to internal services restricted by policy.

## Reference Configuration (distribution switch)

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

interface gigabitEthernet1/0/1
 switchport mode trunk
 switchport trunk allowed vlan 10,20,30
```

## Verification Output Checklist

```bash
show vlan brief
show interfaces trunk
show ip interface brief
show ip route
```

- `show interfaces trunk` lists VLAN 10,20,30 on uplinks.
- `show ip interface brief` shows VLAN SVIs up/up.
- Clients ping gateway and authorized destinations.

## Failure Injection and Recovery

1. Remove VLAN 20 from one trunk allow list.
2. Observe server access failure from VLAN 10 clients.
3. Restore VLAN 20 on trunk and verify traffic recovery.
4. Document symptom, root cause, and corrective action.
