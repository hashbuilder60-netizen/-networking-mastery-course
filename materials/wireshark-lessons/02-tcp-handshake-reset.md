# Wireshark Lesson 02: Models: TCP Handshake and Reset Analysis

## Scenario

Application times out while ping succeeds.

## Useful Filters

- tcp.flags.syn == 1
- tcp.flags.reset == 1
- tcp.port == 443

## Packet Analysis Procedure

1. Capture client to server session attempt.
1. Find SYN, SYN-ACK, ACK sequence.
1. If failure, identify packet with RST.
1. Map RST source to server or policy device.

## Interpretation Notes

- Handshake success confirms transport path for that port.
- Server RST usually means closed service or app refusal.
- Middlebox RST indicates policy decision.

## Verification Checklist

- Capture contains both failing and successful reference packets where possible.
- Root-cause statement cites exact packet evidence.
- After-fix capture demonstrates restored behavior.

## Reflection Exercise

1. Reproduce this scenario in your lab.
1. Capture before and after your fix.
1. Write a five-line root-cause summary from packet evidence.
