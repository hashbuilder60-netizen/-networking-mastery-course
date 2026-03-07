# Walkthrough 04: Security ACL and Hardening

## Goal

Implement least-privilege ACLs and secure management plane.

## Policy Example

- USERS can reach APP on TCP 443
- GUEST cannot reach internal server networks
- Management VLAN can SSH to devices

## ACL Sketch

```bash
ip access-list extended USERS_TO_APP
 permit tcp 10.10.10.0 0.0.0.255 10.10.20.0 0.0.0.255 eq 443
 deny ip 10.10.30.0 0.0.0.255 10.10.0.0 0.0.255.255
 permit ip any any
```

## Verification

```bash
show access-lists
show logging
```

## Failure Drill

Introduce a shadow deny above permit and fix using hit counters.
