# Wireshark Lesson 07: Services: DHCP and DNS Transaction Tracing

## Scenario

Client gets IP but cannot open websites.

## Useful Filters

- bootp 

## Packet Analysis Procedure

1. 

## Interpretation Notes

-  dhcp
- dns
- udp.port == 53|Capture client lease process.
- Verify gateway and DNS options in DHCP ACK.
- Trace DNS query and response for target domain.
- Validate follow-up session attempt to resolved address.|Bad DNS option in DHCP causes broad app failures.
- NXDOMAIN differs from SERVFAIL and implies different root cause.
- Good DNS plus failed TCP points to policy or server issue.

## Verification Checklist

- Capture contains both failing and successful reference packets where possible.
- Root-cause statement cites exact packet evidence.
- After-fix capture demonstrates restored behavior.

## Reflection Exercise

1. Reproduce this scenario in your lab.
1. Capture before and after your fix.
1. Write a five-line root-cause summary from packet evidence.
