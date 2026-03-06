# Learning Guide: Module 07 - Core Services: DHCP, DNS, NAT, NTP, QoS

## Why This Module Matters

Most user-facing outages are service-chain failures, not raw link failures.

## Core Concepts

- DHCP automates address assignment using discover-offer-request-acknowledge flow.
- DNS maps names to IPs and depends on recursive caches and authoritative responses.
- NAT/PAT translates private addresses for external reachability while tracking sessions.
- NTP synchronizes clocks, critical for logs, certificates, and incident correlation.
- QoS classifies/marks traffic so critical applications survive congestion.

## Worked Example

Worked Example: Branch users lose internet after PAT pool exhaustion. Existing sessions continue briefly; new sessions fail until translations age or capacity is expanded.

## Commands to Practice

- show ip dhcp binding
- show ip dhcp pool
- show ip nat translations
- show ip nat statistics
- show ntp status
- show policy-map interface

## Step-by-Step Lab Drill

1. Configure DHCP scope + relay on SVI.
1. Set PAT on edge interface.
1. Configure NTP peers and verify sync.
1. Mark voice traffic DSCP and prioritize.
1. Validate each service dependency in order.

## Troubleshooting Scenario

**Scenario:** Symptom: Users report browser DNS errors.

**Fix Workflow:**

1. Verify DHCP provided DNS server address.
1. Test resolver reachability from client and gateway.
1. Check recursive resolver health and forwarders.
1. Clear stale cache where needed.

## Knowledge Check

### Q1
What is DHCP relay role?
**Answer:** Forwards broadcasts across routed boundaries.

### Q2
Why is NTP operationally critical?
**Answer:** Accurate logs and auth validity.

### Q3
PAT primary advantage?
**Answer:** Many internal hosts share one public IP.

### Q4
What does QoS not do?
**Answer:** It does not create bandwidth; it prioritizes.

### Q5
Why can DNS outage seem global?
**Answer:** Most apps rely on name resolution first.

