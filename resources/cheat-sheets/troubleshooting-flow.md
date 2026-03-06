# Troubleshooting Flow Cheat Sheet

## 5-Step Isolation Method

1. Scope the problem.
- Single host, VLAN, site, or global.
- User impact and business impact.

1. Validate transport path.
- Interface up/down state.
- VLAN/trunk or link status.
- Routing and return path.

1. Validate service dependency chain.
- DNS, DHCP, NAT, auth, time sync.
- Application port reachability.

1. Confirm policy and security controls.
- ACL/firewall permit path.
- Segmentation expectations.

1. Prove restoration.
- Before/after verification outputs.
- User-experience confirmation.
- Incident documentation.

## High-Value Commands

```bash
show ip interface brief
show interfaces counters errors
show vlan brief
show interfaces trunk
show ip route
show access-lists
show logging
```
