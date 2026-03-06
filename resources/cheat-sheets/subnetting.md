# Subnetting Cheat Sheet

## CIDR to Mask
- /24 = 255.255.255.0
- /25 = 255.255.255.128
- /26 = 255.255.255.192
- /27 = 255.255.255.224
- /28 = 255.255.255.240
- /29 = 255.255.255.248
- /30 = 255.255.255.252

## Host Capacity Formula
- Hosts per subnet: `2^(32-prefix) - 2` (IPv4 typical host subnet)

## Subnetting Workflow
1. Determine required hosts and subnets.
2. Select smallest prefix that meets host count.
3. Allocate largest networks first (VLSM).
4. Reserve room for growth and summarization.
5. Document gateway, usable range, and broadcast.
