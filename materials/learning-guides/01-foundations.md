# Learning Guide: Module 01 - Networking Foundations

## Why This Module Matters

This module gives learners the mental model for how devices communicate and where failures usually start.

## Core Concepts

- A network is a system of connected nodes exchanging frames/packets under specific rules called protocols.
- End hosts send traffic to local peers directly, but remote traffic must be sent to the default gateway.
- Switches forward frames using MAC learning while routers forward packets using longest-prefix route lookup.
- Physical layers (cables, optics, speed/duplex) strongly affect reliability; many outages are Layer 1 or 2.
- Good operators build a baseline: interface states, expected latency, expected route paths, and service health.

## Worked Example

Worked Example: Host A (10.10.10.11/24) pings Host B (10.10.20.22/24). Host A sees Host B is remote, ARPs for the default gateway MAC, sends frame to gateway, router routes to 10.10.20.0/24, and forwards to Host B subnet.

## Commands to Practice

- show ip interface brief
- show interfaces status
- show mac address-table
- show cdp neighbors detail
- ping <gateway>
- traceroute <remote-host>

## Step-by-Step Lab Drill

1. Build 1 router, 2 switches, 4 PCs.
1. Assign IPs and default gateways.
1. Verify same-VLAN and inter-VLAN traffic behavior.
1. Disconnect one uplink and observe failure symptoms.
1. Restore and confirm convergence.

## Troubleshooting Scenario

**Scenario:** Symptom: Users can reach local printers but not internet apps.

**Fix Workflow:**

1. Check default gateway on affected hosts.
1. Check SVI or routed interface status on gateway device.
1. Confirm default route on edge router.
1. Validate NAT and DNS after routing is restored.

## Knowledge Check

### Q1
Why does remote traffic need a gateway?
**Answer:** Because the host has no direct L2 path to remote subnet.

### Q2
What does a switch learn in its CAM table?
**Answer:** Source MAC and ingress port per VLAN.

### Q3
Why is baseline documentation important?
**Answer:** It lets you quickly detect abnormal behavior.

### Q4
What does duplex mismatch cause?
**Answer:** CRC errors, retransmissions, and poor throughput.

### Q5
Which layer usually fails first physically?
**Answer:** Layer 1 (cabling/transceiver/power).

