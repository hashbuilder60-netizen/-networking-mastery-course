# Answer Key: Module 12: Observability and Troubleshooting

## Expected Approach

1. Start with scope and baseline assumptions.
2. Validate physical and interface state.
3. Confirm control-plane health (adjacency, learning, route or service state).
4. Confirm data-plane behavior with targeted tests.
5. Restore service with minimal blast radius and re-validate end to end.

## Strong Submission Characteristics

- Uses evidence, not guesswork.
- Distinguishes symptoms from root cause.
- Includes rollback-safe change logic.
- Documents why the fix worked.

## Scoring Rubric (100)

- Build correctness: 30
- Verification quality: 20
- Troubleshooting method: 30
- RCA clarity: 10
- Preventive recommendation: 10

## Common Deductions

- Missing return-path validation.
- No proof of restoration after fix.
- Root cause stated without evidence.
- No preventive action.
