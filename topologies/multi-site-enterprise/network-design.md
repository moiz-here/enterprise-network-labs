# Multi-Site Enterprise — Network Design

## Goals

- Three sites: HQ (core), Branch 1, Branch 2
- Single OSPF Area 0 for simplicity and clear learning of adjacency + LSDB
- Hierarchical IPv4 addressing for easy summarization later
- End-to-end IP reachability between all LAN segments

## Design decisions

| Decision | Choice | Rationale |
|----------|--------|-----------|
| IGP | OSPF process 1, Area 0 | Industry-standard, HCIA-relevant |
| Sites | 3 | Enough to show multi-site without excessive complexity |
| Router roles | HQ = hub; branches = spokes | Matches typical enterprise campus / branch model |
| Switching | S3700 per site | Access-layer practice; L2 within site |

## Logical layout

```
HQ LAN 192.168.0.0/24 ── AR2220E ── WAN links ── Branch routers ── Branch LANs
```

Inter-site links use `10.0.x.0/24` blocks. Site LANs use `192.168.x.0/24`.

## OSPF parameters (lab defaults)

- Process ID: `1`
- Area: `0.0.0.0`
- Router-IDs: aligned with loopback or highest LAN IP (documented per device config)
- Hello/Dead: platform defaults unless noted in troubleshooting

## Out of scope (v1)

- Multi-area OSPF
- Redistribution
- NAT / firewall
- QoS

These are listed under Future Work in the main README.
