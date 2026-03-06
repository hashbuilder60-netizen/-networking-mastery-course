# Material Pack: Module 14: Advanced Enterprise Design

## Objectives (Expanded)

- Produce scalable and resilient enterprise designs.
- Balance security, availability, and cost constraints.
- Document architecture decisions with rationale.

## Lesson Breakdown with Teaching Notes

1. Hierarchical campus and data center patterns
2. Redundancy: FHRP, ECMP, multi-homing
3. Addressing and summarization at scale
4. Segmentation strategies: VRF, VLAN, microsegmentation
5. Operational design: backups, change control, DR

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

- Lab 1: Design review workshop with constraints
- Lab 2: High-availability simulation and failover test
- Stretch Lab: Capacity and growth projection exercise

### Lab Evidence Checklist

- Topology screenshot or diagram.
- Addressing and interface mapping.
- Config snippets per device.
- Verification command output.
- One injected failure and recovery notes.

## Troubleshooting Patterns

- Drill A: Split-brain gateway behavior
- Drill B: Route leak across segmentation boundary

### Fast Isolation Workflow

1. Confirm scope: single host, VLAN, site, or global.
2. Validate Layer 1/2 state before deep protocol analysis.
3. Confirm routing and return path symmetry.
4. Validate service dependencies (DNS, DHCP, auth, time).
5. Capture evidence and document root cause.

## Command and Tool Kit

- `show standby brief`
- `show vrrp brief`
- `show ip route summary`
- `show vrf`
- `show platform capacity`

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
