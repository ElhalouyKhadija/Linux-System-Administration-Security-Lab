# Phase 4 — Firewall and Security Rules

## Overview

This phase focused on inspecting the firewall configuration of a Kali Linux system and reviewing its current network-filtering policies. The inspection was performed with **iptables** and did not modify the existing firewall configuration.

## Objectives

- Inspect the active iptables configuration.
- Understand the purpose of the primary firewall chains.
- Identify the default policies applied to inbound, forwarded, and outbound traffic.
- Review packet and byte counters.
- Document the system's firewall posture without changing any rules.

## 1. Firewall Inspection

The active firewall rules were inspected with the following command:

```bash
sudo iptables -L -n -v
```

### Command Options

| Option | Description |
|:------:|-------------|
| `-L` | Lists the rules in each firewall chain. |
| `-n` | Displays IP addresses and port numbers in numeric format. |
| `-v` | Shows verbose information, including packet and byte counters. |

## 2. Primary Firewall Chains

The command displays three standard iptables chains:

| Chain | Purpose |
|-------|---------|
| `INPUT` | Controls traffic entering the Kali Linux system. |
| `FORWARD` | Controls packets routed through the system. |
| `OUTPUT` | Controls traffic leaving the system. |

## 3. Observed Configuration

The inspection showed the following default policies:

| Chain | Default Policy |
|-------|----------------|
| `INPUT` | `ACCEPT` |
| `FORWARD` | `ACCEPT` |
| `OUTPUT` | `ACCEPT` |

At the time of testing:

- No visible filtering rules were configured.
- The default policy for all three primary chains was `ACCEPT`.
- Packet and byte counters were `0`.

> **Note:** This observation reflects the firewall state at the time of inspection. Firewall rules and counters may change as the system configuration or network activity changes.

## 4. Security Assessment

The system was operating with an unrestricted default policy for incoming, forwarded, and outgoing traffic. Because no visible iptables filtering rules were present, the inspection did not identify an active rule set restricting network traffic.

No firewall rules were added, removed, or modified during this phase. The work was limited to inspection and documentation.

## 5. Key Takeaways

This phase demonstrated how to:

- Inspect a Linux firewall configuration with iptables.
- Distinguish between the `INPUT`, `FORWARD`, and `OUTPUT` chains.
- Interpret default firewall policies.
- Read packet and byte counters.
- Perform a basic firewall security assessment.

## Evidence

The practical work was performed on Kali Linux and verified using the terminal command shown above and a supporting screenshot.

## Practical Status

**Applied — Inspection and Documentation Completed**

The firewall configuration was successfully inspected and documented. No configuration changes were performed during this phase.
