# Walkthrough 03: DHCP + DNS + NAT + NTP + QoS

## Goal

Deploy core branch services and validate service dependency order.

## Dependency Order

1. DHCP lease and gateway
1. DNS name resolution
1. NAT translation for internet path
1. NTP sync for stable logs
1. QoS for critical app traffic

## Verification Commands

```bash
show ip dhcp binding
show ip nat translations
show ntp status
show policy-map interface
```

## Failure Drill

Disable DHCP relay temporarily and document client symptom progression.
