# Learning Guide: Module 06 - Transport Layer Behavior (TCP/UDP)

## Why This Module Matters

Application experience depends heavily on transport mechanics and path quality.

## Core Concepts

- TCP provides reliability via sequence numbers, ACKs, retransmission, and flow/congestion control.
- UDP is connectionless and minimal overhead, often preferred for real-time streams and telemetry.
- Port numbers multiplex services on one host and help firewalls apply policy.
- Latency, jitter, and loss influence user experience differently for each application type.
- Reachability alone is not service health; socket and handshake checks are required.

## Worked Example

Worked Example: User can ping server but cannot load web app. Ping checks ICMP path, but web app needs TCP 443 session and backend dependencies.

## Commands to Practice

- netstat -an
- ss -lntup
- tcpdump -nn
- curl -v <url>
- telnet <host> <port>
- wireshark

## Step-by-Step Lab Drill

1. Capture TCP three-way handshake.
1. Simulate packet loss and observe retransmits.
1. Test UDP stream under jitter.
1. Compare user experience across conditions.
1. Document transport-level evidence.

## Troubleshooting Scenario

**Scenario:** Symptom: Random app slowness under peak traffic.

**Fix Workflow:**

1. Check retransmission and out-of-order trends.
1. Check interface drops/queue behavior.
1. Apply QoS for critical flows.
1. Retest with controlled load.

## Knowledge Check

### Q1
What does SYN-SYN/ACK-ACK do?
**Answer:** Establish TCP session state.

### Q2
Why can UDP sound/video be choppy?
**Answer:** No retransmission and jitter sensitivity.

### Q3
What indicates a closed service port?
**Answer:** TCP RST or connection refused.

### Q4
Why might ping pass while app fails?
**Answer:** Different protocol/port path.

### Q5
What does high RTT do to TCP throughput?
**Answer:** Reduces effective window utilization.

