# Verification — Connectivity Tests

## Ping matrix (success expected)

| From | To | Target IP | Result |
|------|-----|-----------|--------|
| HQ PC | Branch 1 gateway | 192.168.1.1 | Success |
| HQ PC | Branch 2 gateway | 192.168.2.1 | Success |
| Branch 1 PC | HQ gateway | 192.168.0.1 | Success |
| Branch 1 PC | Branch 2 PC | 192.168.2.10 | Success |
| Branch 2 PC | HQ LAN host | 192.168.0.10 | Success |

## Commands

```text
ping 192.168.1.1
ping 192.168.2.1
tracert 192.168.2.10
```

## Captures for README

- `assets/screenshots/ping-test.png`
- `assets/screenshots/traceroute-test.png`

## Pass criteria (lab)

- All inter-site pings succeed with low loss
- Traceroute shows path via expected next-hops (HQ as hub)
