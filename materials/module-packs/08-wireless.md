# Material Pack: Module 08: Wireless Networking

## Objectives (Expanded)

- Understand RF fundamentals and WLAN architecture.
- Design secure SSID/VLAN mapping and roaming strategy.
- Troubleshoot common wireless performance issues.

## Lesson Breakdown with Teaching Notes

1. RF basics: channel width, overlap, SNR, interference
2. 802.11 standards and modern Wi-Fi design
3. Controller-based vs controllerless models
4. Authentication: WPA2/WPA3 Enterprise and guest access
5. Site survey fundamentals and capacity planning

### What To Emphasize

- Tie every concept to packet flow and business impact.
- Validate every configuration with at least two independent checks.
- Distinguish control-plane problems from data-plane problems.
- Document baseline behavior before introducing changes.

### Common Misunderstandings

- Confusing reachability with service availability.
- Assuming protocol adjacency equals healthy application flow.
- Skipping rollback planning before change implementation.
- Relying on one command output instead of triangulating evidence.

## Lab Execution Pack

- Lab 1: Dual-SSID deployment with role-based VLANs
- Lab 2: Channel planning and overlap reduction
- Stretch Lab: Roaming validation walkthrough

### Lab Evidence Checklist

- Topology screenshot or diagram.
- Addressing and interface mapping.
- Config snippets per device.
- Verification command output.
- One injected failure and recovery notes.

## Troubleshooting Patterns

- Drill A: Sticky clients and low data rates
- Drill B: Co-channel interference causing throughput collapse

### Fast Isolation Workflow

1. Confirm scope: single host, VLAN, site, or global.
2. Validate Layer 1/2 state before deep protocol analysis.
3. Confirm routing and return path symmetry.
4. Validate service dependencies (DNS, DHCP, auth, time).
5. Capture evidence and document root cause.

## Command and Tool Kit

- `show wlan summary`
- `show ap summary`
- `show client summary`
- `show wireless stats`
- `show radius statistics`

## Review Questions

- Which concept in this module has the highest operational risk if misconfigured?
- What would fail first if one key dependency broke?
- Which verification command gives you the fastest confidence signal?
- How would you explain this module to a junior engineer in 3 minutes?
- Which logs or counters would you collect during an outage?
- What preventive control would reduce repeat incidents?

## Performance Standard

- Rebuild the lab from memory in under 45 minutes.
- Diagnose one injected fault in under 20 minutes.
- Explain root cause and fix path in clear operational language.
