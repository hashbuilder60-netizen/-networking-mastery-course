# Learning Guide: Module 05 - Routing, OSPF, and BGP Introduction

## Why This Module Matters

Routing is the backbone of multi-network communication and fault isolation.

## Core Concepts

- Routers select paths with longest-prefix match, then administrative distance, then protocol metric.
- Static routes provide deterministic control and are useful for stubs and default paths.
- OSPF builds adjacency, floods LSAs, and runs SPF to create loop-free shortest paths.
- Area design and summarization improve scale and reduce topology churn.
- BGP is policy-driven inter-domain routing used at internet and multi-provider edges.

## Worked Example

Worked Example: Floating static default route with higher distance remains backup until primary OSPF route disappears, then traffic fails over automatically.

## Commands to Practice

- show ip route
- show ip ospf neighbor
- show ip ospf database
- show ip protocols
- show ip route ospf
- show ip bgp summary

## Step-by-Step Lab Drill

1. Configure OSPF neighbors in area 0.
1. Add area boundary and ABR summarization.
1. Inject default route from edge.
1. Add floating static backup path.
1. Simulate link failure and verify failover.

## Troubleshooting Scenario

**Scenario:** Symptom: Route exists in table but app still fails.

**Fix Workflow:**

1. Check return path symmetry.
1. Check ACL/NAT/policy along path.
1. Validate next-hop recursive reachability.
1. Use traceroute from both directions.

## Knowledge Check

### Q1
What does OSPF adjacency require first?
**Answer:** Matching timers/network/auth parameters.

### Q2
Why use area 0?
**Answer:** Backbone inter-area transit.

### Q3
When use floating static?
**Answer:** Backup route preference.

### Q4
What is AD used for?
**Answer:** Choosing between routing sources.

### Q5
Why choose BGP at edge?
**Answer:** Granular policy control and internet pathing.

