# Wireshark Lesson 08: Wireless: Association and Authentication Packets

## Scenario

Client sees SSID but cannot join.

## Useful Filters

- wlan.fc.type_subtype == 0x00
- eapol
- radius

## Packet Analysis Procedure

1. Capture probe, auth, and association frames.
1. Trace key exchange sequence.
1. Inspect EAP or RADIUS success/failure.
1. Identify first failed stage in join workflow.

## Interpretation Notes

- Association success does not guarantee auth success.
- 4-way key exchange failure often indicates key mismatch or loss.
- RADIUS reject indicates identity or policy issue.

## Verification Checklist

- Capture contains both failing and successful reference packets where possible.
- Root-cause statement cites exact packet evidence.
- After-fix capture demonstrates restored behavior.

## Reflection Exercise

1. Reproduce this scenario in your lab.
1. Capture before and after your fix.
1. Write a five-line root-cause summary from packet evidence.
