# Wireshark Lesson 13: WAN and VPN: IKE and IPSec Negotiation Analysis

## Scenario

Tunnel appears up but protected subnet fails.

## Useful Filters

- isakmp 

## Packet Analysis Procedure

1. 

## Interpretation Notes

-  ikev2
- esp
- udp.port == 500 || udp.port == 4500|Capture tunnel setup and data phase.
- Verify phase-1 and phase-2 proposal match.
- Inspect traffic selectors for protected prefixes.
- Confirm ESP data volume during business flow tests.|Successful IKE does not guarantee correct selectors.
- NAT-T changes packet form and MTU behavior.
- Selector mismatch yields idle tunnel with no useful traffic.

## Verification Checklist

- Capture contains both failing and successful reference packets where possible.
- Root-cause statement cites exact packet evidence.
- After-fix capture demonstrates restored behavior.

## Reflection Exercise

1. Reproduce this scenario in your lab.
1. Capture before and after your fix.
1. Write a five-line root-cause summary from packet evidence.
