# Network Design Review Checklist

## Architecture

- Are segmentation boundaries explicit and documented?
- Are failure domains bounded?
- Is there a clear capacity growth plan?

## Routing and Addressing

- Is summarization used where appropriate?
- Are overlapping subnets eliminated?
- Is IPv6 strategy documented?

## Security

- Is least privilege enforced by policy?
- Are management interfaces isolated and protected?
- Are logging and time synchronization standardized?

## Operations

- Are monitoring and alert thresholds defined?
- Is change rollback tested?
- Is ownership clear for every critical component?
