# Material Pack: Module 03: IPv4/IPv6 Addressing and Subnetting

## Objectives (Expanded)

- Master binary math for subnetting quickly.
- Design IPv4 subnet plans for enterprise segments.
- Configure and verify IPv6 addressing and routing basics.

## Lesson Breakdown with Teaching Notes

1. IPv4 structure, classes vs CIDR, private/public ranges
2. Subnetting, VLSM, summarization, and route aggregation
3. IPv6 format, types, SLAAC, DHCPv6, link-local/global
4. Neighbor Discovery Protocol basics
5. Address planning for campus and branch designs

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

- Lab 1: 20 timed subnetting drills
- Lab 2: Dual-stack lab with static routes
- Stretch Lab: Summarization exercise between area boundaries

### Lab Evidence Checklist

- Topology screenshot or diagram.
- Addressing and interface mapping.
- Config snippets per device.
- Verification command output.
- One injected failure and recovery notes.

## Troubleshooting Patterns

- Drill A: Overlapping subnets causing asymmetric reachability
- Drill B: Wrong IPv6 gateway due to RA behavior

### Fast Isolation Workflow

1. Confirm scope: single host, VLAN, site, or global.
2. Validate Layer 1/2 state before deep protocol analysis.
3. Confirm routing and return path symmetry.
4. Validate service dependencies (DNS, DHCP, auth, time).
5. Capture evidence and document root cause.

## Command and Tool Kit

- `show ip route`
- `show ip interface brief`
- `show ipv6 interface brief`
- `show ipv6 neighbors`
- `ping ipv6 <addr>`

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
