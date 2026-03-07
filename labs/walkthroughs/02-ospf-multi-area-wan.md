# Walkthrough 02: OSPF Multi-Area WAN

## Goal

Deploy OSPF for HQ and branch with area design and route summarization.

## Routing Plan

- Area 0 backbone between core routers
- Area 10 at branch
- ABR summarizes branch routes toward backbone

## Core OSPF Config Example

```bash
router ospf 10
 router-id 1.1.1.1
 network 10.0.0.0 0.0.0.255 area 0
 network 10.10.0.0 0.0.255.255 area 10
 area 10 range 10.10.0.0 255.255.0.0
```

## Verification

```bash
show ip ospf neighbor
show ip ospf database
show ip route ospf
```

## Failure Drill

Set OSPF hello/dead timers differently on one side and fix adjacency.
