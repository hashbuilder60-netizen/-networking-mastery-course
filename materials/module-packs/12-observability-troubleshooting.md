# Material Pack: Module 12: Observability and Troubleshooting

## Objectives (Expanded)

- Use structured troubleshooting methodologies.
- Correlate logs, metrics, flows, and packet traces.
- Produce high-quality incident reports and RCAs.

## Lesson Breakdown with Teaching Notes

1. Top-down, bottom-up, divide-and-conquer workflows
2. Telemetry: SNMP, NetFlow/sFlow/IPFIX, syslog
3. SLA/SLO concepts for network reliability
4. War-room communication and escalation
5. Post-incident review and prevention tracking

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

- Lab 1: End-to-end outage simulation
- Lab 2: Packet+flow correlation exercise
- Stretch Lab: RCA report from raw incident data

### Lab Evidence Checklist

- Topology screenshot or diagram.
- Addressing and interface mapping.
- Config snippets per device.
- Verification command output.
- One injected failure and recovery notes.

## Troubleshooting Patterns

- Drill A: Intermittent packet loss across WAN path
- Drill B: Broadcast storm diagnosis and isolation

### Fast Isolation Workflow

1. Confirm scope: single host, VLAN, site, or global.
2. Validate Layer 1/2 state before deep protocol analysis.
3. Confirm routing and return path symmetry.
4. Validate service dependencies (DNS, DHCP, auth, time).
5. Capture evidence and document root cause.

## Command and Tool Kit

- `show logging`
- `show interfaces counters errors`
- `show processes cpu`
- `tcpdump -nn -i <if>`
- `flow-export query`

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
