# Material Pack: Module 13: WAN, MPLS, and VPN Technologies

## Objectives (Expanded)

- Understand WAN architecture choices and tradeoffs.
- Configure site-to-site VPN concepts and policy intent.
- Compare MPLS, DIA, and SD-WAN strategies.

## Lesson Breakdown with Teaching Notes

1. WAN links, SLAs, latency, and QoS over distance
2. IPSec concepts: IKE phases, transforms, tunnels
3. DMVPN/SD-WAN high-level architecture
4. MPLS L3VPN fundamentals (provider view)
5. Branch resiliency and path steering

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

- Lab 1: Dual-WAN branch design with failover policy
- Lab 2: IPSec tunnel validation scenario
- Stretch Lab: WAN QoS marking and policy checks

### Lab Evidence Checklist

- Topology screenshot or diagram.
- Addressing and interface mapping.
- Config snippets per device.
- Verification command output.
- One injected failure and recovery notes.

## Troubleshooting Patterns

- Drill A: Tunnel up but no interesting traffic
- Drill B: MTU/fragmentation issues over VPN

### Fast Isolation Workflow

1. Confirm scope: single host, VLAN, site, or global.
2. Validate Layer 1/2 state before deep protocol analysis.
3. Confirm routing and return path symmetry.
4. Validate service dependencies (DNS, DHCP, auth, time).
5. Capture evidence and document root cause.

## Command and Tool Kit

- `show crypto isakmp sa`
- `show crypto ipsec sa`
- `show interface tunnel`
- `show ip sla statistics`
- `show track`

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
