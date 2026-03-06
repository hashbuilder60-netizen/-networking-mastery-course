# Learning Guide: Module 13 - WAN, VPN, and Branch Connectivity

## Why This Module Matters

Branches need resilient, secure transport for business applications under varying link quality.

## Core Concepts

- WAN design balances cost, SLA, latency, and operational complexity.
- IPSec secures traffic with negotiated policies and encryption parameters.
- Path steering should be application-aware, not bandwidth-only.
- Failover health checks must test real reachability, not interface state alone.
- MTU overhead from encapsulation can silently degrade application performance.

## Worked Example

Worked Example: Tunnel is up but ERP still fails because crypto ACL excludes ERP subnet; control tunnel status alone is not proof of data policy correctness.

## Commands to Practice

- show crypto isakmp sa
- show crypto ipsec sa
- show interface tunnel
- show ip sla statistics
- show track
- show policy-map interface

## Step-by-Step Lab Drill

1. Build dual-WAN branch edge topology.
1. Configure primary/backup path policy.
1. Apply IPSec intent between branch and HQ.
1. Simulate primary failure with IP SLA track.
1. Measure recovery time and app impact.

## Troubleshooting Scenario

**Scenario:** Symptom: VPN established but only some subnets pass traffic.

**Fix Workflow:**

1. Validate interesting-traffic selectors on both peers.
1. Check NAT exemption/ordering before encryption.
1. Check routing for encrypted subnets.
1. Retest each subnet pair explicitly.

## Knowledge Check

### Q1
Why can tunnel-up mislead operators?
**Answer:** Data selectors/routes may still be wrong.

### Q2
What should failover probes test?
**Answer:** End-to-end path health.

### Q3
VPN MTU issue symptom?
**Answer:** Large payload failure, fragmentation, retransmits.

### Q4
MPLS advantage?
**Answer:** Predictable provider-managed transport.

### Q5
What secures branch internet breakout?
**Answer:** Policy, filtering, and encrypted sensitive flows.

