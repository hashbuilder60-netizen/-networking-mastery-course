# Learning Guide: Module 03 - IPv4 and IPv6 Addressing/Subnetting

## Why This Module Matters

Addressing mistakes create silent outages and scaling issues; this module builds design precision.

## Core Concepts

- CIDR uses prefix lengths to define network/host boundaries independent of old classful ranges.
- VLSM assigns different subnet sizes to different segments, preserving address space efficiently.
- Route summarization reduces route table size and control-plane churn between domains.
- IPv6 uses NDP instead of ARP and relies heavily on link-local addressing for neighbor operations.
- Dual-stack means two independent forwarding planes; both must be validated during troubleshooting.

## Worked Example

Worked Example: Split 192.168.10.0/24 into /27 blocks. Each /27 has 32 addresses, 30 usable hosts. Subnets increment by 32: .0, .32, .64, .96, .128, .160, .192, .224.

## Commands to Practice

- show ip route
- show ip interface brief
- show ipv6 interface brief
- show ipv6 neighbors
- ping ipv6 <address>
- show ip protocols

## Step-by-Step Lab Drill

1. Create VLSM plan for HR, Engineering, Voice, Guest.
1. Configure IPv4 and IPv6 addressing on interfaces.
1. Add static routes and default routes.
1. Verify reachability across all subnets.
1. Summarize route blocks at distribution layer.

## Troubleshooting Scenario

**Scenario:** Symptom: Some hosts in same VLAN cannot communicate.

**Fix Workflow:**

1. Check mask mismatch on affected hosts.
1. Check duplicate IP conflicts via ARP/NDP entries.
1. Validate gateway IP belongs to correct subnet.
1. Reassign and retest.

## Knowledge Check

### Q1
How many usable hosts in /27?
**Answer:** 30.

### Q2
Why summarize routes?
**Answer:** Reduce routing scale and instability.

### Q3
What is mandatory on IPv6 interfaces?
**Answer:** Link-local address.

### Q4
Difference between /30 and /31 usage?
**Answer:** /31 supports point-to-point with 2 usable addresses.

### Q5
What does overlap cause?
**Answer:** Ambiguous forwarding and intermittent reachability.

