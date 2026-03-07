# Wireshark Lesson 05: Routing: OSPF Control Plane Packet Flow

## Scenario

OSPF neighbor never reaches FULL.

## Useful Filters

- ospf
- ip.proto == 89

## Packet Analysis Procedure

1. Capture adjacency formation between peers.
1. Inspect Hello area, timers, and auth fields.
1. Inspect DD exchange and sequence progression.
1. Identify exact state transition where failure occurs.

## Interpretation Notes

- Hello mismatch blocks adjacency start.
- MTU mismatch often stalls in EXSTART or EXCHANGE.
- Auth mismatch causes dropped control packets.

## Verification Checklist

- Capture contains both failing and successful reference packets where possible.
- Root-cause statement cites exact packet evidence.
- After-fix capture demonstrates restored behavior.

## Reflection Exercise

1. Reproduce this scenario in your lab.
1. Capture before and after your fix.
1. Write a five-line root-cause summary from packet evidence.
