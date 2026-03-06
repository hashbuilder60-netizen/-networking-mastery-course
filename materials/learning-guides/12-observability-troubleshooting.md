# Learning Guide: Module 12 - Observability and Advanced Troubleshooting

## Why This Module Matters

Reliable operations require evidence-driven diagnosis, not command memorization alone.

## Core Concepts

- Use a structured method: scope, isolate, validate hypothesis, implement fix, verify restoration.
- Correlate metrics, logs, flows, and packet captures for complete incident context.
- Baseline normal behavior is needed before anomalies can be trusted.
- RCA should identify trigger, contributing factors, and missing controls.
- Post-incident actions must be assigned, tracked, and verified closed.

## Worked Example

Worked Example: Packet loss appears random but aligns with interface CRC spikes every time backup circuit is active, identifying physical carrier issue not app bug.

## Commands to Practice

- show logging
- show interfaces counters errors
- show processes cpu
- show platform health
- tcpdump -nn -i <if>
- flow-export query

## Step-by-Step Lab Drill

1. Run staged outage scenario with mixed symptoms.
1. Collect evidence from all layers.
1. Restore services in lowest-risk order.
1. Write timeline and blast-radius report.
1. Present RCA with preventive actions.

## Troubleshooting Scenario

**Scenario:** Symptom: Intermittent branch call quality degradation.

**Fix Workflow:**

1. Check jitter/loss metrics during busy hours.
1. Check queue drops and QoS counters.
1. Check WAN provider path changes.
1. Adjust QoS and validate MOS improvement.

## Knowledge Check

### Q1
First troubleshooting step?
**Answer:** Define scope and impact.

### Q2
Why combine logs and packets?
**Answer:** Each data source covers different visibility.

### Q3
What is good RCA output?
**Answer:** Cause + controls + action owners.

### Q4
Why baseline before change?
**Answer:** Detect regressions reliably.

### Q5
What closes an incident truly?
**Answer:** Validated restoration and prevention tasks.

