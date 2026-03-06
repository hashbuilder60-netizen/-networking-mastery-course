# Material Pack: Module 07: Core Network Services

## Objectives (Expanded)

- Configure and validate DHCP, DNS, NAT, and NTP.
- Implement foundational QoS classification and queuing.
- Understand service dependencies and failure cascades.

## Lesson Breakdown with Teaching Notes

1. DHCP DORA, relay, exclusions, and leases
2. DNS recursion, caching, and split horizon
3. NAT types: static, dynamic, PAT, and limitations
4. NTP hierarchy and time sync troubleshooting
5. QoS terminology: classification, marking, queueing, policing

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

- Lab 1: DHCP relay across VLANs
- Lab 2: NAT overload for branch internet edge
- Stretch Lab: QoS marking and traffic class verification

### Lab Evidence Checklist

- Topology screenshot or diagram.
- Addressing and interface mapping.
- Config snippets per device.
- Verification command output.
- One injected failure and recovery notes.

## Troubleshooting Patterns

- Drill A: DHCP starvation or lease exhaustion
- Drill B: NAT translations exist but sessions fail

### Fast Isolation Workflow

1. Confirm scope: single host, VLAN, site, or global.
2. Validate Layer 1/2 state before deep protocol analysis.
3. Confirm routing and return path symmetry.
4. Validate service dependencies (DNS, DHCP, auth, time).
5. Capture evidence and document root cause.

## Command and Tool Kit

- `show ip dhcp binding`
- `show ip nat translations`
- `show ntp status`
- `show access-lists`
- `show policy-map interface`

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
