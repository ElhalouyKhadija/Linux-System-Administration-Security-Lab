# Phase 2 — Network Configuration & Connectivity

## Objective

This phase focused on inspecting network configuration and testing network connectivity on Kali Linux.

The objective was to review the network interface, IP addressing, routing, DNS configuration, and external network connectivity.

## Network Configuration

The network configuration identified during the practical lab was:

```text
Interface:       eth0
IP address:      192.168.0.117/24
Default gateway: 192.168.0.1
DNS server:      192.168.0.1
```

## Network Configuration Verification

The network interface and IP address were inspected using:

```bash
ip addr
```

The routing table was inspected using:

```bash
ip route
```

DNS configuration was inspected using:

```bash
cat /etc/resolv.conf
```

## Connectivity Tests

### Test 1 — Google DNS

Connectivity to `8.8.8.8` was tested using:

```bash
ping -c 4 8.8.8.8
```

Observed result:

```text
4 packets transmitted
4 packets received
0% packet loss
```

The test completed successfully with no packet loss.

### Test 2 — Cloudflare DNS

Connectivity to `1.1.1.1` was tested using:

```bash
ping -c 4 1.1.1.1
```

Observed result:

```text
4 packets transmitted
4 packets received
0% packet loss
```

The test completed successfully with no packet loss.

### Test 3 — HTTPS Connectivity

HTTPS connectivity was tested using:

```bash
curl -I https://google.com
```

Observed result:

```text
HTTP/2 301
```

The received HTTP response confirmed successful HTTPS connectivity to the tested website.

## Network Concepts Practiced

The practical work covered the following basic network path:

```text
Network Interface
        ↓
IP Address
        ↓
Default Gateway
        ↓
DNS Configuration
        ↓
External Network Connectivity
```

## Skills Practiced

* Linux network interfaces
* IPv4 addressing
* Subnet notation
* Routing
* Default gateway configuration
* DNS configuration
* `/etc/resolv.conf`
* Network connectivity testing
* `ping`
* `curl`
* HTTP/HTTPS connectivity

## Practical Evidence

The practical work was performed on Kali Linux using the network configuration and connectivity commands documented above.

One screenshot is included as visual evidence of the practical work performed during this phase.

## Practical Status

**Applied / Completed**

The network configuration and connectivity tests were performed and documented during the practical lab.
