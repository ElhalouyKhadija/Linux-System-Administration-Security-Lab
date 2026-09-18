# Phase 6 — System Resources & Troubleshooting

> **Status:** ✅ Applied and completed  
> **Environment:** Kali Linux

## Overview

This phase focused on inspecting system resources and performing basic troubleshooting checks on a Kali Linux system. The assessment covered disk capacity, memory and swap utilization, system uptime, and processor load averages.

## Objectives

- Review available disk space and filesystem utilization.
- Inspect physical memory and swap usage.
- Check system uptime.
- Interpret the system load averages.
- Practice essential Linux resource-monitoring commands.

## 1. Disk Space Analysis

Disk usage was checked with the following command:

```bash
df -h
```

### Main System Partition

| Metric | Value |
|---|---:|
| Device | `/dev/sda1` |
| Total capacity | 79G |
| Used space | 16G |
| Available space | 59G |
| Utilization | 22% |

The system partition had **59G of available space** and was using **22%** of its total capacity, indicating a healthy amount of remaining storage.

## 2. Memory and Swap Usage

Memory usage was checked with:

```bash
free -h
```

### Resource Summary

| Resource | Value |
|---|---:|
| Total RAM | 1.9Gi |
| Used RAM | 857Mi |
| Free RAM | 254Mi |
| Available RAM | 1.1Gi |
| Swap | 953Mi |

The system had approximately **1.1Gi of available memory**, providing sufficient capacity for the observed workload.

## 3. System Uptime and Load

System uptime and load averages were checked using:

```bash
uptime
```

### Results

- **Uptime:** Approximately 2 hours and 35 minutes
- **Load averages:** `0.36 0.30 0.30`

The three load-average values represent the system load over the previous **1, 5, and 15 minutes**, respectively. The relatively low values indicate that the system was operating under a light workload during the assessment.

## Key Learnings

- How to check available disk space with `df -h`.
- How to inspect RAM and swap usage with `free -h`.
- How to verify system uptime with `uptime`.
- How to interpret one-, five-, and fifteen-minute load averages.
- How to perform basic Linux system resource and health checks.

## Evidence and Verification

The practical work was performed on **Kali Linux** and verified using terminal commands and screenshots. The recorded results document the system's disk capacity, memory state, swap allocation, uptime, and load averages at the time of testing.

## Practical Status

**Applied / Completed** ✅

This phase was practically performed and verified on Kali Linux.
