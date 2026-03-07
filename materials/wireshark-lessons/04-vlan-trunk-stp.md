# Wireshark Lesson 04: Switching: VLAN Tag and STP Event Inspection

## Scenario

Intermittent loss after switching change.

## Useful Filters

- stp
- vlan
- eth.type == 0x8100

## Packet Analysis Procedure

1. Capture trunk traffic during issue.
1. Inspect VLAN tag IDs on impacted flow.
1. Check BPDU and topology change events.
1. Correlate packet loss with topology events.

## Interpretation Notes

- Unexpected VLAN IDs indicate trunk allow-list error.
- Frequent topology changes cause short traffic interruption.
- BPDU pattern confirms root stability or instability.

## Verification Checklist

- Capture contains both failing and successful reference packets where possible.
- Root-cause statement cites exact packet evidence.
- After-fix capture demonstrates restored behavior.

## Reflection Exercise

1. Reproduce this scenario in your lab.
1. Capture before and after your fix.
1. Write a five-line root-cause summary from packet evidence.
