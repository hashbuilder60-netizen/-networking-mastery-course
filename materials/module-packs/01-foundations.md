# Material Pack: Module 01: Networking Foundations

## Objectives (Expanded)

- Explain what networks are and why they matter.
- Differentiate LAN, WAN, MAN, WLAN, PAN, SAN.
- Describe network topologies, media, and device roles.
- Understand packet flow between hosts in a basic LAN.

## Lesson Breakdown with Teaching Notes

1. Network purpose, business value, and reliability concepts
2. Network components: routers, switches, firewalls, APs, NICs
3. Physical media: UTP, fiber, transceivers, connectors, speed/duplex
4. Topology models: star, mesh, spine-leaf, hub-and-spoke
5. Basic CLI orientation and documentation discipline

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

- Lab 1: Build a 2-switch, 2-router baseline topology
- Lab 2: Identify devices, interfaces, and cable types
- Stretch Lab: Capture first ping with Wireshark and annotate headers

### Lab Evidence Checklist

- Topology screenshot or diagram.
- Addressing and interface mapping.
- Config snippets per device.
- Verification command output.
- One injected failure and recovery notes.

## Troubleshooting Patterns

- Drill A: Host cannot reach default gateway
- Drill B: Speed/duplex mismatch causing packet loss

### Fast Isolation Workflow

1. Confirm scope: single host, VLAN, site, or global.
2. Validate Layer 1/2 state before deep protocol analysis.
3. Confirm routing and return path symmetry.
4. Validate service dependencies (DNS, DHCP, auth, time).
5. Capture evidence and document root cause.

## Command and Tool Kit

- `show ip interface brief`
- `show interfaces status`
- `show mac address-table`
- `ping <gateway>`
- `traceroute <host>`

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
