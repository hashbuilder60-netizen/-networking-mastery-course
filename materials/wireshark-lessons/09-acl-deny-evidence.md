# Wireshark Lesson 09: Security: ACL Deny and Permit Evidence

## Scenario

Business app blocked after policy update.

## Useful Filters

- ip.addr == 10.10.20.15 && tcp.port == 443
- icmp.type == 3
- tcp.flags.reset == 1

## Packet Analysis Procedure

1. Capture near policy enforcement device.
1. Test allowed and denied source profiles.
1. Inspect deny behavior type (silent drop or active reject).
1. Compare results against policy matrix.

## Interpretation Notes

- Silent drop appears as client retransmission timeout.
- Active deny appears as unreachable or reset.
- Comparative captures validate least-privilege intent.

## Verification Checklist

- Capture contains both failing and successful reference packets where possible.
- Root-cause statement cites exact packet evidence.
- After-fix capture demonstrates restored behavior.

## Reflection Exercise

1. Reproduce this scenario in your lab.
1. Capture before and after your fix.
1. Write a five-line root-cause summary from packet evidence.
