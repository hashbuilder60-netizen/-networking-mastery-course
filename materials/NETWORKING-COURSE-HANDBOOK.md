# Networking Course Handbook (Learnable Content)

This handbook is the core teaching text for the repository. Read in order from Chapter 1 to Chapter 15.

## How to Use This Handbook

1. Read the chapter theory.
1. Run the chapter command walkthrough.
1. Build the matching lab in `labs/walkthroughs`.
1. Break one thing intentionally.
1. Fix it and explain root cause in your own words.

---

## Chapter 1: Networking Foundations

### What a network actually is

A network is a forwarding system made of endpoints and intermediary devices.
Endpoints create and consume data. Intermediary devices decide where data goes next.
All networking problems are some combination of these five dimensions:

- addressing
- forwarding decision
- policy decision
- physical transport quality
- service dependency

### Device roles

- Switch: forwards frames inside a Layer 2 broadcast domain.
- Router: forwards packets between Layer 3 networks.
- Firewall: permits or denies traffic according to policy.
- Access Point: bridges wireless clients into wired network segments.

### Command walkthrough

```bash
show ip interface brief
show interfaces status
show mac address-table
show cdp neighbors detail
ping 10.10.10.1
traceroute 8.8.8.8
```

### What good output looks like

- Interfaces required for traffic are up/up.
- MAC table is learning expected host MACs on expected ports.
- Neighbor table reflects expected topology.
- Ping shows stable latency with zero loss on local segment.

### Common failure pattern

If local pings work but remote pings fail, default gateway or routing path is usually wrong.

---

## Chapter 2: OSI/TCP-IP and Encapsulation

### Why layering matters

Layering gives you a troubleshooting map. Without it, you guess.
Use this sequence every time:

1. physical and link health
1. local IP configuration
1. route path and return path
1. transport handshake
1. application dependency

### Encapsulation path

- Application creates data.
- Transport wraps segment header.
- Network wraps IP header.
- Data link wraps frame header/trailer.
- Physical transmits bits.

At every router hop, Layer 2 headers are rewritten. Layer 3 source and destination usually remain end-to-end.

### Command walkthrough

```bash
ping 10.20.20.10
traceroute 10.20.20.10
telnet 10.20.20.10 443
nslookup app.internal.local
show interfaces mtu
```

### Failure pattern

Small packets work, larger app transactions fail:

- MTU mismatch
- blocked ICMP fragmentation-needed
- tunnel overhead not accounted for

---

## Chapter 3: Addressing and Subnetting (IPv4 and IPv6)

### IPv4 subnet logic

Given prefix length `/p`:

- total addresses = `2^(32-p)`
- usable host addresses (typical LAN) = `2^(32-p) - 2`

Example `/27`:

- total 32
- usable 30
- block size 32

### Fast VLSM workflow

1. list required host counts biggest to smallest
1. assign smallest prefix that fits each requirement
1. place largest networks first
1. reserve summary space
1. document gateways and growth buffer

### IPv6 operational notes

- link-local exists on every interface
- NDP replaces ARP
- dual-stack means you must validate IPv4 and IPv6 separately

### Command walkthrough

```bash
show ip route
show ip interface brief
show ipv6 interface brief
show ipv6 neighbors
ping ipv6 2001:db8:10::1
```

---

## Chapter 4: Switching, VLANs, STP, EtherChannel

### VLAN and trunk essentials

VLANs separate broadcast domains.
Trunks carry multiple VLANs between switches.
Never allow all VLANs by default on every trunk in production designs.

### STP logic

STP prevents loops by blocking selected redundant paths.
Root placement should be intentional, usually distribution/core layer.

### EtherChannel logic

Bundle links with LACP when possible.
All member links must match speed/duplex/VLAN/trunk settings.

### Command walkthrough

```bash
show vlan brief
show interfaces trunk
show spanning-tree
show spanning-tree vlan 10
show etherchannel summary
```

### Failure pattern

Native VLAN mismatch can create strange traffic behavior and security risk.

---

## Chapter 5: Routing, OSPF, and BGP Intro

### Forwarding decision order

Routers select route by:

1. longest prefix match
1. administrative distance
1. protocol metric

### OSPF essentials

OSPF forms neighbors, exchanges LSAs, builds LSDB, then computes SPF tree.
If neighbors are down, no OSPF routes will be learned regardless of config intent.

### BGP at edge

BGP is policy routing for inter-domain connectivity.
Use it when you need controlled internet path policy or multi-provider strategy.

### Command walkthrough

```bash
show ip route
show ip ospf neighbor
show ip ospf database
show ip protocols
show ip bgp summary
```

---

## Chapter 6: Transport Behavior (TCP and UDP)

### TCP

TCP provides reliability through sequence numbers, acknowledgments, retransmission, and flow control.
Latency and packet loss directly impact effective throughput.

