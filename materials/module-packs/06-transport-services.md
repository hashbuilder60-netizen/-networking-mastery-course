# Material Pack: Module 06: Transport Layer and Service Behavior

## Objectives (Expanded)

- Contrast TCP and UDP under real network conditions.
- Interpret ports, sockets, and session behavior.
- Diagnose retransmissions, latency, and handshake issues.

## Lesson Breakdown with Teaching Notes

1. TCP handshake, flags, flow control, and retransmission
2. UDP behavior and real-time application tradeoffs
3. Common ports and service mapping
4. Session persistence and load balancing basics
5. Impact of latency, jitter, packet loss on apps

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

- Lab 1: Packet capture of web transaction
- Lab 2: Simulate delay/loss and observe TCP adaptation
- Stretch Lab: Troubleshoot service reachability with tools

### Lab Evidence Checklist

- Topology screenshot or diagram.
- Addressing and interface mapping.
- Config snippets per device.
- Verification command output.
- One injected failure and recovery notes.

## Troubleshooting Patterns

- Drill A: Three-way handshake fails intermittently
- Drill B: DNS works but app still unavailable

### Fast Isolation Workflow

1. Confirm scope: single host, VLAN, site, or global.
2. Validate Layer 1/2 state before deep protocol analysis.
3. Confirm routing and return path symmetry.
4. Validate service dependencies (DNS, DHCP, auth, time).
5. Capture evidence and document root cause.

## Command and Tool Kit

- `netstat -an`
- `ss -lntup`
- `tcpdump -nn`
- `curl -v <url>`
- `telnet <host> <port>`

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
