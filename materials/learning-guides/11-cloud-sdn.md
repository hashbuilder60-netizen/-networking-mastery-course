# Learning Guide: Module 11 - Cloud Networking and SDN

## Why This Module Matters

Enterprise networks increasingly span on-prem and cloud; engineers must design both coherently.

## Core Concepts

- Cloud VPC/VNet design uses subnets, route tables, and security controls instead of physical VLAN boundaries.
- Security groups (stateful) and NACLs (stateless, subnet level) require coordinated policy planning.
- Transit architectures centralize multi-network connectivity and route control.
- Overlay networks provide tenant segmentation over shared underlay transport.
- Hybrid routing fails quickly when CIDR overlap and route propagation are not planned.

## Worked Example

Worked Example: App subnet can reach DB only on 5432/TCP by route + security group permit; NACL denies all other inbound for strict data tier isolation.

## Commands to Practice

- show vxlan
- show nve peers
- show ip route vrf <name>
- traceroute <cloud-endpoint>
- cloud route-table describe
- cloud security-group list

## Step-by-Step Lab Drill

1. Design 3-tier cloud subnet model.
1. Apply route table per tier intent.
1. Apply SG/NACL policy matrix.
1. Connect simulated branch to cloud transit.
1. Validate allowed and denied flows.

## Troubleshooting Scenario

**Scenario:** Symptom: On-prem branch reaches cloud gateway but not app subnet.

**Fix Workflow:**

1. Check route propagation into transit and spoke tables.
1. Check SG/NACL for source CIDR permits.
1. Check return route from app subnet.
1. Retest with targeted port probes.

## Knowledge Check

### Q1
SG vs NACL difference?
**Answer:** SG stateful instance-level, NACL stateless subnet-level.

### Q2
Why avoid CIDR overlap?
**Answer:** Breaks deterministic routing.

### Q3
Overlay purpose?
**Answer:** Logical segmentation over shared transport.

### Q4
Transit hub benefit?
**Answer:** Central policy and scalable connectivity.

### Q5
Hybrid outage common cause?
**Answer:** Missing return path or blocked security rule.

