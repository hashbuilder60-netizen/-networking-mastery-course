# Material Pack: Module 09: Network Security and Hardening

## Objectives (Expanded)

- Apply layered security controls in campus/branch networks.
- Build ACL and segmentation policy with least privilege.
- Harden network device management plane.

## Lesson Breakdown with Teaching Notes

1. Threat models and attack surfaces for networks
2. ACL design logic, ordering, and verification
3. AAA concepts: TACACS+, RADIUS, local fallback
4. Port security, DHCP snooping, DAI, IP source guard
5. Management hardening: SSH, SNMPv3, logging, banners

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

- Lab 1: ACL policy implementation challenge
- Lab 2: L2 security features against spoofing attacks
- Stretch Lab: Secure management plane baseline

### Lab Evidence Checklist

- Topology screenshot or diagram.
- Addressing and interface mapping.
- Config snippets per device.
- Verification command output.
- One injected failure and recovery notes.

## Troubleshooting Patterns

- Drill A: ACL shadow rule blocks business app
- Drill B: Control-plane policing too strict

### Fast Isolation Workflow

1. Confirm scope: single host, VLAN, site, or global.
2. Validate Layer 1/2 state before deep protocol analysis.
3. Confirm routing and return path symmetry.
4. Validate service dependencies (DNS, DHCP, auth, time).
5. Capture evidence and document root cause.

## Command and Tool Kit

- `show access-lists`
- `show aaa sessions`
- `show port-security interface`
- `show ip dhcp snooping binding`
- `show logging`

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
