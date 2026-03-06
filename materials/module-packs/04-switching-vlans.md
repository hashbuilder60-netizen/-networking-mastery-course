# Material Pack: Module 04: Switching, VLANs, STP, and EtherChannel

## Objectives (Expanded)

- Configure VLAN segmentation and trunks correctly.
- Implement STP safely and tune root bridge roles.
- Build EtherChannel and verify load distribution.

## Lesson Breakdown with Teaching Notes

1. MAC learning, CAM tables, forwarding decisions
2. VLAN access/trunk ports and tagging standards
3. Inter-VLAN routing: SVI vs router-on-a-stick
4. STP, RSTP, root election, port states/roles
5. LACP vs PAgP and channel consistency checks

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

- Lab 1: Multi-VLAN campus access design
- Lab 2: STP failover timing comparison lab
- Stretch Lab: LACP bundle build and misconfig recovery

### Lab Evidence Checklist

- Topology screenshot or diagram.
- Addressing and interface mapping.
- Config snippets per device.
- Verification command output.
- One injected failure and recovery notes.

## Troubleshooting Patterns

- Drill A: Native VLAN mismatch and traffic leakage
- Drill B: Unidirectional link causing STP instability

### Fast Isolation Workflow

1. Confirm scope: single host, VLAN, site, or global.
2. Validate Layer 1/2 state before deep protocol analysis.
3. Confirm routing and return path symmetry.
4. Validate service dependencies (DNS, DHCP, auth, time).
5. Capture evidence and document root cause.

## Command and Tool Kit

- `show vlan brief`
- `show interfaces trunk`
- `show spanning-tree`
- `show etherchannel summary`
- `show mac address-table dynamic`

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
