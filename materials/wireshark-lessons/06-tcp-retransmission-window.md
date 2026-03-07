# Wireshark Lesson 06: Transport: Retransmission and Window Behavior

## Scenario

Users report slowness at peak hours.

## Useful Filters

- tcp.analysis.retransmission
- tcp.analysis.duplicate_ack
- tcp.window_size

## Packet Analysis Procedure

1. Capture long transfer during peak.
1. Mark retransmission bursts in timeline.
1. Inspect duplicate ACK clusters.
1. Inspect receive window changes over time.

## Interpretation Notes

- Retransmissions indicate loss or reordering.
- Duplicate ACK bursts often trigger fast retransmit.
- Small receive window throttles throughput.

## Verification Checklist

- Capture contains both failing and successful reference packets where possible.
- Root-cause statement cites exact packet evidence.
- After-fix capture demonstrates restored behavior.

## Reflection Exercise

1. Reproduce this scenario in your lab.
1. Capture before and after your fix.
1. Write a five-line root-cause summary from packet evidence.
