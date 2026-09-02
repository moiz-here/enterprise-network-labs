# Verification — OSPF Neighbor Status

## Commands

```text
display ospf peer
display ospf peer brief
```

## Expected result (lab)

| Local device | Neighbor Router-ID | State | Interface |
|--------------|--------------------|-------|-----------|
| HQ | 1.1.1.2 | Full | GE toward Branch 1 |
| HQ | 1.1.1.3 | Full | GE toward Branch 2 |
| Branch 1 | 1.1.1.1 | Full | Uplink to HQ |
| Branch 2 | 1.1.1.1 | Full | Uplink to HQ |

## How to capture for GitHub

1. Run `display ospf peer` on HQ
2. Screenshot terminal window in eNSP
3. Save as `assets/screenshots/ospf-neighbor-status.png`

## If neighbors stuck in Init / 2-Way

See [`troubleshooting-notes.md`](troubleshooting-notes.md).
