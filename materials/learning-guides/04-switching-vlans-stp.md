# Learning Guide: Module 04 - Switching, VLANs, STP, and EtherChannel

## Why This Module Matters

Campus stability depends on controlled Layer 2 behavior, loop prevention, and predictable segmentation.

## Core Concepts

- VLANs isolate broadcast domains and enforce logical segmentation over shared switch fabric.
- Trunk ports carry multiple VLANs using tags; access ports carry one VLAN untagged for endpoint simplicity.
- STP blocks redundant links to prevent loops and broadcast storms; root placement impacts forwarding paths.
- RSTP converges faster than classic STP and is standard in modern enterprise designs.
- EtherChannel bundles links for throughput and resiliency but all member settings must match.

## Worked Example

Worked Example: Two access switches uplink to distribution using LACP bundle. If one member fails, port-channel stays up and traffic continues with reduced bandwidth.

## Commands to Practice

- show vlan brief
- show interfaces trunk
- show spanning-tree
- show spanning-tree vlan <id>
- show etherchannel summary
- show mac address-table dynamic

## Step-by-Step Lab Drill

1. Create VLANs for Users, Voice, Servers, Guest.
1. Configure trunk allowed VLAN list explicitly.
1. Set root primary/secondary for key VLANs.
1. Build LACP bundle between switches.
1. Shut one member link and verify continuity.

## Troubleshooting Scenario

**Scenario:** Symptom: Intermittent connectivity and high CPU on switches.

**Fix Workflow:**

1. Check for STP topology changes and root instability.
1. Find mispatched loop or rogue switch.
1. Enable BPDU Guard on edge ports.
1. Stabilize root placement and retest.

## Knowledge Check

### Q1
Why restrict allowed VLANs on trunks?
**Answer:** Reduce blast radius and leakage risk.

### Q2
What does STP root decide?
**Answer:** Best loop-free tree paths.

### Q3
LACP benefit over static channel?
**Answer:** Negotiation and consistency checks.

### Q4
What can native VLAN mismatch cause?
**Answer:** Unexpected untagged traffic behavior.

### Q5
Why is BPDU Guard valuable?
**Answer:** Protects edge against accidental loop devices.

