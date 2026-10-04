# Practical Network Administration Commands

This reference documents the commands used during the practical Linux system administration and security lab for inspecting network configuration and verifying connectivity.

> **Note:** Run these commands in a Linux terminal. Some commands may require administrator privileges depending on your system configuration.

## 1. Check Network Interfaces

Display all network interfaces and their assigned IP addresses.

```bash
ip addr
```

## 2. Check the Routing Table

View the system's current routing table.

```bash
ip route
```

## 3. Check the Default Gateway

Display the configured default gateway.

```bash
ip route | grep default
```

## 4. Check DNS Configuration

Inspect the DNS resolver configuration currently used by the system.

```bash
cat /etc/resolv.conf
```

## 5. Test Connectivity to Google DNS

Send four ICMP packets to Google's public DNS server to test network connectivity.

```bash
ping -c 4 8.8.8.8
```

## 6. Test Connectivity to Cloudflare DNS

Send four ICMP packets to Cloudflare's public DNS server.

```bash
ping -c 4 1.1.1.1
```

## 7. Test HTTP/HTTPS Connectivity

Fetch only the HTTP response headers from Google to verify HTTPS connectivity.

```bash
curl -I https://google.com
```

---

### Command Summary

| Purpose | Command |
|---|---|
| Network interfaces | `ip addr` |
| Routing table | `ip route` |
| Default gateway | `ip route \| grep default` |
| DNS configuration | `cat /etc/resolv.conf` |
| Google DNS connectivity | `ping -c 4 8.8.8.8` |
| Cloudflare DNS connectivity | `ping -c 4 1.1.1.1` |
| HTTPS connectivity | `curl -I https://google.com` |
