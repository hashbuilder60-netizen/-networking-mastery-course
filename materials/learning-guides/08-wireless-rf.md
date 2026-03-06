# Learning Guide: Module 08 - Wireless Networking and RF Operations

## Why This Module Matters

Wireless is shared medium; design quality determines user stability more than raw AP count.

## Core Concepts

- RF planning must account for channel overlap, interference, and client density.
- 2.4 GHz has longer range but fewer non-overlapping channels; 5/6 GHz provides cleaner capacity.
- SSID to VLAN mapping enables policy segmentation for staff, guest, and IoT devices.
- Enterprise auth (802.1X/WPA2-Enterprise/WPA3-Enterprise) improves identity-based access.
- Roaming quality depends on AP placement, power tuning, and controller thresholds.

## Worked Example

Worked Example: Office with many APs on same channel has low throughput. Re-channeling and power tuning reduces co-channel contention and improves airtime fairness.

## Commands to Practice

- show wlan summary
- show ap summary
- show client summary
- show wireless stats
- show radius statistics
- ping <gateway>

## Step-by-Step Lab Drill

1. Deploy staff and guest SSIDs.
1. Map each SSID to correct VLAN.
1. Apply enterprise auth for staff.
1. Tune channels to reduce overlap.
1. Walk-test roaming between AP zones.

## Troubleshooting Scenario

**Scenario:** Symptom: Users have full bars but poor speed.

**Fix Workflow:**

1. Check retry rate and channel utilization.
1. Check co-channel interference.
1. Check client band steering policy.
1. Retune channel/power and reassess.

## Knowledge Check

### Q1
Why can high RSSI still be slow?
**Answer:** Interference/contention can dominate.

### Q2
What is co-channel interference?
**Answer:** APs sharing same channel and airtime.

### Q3
Why separate guest SSID VLAN?
**Answer:** Security and policy isolation.

### Q4
What helps roaming voice clients?
**Answer:** Consistent AP spacing and tuned thresholds.

### Q5
What is airtime fairness?
**Answer:** Balancing medium use across clients.

