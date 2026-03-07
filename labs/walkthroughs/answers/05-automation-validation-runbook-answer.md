# Walkthrough 05 Solved: Automation Validation Runbook

## Expected End State

- Backup captured before change.
- Intended config rendered from inventory data.
- Pilot rollout succeeds with no regressions.
- Post-check validates policy and service health.

## Suggested Execution Sequence

```bash
python backup_configs.py
python render_configs.py --inventory inventory.yml
python validate_precheck.py
python apply_changes.py --limit pilot
python validate_postcheck.py
```

## Validation Evidence

- Before and after config diff.
- Service reachability tests unchanged or improved.
- Compliance script reports pass for required controls.

## Failure Injection and Recovery

1. Push intentionally incorrect interface description template.
2. Detect mismatch in post-check output.
3. Roll back to previous known good config.
4. Re-run post-check to confirm clean state.
