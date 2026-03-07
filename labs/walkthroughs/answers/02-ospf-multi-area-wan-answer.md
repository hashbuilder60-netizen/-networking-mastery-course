# Walkthrough 02 Solved: OSPF Multi-Area WAN

## Expected End State

- Backbone links in area 0 are stable.
- Branch prefixes in area 10 are advertised and summarized.
- Failover path restores reachability within acceptable convergence time.

## Reference OSPF Configuration

```bash
router ospf 10
 router-id 1.1.1.1
 network 10.0.0.0 0.0.0.255 area 0
 network 10.10.0.0 0.0.255.255 area 10
 area 10 range 10.10.0.0 255.255.0.0
```

## Verification

```bash
show ip ospf neighbor
show ip ospf database
show ip route ospf
show ip protocols
```

- Neighbors reach `FULL` state.
- OSPF routes populate expected prefixes.
- Summarized route visible on ABR-facing routers.

## Failure Injection and Recovery

1. Set mismatched hello/dead timers on one peer.
2. Confirm adjacency loss and route withdrawal.
3. Correct timer mismatch.
4. Confirm adjacency and route recovery.
