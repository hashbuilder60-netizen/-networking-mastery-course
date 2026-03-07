# Wireshark Lesson 01: Foundations: ARP and ICMP Path Discovery

## Scenario

Host cannot reach default gateway.

## Useful Filters

- arp
- icmp
- eth.addr == aa:bb:cc:dd:ee:ff

## Packet Analysis Procedure

1. Start capture on user VLAN span port.
1. Generate ping from client to gateway.
1. Locate ARP request and ARP reply.
1. Validate ICMP echo request and reply timing.

## Interpretation Notes

- ARP must resolve next-hop MAC before ICMP leaves host.
- Missing ARP reply indicates L2 path or VLAN issue.
- Stable ICMP RTT indicates healthy local forwarding.

## Verification Checklist

- Capture contains both failing and successful reference packets where possible.
- Root-cause statement cites exact packet evidence.
- After-fix capture demonstrates restored behavior.

## Reflection Exercise

1. Reproduce this scenario in your lab.
1. Capture before and after your fix.
1. Write a five-line root-cause summary from packet evidence.