### UDP

UDP is lower overhead and no built-in retransmission.
Better for real-time traffic when timeliness matters more than perfect delivery.

### Command walkthrough

```bash
netstat -an
ss -lntup
tcpdump -nn
curl -v https://example.org
```

### Failure pattern

Ping success does not prove app success. App may fail due port policy, TLS, or server process state.

---

## Chapter 7: Core Services (DHCP, DNS, NAT, NTP, QoS)

### Dependency chain

Most user reports are service-chain issues, not pure routing failures.
Typical chain:

1. host gets IP config (DHCP)
1. host resolves name (DNS)
1. host reaches destination (routing/NAT/policy)
1. app session established

### Command walkthrough

```bash
show ip dhcp binding
show ip nat translations
show ip nat statistics
show ntp status
show policy-map interface
```

### Operational rule

If time is wrong, logs and certificates become untrustworthy. Always validate NTP early.

---

## Chapter 8: Wireless Networking

### RF realities

Wireless is shared half-duplex medium.
Higher client density with poor channel plan causes contention and low throughput even with strong signal.

### Design principles

- separate SSIDs by trust domain
- map SSIDs to correct VLANs
- tune channel and power, do not leave defaults blindly
- validate roaming behavior for voice clients

### Command walkthrough

```bash
show wlan summary
show ap summary
show client summary
show wireless stats
show radius statistics
```

---

## Chapter 9: Network Security and Hardening

### Security baseline

- least privilege policy
- AAA for admin control
- secure management plane (SSH, SNMPv3)
- logging and time sync
- L2 protections at access edge

### ACL design method

1. write required flows first
1. place explicit permits for required traffic
1. place explicit denies for sensitive zones
1. end with deny-any and log where appropriate
1. validate with test matrix

### Command walkthrough

```bash
show access-lists
show aaa sessions
show port-security interface
show ip dhcp snooping binding
show logging
```

---

## Chapter 10: Automation and Programmability

### Automation principles

- idempotent changes
- source-of-truth inventory
- pre-check and post-check gates
- rollback plan tested before production

### Simple workflow

1. backup current configs
1. render intended config from data model
1. dry-run diff
1. apply change to pilot subset
1. run validation checks

### Command walkthrough

```bash
python backup_configs.py
python validate_ntp.py
git status
git diff
```

---

## Chapter 11: Cloud Networking and SDN

### Cloud mapping

On-prem concepts map to cloud constructs:

- VLAN-like separation -> subnets
- ACL zones -> security groups and NACLs
- core routing -> transit constructs

### Common hybrid failure

Route to cloud exists from branch, but return path is blocked by route table or security rule mismatch.

### Validation checklist

- route table entries for both directions
- security policy for source and destination CIDR
- DNS resolution path
- MTU impact of overlays/tunnels

---

## Chapter 12: Observability and Troubleshooting

### Incident workflow

1. define impact and scope
1. collect evidence, do not guess
1. test one hypothesis at a time
1. apply smallest safe fix
1. verify restoration end-to-end
1. write RCA with preventive action

### Data sources you must correlate

- device logs
- interface counters
- flow records
- packet captures
- user impact timeline

---

## Chapter 13: WAN and VPN

### WAN decision tradeoffs

Compare options by:

- latency and jitter
- SLA and provider support
- cost per site
- failover behavior
- operational complexity

### VPN reality

Tunnel up only means control plane is up.
You still need selectors, routing, NAT exemption, and policy alignment for data to flow.

### Command walkthrough

```bash
show crypto isakmp sa
show crypto ipsec sa
show interface tunnel
show ip sla statistics
show track
```

---

## Chapter 14: Enterprise Design

### Good design goals

- bounded failure domains
- clear segmentation boundaries
- deterministic routing and summarization
- observable systems with measurable SLOs
- manageable operations by real teams

### Design review questions

- what fails if this link/device dies?
- can we roll back safely during change?
- can on-call engineer diagnose this at 2 AM?
- does policy intent match real traffic paths?

---

## Chapter 15: Career and Certification Readiness

### What gets people hired

- practical troubleshooting method
- clean documentation
- ability to explain tradeoffs
- repeatable lab portfolio with evidence

### Portfolio standard

Each project should include:

1. business objective
1. architecture and addressing plan
1. config snippets
1. verification evidence
1. incident or failure simulation
1. lessons learned and improvement plan

---

## Final Practical Assignment

Build an enterprise mini-network with:

- VLAN segmentation
- inter-VLAN routing
- OSPF between sites
- DHCP/DNS/NAT services
- ACL security policy
- monitoring evidence

Deliverables:

- topology diagram
- config files
- verification outputs
- one injected failure with RCA

If you can complete this end-to-end and explain each design choice, you are no longer a beginner.
