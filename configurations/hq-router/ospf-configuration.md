# HQ Router — OSPF Configuration Notes

## Role

HQ acts as the hub in a three-site single-area OSPF design.

## Key commands used

```text
ospf 1 router-id 1.1.1.1
 area 0.0.0.0
  network 192.168.0.0 0.0.0.255
  network 10.0.0.0 0.0.0.255
```

## Intent

- Advertise HQ LAN (`192.168.0.0/24`) into OSPF
- Advertise inter-site link (`10.0.0.0/24`) into OSPF
- Stable Router-ID via Loopback0 (`1.1.1.1`)

## Verification commands

```text
display ospf peer
display ospf peer brief
display ip routing-table
display ospf lsdb
ping 192.168.1.1
ping 192.168.2.1
```

## Expected neighbors

Adjacencies toward Branch 1 and Branch 2 once Layer-3 links and OSPF network statements match on both sides.
