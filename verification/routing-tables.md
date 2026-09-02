# Verification — Routing Tables

## Commands

```text
display ip routing-table
display ip routing-table protocol ospf
```

## Expected OSPF-learned prefixes (examples)

On **HQ**, expect routes to:

- `192.168.1.0/24` via Branch 1 uplink
- `192.168.2.0/24` via Branch 2 uplink

On **Branch 1**, expect:

- `192.168.0.0/24` (HQ LAN)
- `192.168.2.0/24` (Branch 2 LAN)
- HQ WAN / transit prefixes as designed

## Capture

Save HQ routing table screenshot as:

`assets/screenshots/ospf-routing-table.png` or `routing-table-hq.png`
