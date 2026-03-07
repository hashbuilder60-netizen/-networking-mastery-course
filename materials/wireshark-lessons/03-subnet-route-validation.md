# Wireshark Lesson 03: Addressing: Subnet and Route Path Validation

## Scenario

Some hosts in same VLAN communicate, others fail.

## Useful Filters

- icmp
- arp
- ip.addr == 10.10.30.25

## Packet Analysis Procedure

1. Capture from healthy and failing host.
1. Ping local and remote destinations from both.
1. Check whether failing host ARPs gateway or remote host.
1. Compare route decision behavior from traces.

## Interpretation Notes

- Wrong mask can make remote destination look local.
- ARP for remote subnet target indicates subnetting mistake.
- Correct gateway ARP confirms proper host route logic.

## Verification Checklist

- Capture contains both failing and successful reference packets where possible.
- Root-cause statement cites exact packet evidence.
- After-fix capture demonstrates restored behavior.

## Reflection Exercise

1. Reproduce this scenario in your lab.
1. Capture before and after your fix.
1. Write a five-line root-cause summary from packet evidence.
