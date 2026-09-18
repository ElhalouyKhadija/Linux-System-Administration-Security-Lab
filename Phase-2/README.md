# Phase 2 — Network Configuration & Connectivity

## Objective

This phase focused on checking the network configuration and connectivity on **Kali Linux**.

The objective was to inspect the network interface, IP configuration, routing, DNS settings, and external network connectivity.

## Network Configuration

The network configuration identified during the practical lab was:

```text
Interface:       eth0
IP address:      192.168.0.117/24
Default gateway: 192.168.0.1
DNS server:      192.168.0.1
```

## Network Configuration Verification

The network interface and IP address were checked using:

```bash
ip addr
```

The routing table was checked using:

```bash
ip route
```

DNS configuration was inspected using:

```bash
cat /etc/resolv.conf
```

## Connectivity Tests

### Test 1 — Google DNS

The connection to `8.8.8.8` was tested with:

```bash
ping -c 4 8.8.8.8
```

Result:

```text
4 packets transmitted
4 packets received
0% packet loss
```

### Test 2 — Cloudflare DNS

The connection to `1.1.1.1` was tested with:

```bash
ping -c 4 1.1.1.1
```

Result:

```text
4 packets transmitted
4 packets received
0% packet loss
```

### Test 3 — HTTPS Connectivity

HTTPS connectivity was tested using:

```bash
curl -I https://google.com
```

Result:

```text
HTTP/2 301
```

The response confirmed that the system could establish an HTTPS connection to the website.

## Network Concepts Practiced

During this phase, the following concepts were examined:

```text
Network Interface
        ↓
IP Address
        ↓
Default Gateway
        ↓
DNS Configuration
        ↓
Internet Connectivity
```

## What I Learned

Through this phase, I practiced:

- Linux network interfaces
- `ip addr`
- IPv4 addressing
- Subnet notation
- Routing
- Default gateway
- `ip route`
- DNS configuration
- `/etc/resolv.conf`
- Network connectivity testing
- `ping`
- `curl`
- HTTP/HTTPS connectivity

## Practical Evidence

This phase includes network configuration details, connectivity tests, command results, and screenshots collected from the Kali Linux lab.

## Practical Status

**Applied / Completed**

This phase was practically performed on Kali Linux and verified using network configuration commands, connectivity tests, command results, and screenshots.
