# Learning Guide: Module 09 - Network Security, ACLs, and Hardening

## Why This Module Matters

Security must be engineered into normal operations, not added as an afterthought.

## Core Concepts

- Least privilege means only required flows are allowed; all else should be denied intentionally.
- ACLs are processed top-down, first match wins; ordering errors create major outages.
- AAA centralizes admin access and provides auditability for configuration changes.
- Layer 2 defenses (DHCP snooping, DAI, port security) block common spoofing attacks.
- Management plane hardening requires SSH, SNMPv3, secure logging, and role separation.

## Worked Example

Worked Example: An ACL permit for app subnet placed after broad deny causes outage. Reordering rule resolves outage without widening exposure.

## Commands to Practice

- show access-lists
- show ip interface
- show aaa sessions
- show port-security interface
- show ip dhcp snooping binding
- show logging

## Step-by-Step Lab Drill

1. Create user/server/guest ACL matrix.
1. Implement and verify allow/deny outcomes.
1. Enable DHCP snooping and DAI.
1. Harden management to SSH + AAA.
1. Test break-glass local admin fallback.

## Troubleshooting Scenario

**Scenario:** Symptom: Security policy change broke payroll app.

**Fix Workflow:**

1. Trace exact source/destination/port flow.
1. Check ACL hit counters and order.
1. Insert explicit permit before deny.
1. Validate and document final rule intent.

## Knowledge Check

### Q1
ACL processing order?
**Answer:** Top-down, first match.

### Q2
Why keep local admin fallback?
**Answer:** Recovery if AAA unreachable.

### Q3
DAI depends on what data?
**Answer:** DHCP snooping bindings.

### Q4
Why segment guests from servers?
**Answer:** Containment and risk reduction.

### Q5
What proves ACL fix worked?
**Answer:** Traffic tests + counter increments.

