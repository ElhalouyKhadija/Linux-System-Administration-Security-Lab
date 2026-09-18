# Phase 6 — System Resources & Troubleshooting

This phase introduces essential commands for monitoring system resources and diagnosing common Linux performance issues.

## Disk Usage

Display filesystem disk-space usage in a human-readable format:

```bash
df -h
```

**What it shows:**

- Available and used disk space
- Usage percentage for each mounted filesystem
- Mount points and filesystem locations

## Memory and Swap Usage

View system memory and swap utilization in a human-readable format:

```bash
free -h
```

**What it shows:**

- Total, used, and available physical memory
- Cached and buffered memory
- Total and used swap space

## System Uptime and Load Average

Check how long the system has been running and review its current load average:

```bash
uptime
```

**What it shows:**

- Current system time
- System uptime
- Number of logged-in users
- Load averages for the last 1, 5, and 15 minutes

> **Tip:** Compare the load average with the number of available CPU cores to help identify potential system overload.