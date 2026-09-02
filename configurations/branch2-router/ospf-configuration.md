# Branch 2 Router — OSPF Configuration Notes

## Role

Spoke site. Symmetric to Branch 1 with its own LAN and uplink prefixes.

## Key commands

```text
ospf 1 router-id 1.1.1.3
 area 0.0.0.0
  network 192.168.2.0 0.0.0.255
  network 10.0.2.0 0.0.0.255
```

## Checks

```text
display ospf peer
display ip routing-table
ping 192.168.0.1
ping 192.168.1.10
```
