# Material Pack: Module 10: Network Automation and Programmability

## Objectives (Expanded)

- Automate repetitive configuration and validation tasks.
- Use APIs/NETCONF/RESTCONF for network operations.
- Build idempotent workflows with source control.

## Lesson Breakdown with Teaching Notes

1. Automation mindset and infrastructure as code basics
2. Python essentials for networking
3. Structured data: JSON, YAML, Jinja2 templating
4. APIs, auth tokens, and model-driven interfaces
5. Version control workflows for network teams

### What To Emphasize

- Tie every concept to packet flow and business impact.
- Validate every configuration with at least two independent checks.
- Distinguish control-plane problems from data-plane problems.
- Document baseline behavior before introducing changes.

### Common Misunderstandings

- Confusing reachability with service availability.
- Assuming protocol adjacency equals healthy application flow.
- Skipping rollback planning before change implementation.
- Relying on one command output instead of triangulating evidence.

## Lab Execution Pack

- Lab 1: Automated config backup script
- Lab 2: Generate interface configs from YAML inventory
- Stretch Lab: Post-change validation script

### Lab Evidence Checklist

- Topology screenshot or diagram.
- Addressing and interface mapping.
- Config snippets per device.
- Verification command output.
- One injected failure and recovery notes.

## Troubleshooting Patterns

- Drill A: Script pushes inconsistent configs
- Drill B: API request succeeds but state is unchanged

### Fast Isolation Workflow

1. Confirm scope: single host, VLAN, site, or global.
2. Validate Layer 1/2 state before deep protocol analysis.
3. Confirm routing and return path symmetry.
4. Validate service dependencies (DNS, DHCP, auth, time).
5. Capture evidence and document root cause.

## Command and Tool Kit

- `python backup_configs.py`
- `python validate_ntp.py`
- `git status`
- `git diff`
- `curl -k <api-endpoint>`

## Review Questions

- Which concept in this module has the highest operational risk if misconfigured?
- What would fail first if one key dependency broke?
- Which verification command gives you the fastest confidence signal?
- How would you explain this module to a junior engineer in 3 minutes?
- Which logs or counters would you collect during an outage?
- What preventive control would reduce repeat incidents?

## Performance Standard

- Rebuild the lab from memory in under 45 minutes.
- Diagnose one injected fault in under 20 minutes.
- Explain root cause and fix path in clear operational language.
