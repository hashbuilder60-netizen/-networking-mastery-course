# Learning Guide: Module 02 - OSI, TCP/IP, and Encapsulation

## Why This Module Matters

Learners need layer-based troubleshooting so they do not guess randomly during outages.

## Core Concepts

- Encapsulation adds headers as data moves down the stack: application data -> segment -> packet -> frame -> bits.
- Decapsulation removes headers at receiving host; intermediate routers replace only Layer 2 framing hop by hop.
- OSI model is conceptual, TCP/IP model maps better to real systems, and both are useful operationally.
- Failure at one layer can look like another: DNS outage (app layer) can be mistaken for routing issue.
- MTU and PMTUD problems commonly break specific applications while pings still appear normal.

## Worked Example

Worked Example: HTTPS request sends TCP SYN to port 443, completes handshake, then exchanges TLS records. If return SYN-ACK is blocked, app reports timeout even though DNS and routing may be correct.

## Commands to Practice

- ping <host>
- traceroute <host>
- telnet <host> <port>
- nslookup <name>
- show interfaces mtu
- tcpdump -nn

## Step-by-Step Lab Drill

1. Capture a web session packet trace.
1. Identify L2/L3/L4 headers in order.
1. Lower MTU on one path segment.
1. Test with small and large payloads.
1. Document where communication fails.

## Troubleshooting Scenario

**Scenario:** Symptom: Small packets succeed, file uploads fail.

**Fix Workflow:**

1. Test path MTU with DF-bit probes.
1. Check firewall ICMP fragmentation-needed behavior.
1. Align MTU/MSS across tunnels and WAN edges.
1. Retest application transactions.

## Knowledge Check

### Q1
What changes at every router hop?
**Answer:** Layer 2 header/trailer.

### Q2
Which layer uses ports?
**Answer:** Transport layer.

### Q3
Why can DNS failure look like network failure?
**Answer:** Apps fail name resolution before connecting.

### Q4
What does PMTUD need to work well?
**Answer:** ICMP feedback from transit devices.

### Q5
What does a TCP RST usually indicate?
**Answer:** Endpoint/policy actively refused connection.

