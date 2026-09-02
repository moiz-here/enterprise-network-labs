# Troubleshooting Notes

## Neighbor not forming

| Symptom | Likely cause | Check |
|---------|--------------|-------|
| No neighbor entry | Link down / wrong cable in eNSP | Physical topology, `display interface brief` |
| Stuck in Init | Multicast blocked / OSPF not enabled on interface | `network` statements, interface IP in correct subnet |
| Stuck in 2-Way (unexpected) | DR/BDR on point-to-point style link | Network type; for P2P links set `ospf network-type p2p` if needed |
| Different masks | Subnet mismatch on link | Addressing plan vs actual `ip address` |

## Routes missing

1. Confirm `display ospf lsdb` shows remote networks
2. Confirm `network` statements include LAN and link subnets
3. Check passive-interface mistakes (none in base lab)
4. Verify no ACL filtering OSPF (not used in v1 lab)

## Ping fails but OSPF Full

- Host default gateway wrong
- Switch port down / wrong VLAN
- ICMP blocked (not configured in base lab)

## Lab tip

Change one variable at a time. After each fix, re-check:

```text
display ospf peer brief
display ip routing-table protocol ospf
ping <remote>
```
