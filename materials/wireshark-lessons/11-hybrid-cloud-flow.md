# Wireshark Lesson 11: Cloud and SDN: Hybrid Flow and Security Proof

## Scenario

On-prem reaches cloud edge but app subnet unreachable.

## Useful Filters

- icmp 

## Packet Analysis Procedure

1. 

## Interpretation Notes

-  tcp.port == 443
- ip.addr == 172.16.10.20
- vxlan|Capture on on-prem edge and cloud ingress points.
- Verify encapsulated flow and decapsulated endpoint flow.
- Validate security policy decision on destination side.
- Confirm return-path packets exist.|Forward success without return path causes timeout.
- Overlay headers can hide tenant traffic at wrong capture point.
- Security rule mismatch appears as one-way flow.

## Verification Checklist

- Capture contains both failing and successful reference packets where possible.
- Root-cause statement cites exact packet evidence.
- After-fix capture demonstrates restored behavior.

## Reflection Exercise

1. Reproduce this scenario in your lab.
1. Capture before and after your fix.
1. Write a five-line root-cause summary from packet evidence.
