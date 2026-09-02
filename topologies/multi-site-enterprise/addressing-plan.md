# Addressing Plan — Multi-Site Enterprise

## Summary table

| Site | Role | LAN subnet | LAN gateway | Inter-site / WAN | Router model |
|------|------|------------|-------------|------------------|--------------|
| HQ | Core | 192.168.0.0/24 | 192.168.0.1 | 10.0.0.0/24 | AR2220E |
| Branch 1 | Spoke | 192.168.1.0/24 | 192.168.1.1 | 10.0.1.0/24 | AR1220E |
| Branch 2 | Spoke | 192.168.2.0/24 | 192.168.2.1 | 10.0.2.0/24 | AR1220E |

## Interface sketch (logical)

### HQ — AR2220E

| Interface | IP | Mask | Purpose |
|-----------|-----|------|---------|
| GE0/0/0 | 192.168.0.1 | 24 | HQ LAN |
| GE0/0/1 | 10.0.0.1 | 24 | Link toward branches / core WAN segment |
| Loopback0 | 1.1.1.1 | 32 | Router-ID stability (optional) |

### Branch 1 — AR1220E

| Interface | IP | Mask | Purpose |
|-----------|-----|------|---------|
| GE0/0/0 | 192.168.1.1 | 24 | Branch 1 LAN |
| GE0/0/1 | 10.0.1.1 | 24 | Uplink toward HQ |
| Loopback0 | 1.1.1.2 | 32 | Router-ID (optional) |

### Branch 2 — AR1220E

| Interface | IP | Mask | Purpose |
|-----------|-----|------|---------|
| GE0/0/0 | 192.168.2.1 | 24 | Branch 2 LAN |
| GE0/0/1 | 10.0.2.1 | 24 | Uplink toward HQ |
| Loopback0 | 1.1.1.3 | 32 | Router-ID (optional) |

> **Note:** Exact interface names in eNSP may vary by device image. Match the IP plan; adjust interface IDs to your topology file.

## Host addressing (examples)

| Site | PC / server example | Gateway |
|------|---------------------|---------|
| HQ | 192.168.0.10 | 192.168.0.1 |
| Branch 1 | 192.168.1.10 | 192.168.1.1 |
| Branch 2 | 192.168.2.10 | 192.168.2.1 |

## Summarization target (future / optional)

Aggregate branch WAN blocks toward a summary such as `10.0.0.0/16` when multi-area or ABR labs are added.
