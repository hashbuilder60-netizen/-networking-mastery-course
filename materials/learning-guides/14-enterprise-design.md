# Learning Guide: Module 14 - Enterprise Network Design

## Why This Module Matters

Design quality determines long-term reliability, security, and operational simplicity.

## Core Concepts

- Good design controls failure domains, scaling limits, and operational ownership boundaries.
- Redundancy should remove single points of failure without creating uncontrolled complexity.
- Addressing, summarization, and segmentation should align to org structure and risk model.
- Capacity planning requires utilization trends and growth assumptions, not guesses.
- Change control and tested rollback are design requirements, not process overhead.

## Worked Example

Worked Example: Two-core campus with distribution redundancy and summarized routes per building reduces outage blast radius during access-layer failures.

## Commands to Practice

- show standby brief
- show vrrp brief
- show ip route summary
- show vrf
- show spanning-tree root
- show platform capacity

## Step-by-Step Lab Drill

1. Create logical + physical design for 3-year growth.
1. Define segmentation by department/security zone.
1. Design FHRP and routing redundancy.
1. Write acceptance and rollback tests.
1. Present tradeoff decisions to stakeholders.

## Troubleshooting Scenario

**Scenario:** Symptom: Frequent outages during routine maintenance windows.

**Fix Workflow:**

1. Review dependency map and change sequencing.
1. Add staged deployment and canary checks.
1. Add automatic rollback trigger criteria.
1. Improve pre-change validation checklist.

## Knowledge Check

### Q1
Design for uptime starts with?
**Answer:** Failure-domain and dependency mapping.

### Q2
Risk of over-complex design?
**Answer:** Harder operations and slower recovery.

### Q3
Why summarization at boundaries?
**Answer:** Contain control-plane instability.

### Q4
What proves capacity readiness?
**Answer:** Trend data with headroom policy.

### Q5
Why architecture decision records?
**Answer:** Preserve rationale for future teams.

