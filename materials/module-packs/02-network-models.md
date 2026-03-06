# Material Pack: Module 02: OSI, TCP/IP, and Encapsulation

## Objectives (Expanded)

- Map protocols to OSI and TCP/IP layers.
- Explain encapsulation/decapsulation precisely.
- Predict how failures map to specific layers.

## Lesson Breakdown with Teaching Notes

1. OSI model deep dive with practical examples
2. TCP/IP model and modern stack behavior
3. PDU transitions: data, segment, packet, frame, bits
4. Control plane vs data plane concepts
5. MTU, MSS, fragmentation, and PMTUD fundamentals

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

- Lab 1: Trace packet headers through each layer
- Lab 2: Demonstrate MTU mismatch and recovery
- Stretch Lab: Protocol identification challenge from captures

### Lab Evidence Checklist

- Topology screenshot or diagram.
- Addressing and interface mapping.
- Config snippets per device.
- Verification command output.
- One injected failure and recovery notes.

## Troubleshooting Patterns

- Drill A: Application works locally but fails remotely
- Drill B: PMTUD blackhole symptoms

### Fast Isolation Workflow

1. Confirm scope: single host, VLAN, site, or global.
2. Validate Layer 1/2 state before deep protocol analysis.
3. Confirm routing and return path symmetry.
4. Validate service dependencies (DNS, DHCP, auth, time).
5. Capture evidence and document root cause.

## Command and Tool Kit

- `ping <host>`
- `traceroute <host>`
- `telnet <host> <port>`
- `nslookup <name>`
- `show interfaces mtu`

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
