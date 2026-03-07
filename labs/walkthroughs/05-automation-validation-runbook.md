# Walkthrough 05: Automation Validation Runbook

## Goal

Run a safe network change with pre-check, change, and post-check evidence.

## Runbook

1. Backup current configs.
1. Render intended config from inventory data.
1. Dry-run diff and peer review.
1. Apply to pilot subset.
1. Validate service and policy outcomes.
1. Roll forward or rollback based on evidence.

## Command Skeleton

```bash
python backup_configs.py
python render_configs.py --inventory inventory.yml
python validate_precheck.py
python apply_changes.py --limit pilot
python validate_postcheck.py
```

## Success Criteria

- No critical service regression.
- All compliance checks pass.
- Change log includes before/after evidence.
