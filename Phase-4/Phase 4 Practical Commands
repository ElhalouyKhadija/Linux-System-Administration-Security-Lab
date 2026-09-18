# Phase 4 — Firewall & Security Rules

## Overview

This phase documents the inspection of the host firewall using `iptables`. The goal is to review the active chains, default policies, configured rules, and packet counters.

## Firewall Inspection

Run the following command with administrative privileges:

```bash
sudo iptables -L -n -v
```

### Option Reference

| Option | Purpose |
|---|---|
| `-L` | Lists the firewall rules |
| `-n` | Displays addresses and ports numerically |
| `-v` | Shows verbose details and packet/byte counters |

## Main Firewall Chains

| Chain | Traffic handled |
|---|---|
| `INPUT` | Traffic entering the system |
| `FORWARD` | Traffic passing through the system |
| `OUTPUT` | Traffic leaving the system |

## Practical Result

The inspection showed the following baseline configuration:

```text
INPUT policy: ACCEPT
FORWARD policy: ACCEPT
OUTPUT policy: ACCEPT
Visible filtering rules: None
Packet counters: 0
Byte counters: 0
```

> **Assessment:** No visible filtering rules were configured at the time of inspection. All three default policies were set to `ACCEPT`.

## Key Takeaways

- Reviewed the active `iptables` configuration.
- Identified the purpose of the `INPUT`, `FORWARD`, and `OUTPUT` chains.
- Checked default chain policies and traffic counters.
- Recorded the host's baseline firewall state for future hardening.
