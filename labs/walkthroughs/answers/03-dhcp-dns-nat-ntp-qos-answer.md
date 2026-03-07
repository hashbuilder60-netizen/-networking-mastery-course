# Walkthrough 03 Solved: DHCP, DNS, NAT, NTP, QoS

## Expected End State

- Clients receive correct IP, gateway, and DNS from DHCP.
- DNS resolves application FQDNs.
- NAT translations appear for internet-bound traffic.
- NTP reports synchronized clock.
- QoS policy counters increase for prioritized class.

## Core Validation Commands

```bash
show ip dhcp binding
show ip nat translations
show ip nat statistics
show ntp status
show policy-map interface
```

## Dependency Test Order

1. Verify DHCP lease details.
2. Verify DNS response for known domain.
3. Verify internet flow and NAT translation creation.
4. Verify NTP sync state.
5. Verify QoS class counters for marked traffic.

## Failure Injection and Recovery

1. Disable DHCP relay on VLAN interface.
2. Observe client renewal failure.
3. Re-enable relay and verify lease recovery.
4. Capture before/after evidence.
