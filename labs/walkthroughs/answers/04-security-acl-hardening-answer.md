# Walkthrough 04 Solved: Security ACL and Hardening

## Expected End State

- ACL enforces least privilege according to flow matrix.
- Guest VLAN blocked from internal server networks.
- Management access restricted to trusted admin subnet.
- Device logging captures deny events for audit.

## Reference ACL Pattern

```bash
ip access-list extended USERS_TO_APP
 permit tcp 10.10.10.0 0.0.0.255 10.10.20.0 0.0.0.255 eq 443
 deny ip 10.10.30.0 0.0.0.255 10.10.0.0 0.0.255.255
 permit ip any any
```

## Verification

```bash
show access-lists
show ip interface
show logging
```

- Hit counters increment on expected rules.
- Allowed flows succeed.
- Denied flows fail according to policy intent.

## Failure Injection and Recovery

1. Add broad deny above permit line.
2. Observe app outage for users.
3. Reorder ACL to restore intended permit first.
4. Verify counters and business app recovery.
