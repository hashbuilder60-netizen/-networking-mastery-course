# Material Pack: Module 05: Routing (Static, OSPF, and Intro to BGP)

## Objectives (Expanded)

- Configure static and default routes with tracking.
- Deploy OSPF single and multi-area topologies.
- Explain BGP purpose and basic path selection concepts.

## Lesson Breakdown with Teaching Notes

1. Routing tables, recursive lookup, and administrative distance
2. Static/floating static routes and failover logic
3. OSPF neighbors, LSAs, DR/BDR, SPF calculation
4. Route filtering, summarization, and redistribution concepts
5. BGP fundamentals and enterprise edge overview

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

- Lab 1: OSPF adjacency from scratch
- Lab 2: Area design with ABR summarization
- Stretch Lab: Policy-based route filtering mini-lab

### Lab Evidence Checklist

- Topology screenshot or diagram.
- Addressing and interface mapping.
- Config snippets per device.
- Verification command output.
- One injected failure and recovery notes.

## Troubleshooting Patterns

- Drill A: OSPF neighbor stuck in EXSTART/EXCHANGE
- Drill B: Route present but traffic blackholed

### Fast Isolation Workflow

1. Confirm scope: single host, VLAN, site, or global.
2. Validate Layer 1/2 state before deep protocol analysis.
3. Confirm routing and return path symmetry.
4. Validate service dependencies (DNS, DHCP, auth, time).
5. Capture evidence and document root cause.

## Command and Tool Kit

- `show ip route`
- `show ip ospf neighbor`
- `show ip ospf database`
- `show ip protocols`
- `show ip route ospf`

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
