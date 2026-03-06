# Learning Guide: Module 10 - Network Automation and Programmability

## Why This Module Matters

Modern teams scale through automation, validation, and repeatable change workflows.

## Core Concepts

- Automation should be idempotent: running same playbook twice should converge to same state.
- Source-of-truth inventories reduce drift and human inconsistency.
- Templates separate data from device syntax, improving reuse across environments.
- Pre-check and post-check validation gates reduce outage risk.
- APIs and model-driven interfaces provide structured state vs fragile CLI parsing.

## Worked Example

Worked Example: Generate interface configs from YAML inventory, push only changed interfaces, then run post-checks for admin/oper state and description compliance.

## Commands to Practice

- python backup_configs.py
- python validate_ntp.py
- python generate_interfaces.py
- git status
- git diff
- curl -k <api-endpoint>

## Step-by-Step Lab Drill

1. Create inventory YAML for lab devices.
1. Render configs via template engine.
1. Run backup before push.
1. Apply changes to subset first.
1. Run compliance report and rollback test.

## Troubleshooting Scenario

**Scenario:** Symptom: Script finished with success message but network behavior unchanged.

**Fix Workflow:**

1. Verify target device list selection.
1. Check API response body, not status code only.
1. Validate candidate/commit model if used.
1. Add explicit post-change assertions.

## Knowledge Check

### Q1
Define idempotent workflow.
**Answer:** Repeated runs produce intended state without extra drift.

### Q2
Why use Git for network changes?
**Answer:** Traceability and peer review.

### Q3
What is pre-check purpose?
**Answer:** Ensure safe starting conditions.

### Q4
Why can HTTP 200 still fail intent?
**Answer:** Operation may be accepted but not applied.

### Q5
Best rollback strategy?
**Answer:** Tested, versioned prior state restoration.

