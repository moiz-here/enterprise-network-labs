# Branch 1 Router — OSPF Configuration Notes

## Role

Spoke site. Must form OSPF adjacency with HQ and learn remote LANs (`192.168.0.0/24`, `192.168.2.0/24`).

## Key commands

```text
ospf 1 router-id 1.1.1.2
 area 0.0.0.0
  network 192.168.1.0 0.0.0.255
  network 10.0.1.0 0.0.0.255
```

## Checks

```text
display ospf peer
display ip routing-table
ping 192.168.0.1
ping 192.168.2.10
```
